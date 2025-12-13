# Serverless Endpoints

Welcome to the {{ user_name }} Learning Guide. This guide will help you understand and start using the serverless endpoints of our hosted Large Language Models (LLMs). By the end of this guide, you will have learned how to interact with the LLMs through a series of simple steps, using different programming languages.

!!! note
    Please ensure you have your API key from the {{ user_name }} platform to use the LLM endpoints. If you haven’t already, sign up for an account to get started.

## Step 1: Authentication

Before you can interact with the hosted LLM models, you need to authenticate with your API key. The API key authorizes access to {{ user_name }} endpoints.

!!! tip "Generate Your API Token"
    You may access the API key management function (creation) from **Cloud Portal** > **Settings** > **API Token**.


## Step 2: Finding Endpoint Information

You may find the supported models and their endpoints from **Cloud Portal** > **Inference As A Service** > **Playground**. When a model listed there is selected, click the **API** tab to show the endpoint information.

![Playground API Tab Screenshot](images/{{ resource_dir_name }}/endpoint.png)

Here is an example of the endpoint url:
``` bash
http://192.168.10.202:18081/api/v1/ai/chat/completions
```

!!! tip
    You may also find example code other than cURL command from **Cloud Portal** > **Inference As A Service** > **Playground** and then click the API tab. On the right side click the dropdown list to choose the language.

## Step 3: Sending Requests to the Endpoint

{{ user_name }}'s backend API is compatible with OpenAI, so you can use the OpenAI SDK and simply change the endpoint address to interact with  {{ user_name }}  models.

!!! note
    Please ensure you have your API key from the {{ user_name }} platform to use the LLM endpoints. If you haven’t already, sign up for an account to get started.

### Input Field Explanation

The table below explains each input field in detail:

| Field        | Description                                                                                   |
|--------------|-----------------------------------------------------------------------------------------------|
| **messages** | An array containing message objects. Each message should have a `role` (`system`, `user`, or `assistant`) and `content`. The `role` indicates the message's source. |
| **model**    | The identifier for the LLM model (e.g., `"meta-llama-3-8b-instruct"`).                         |
| **stream**   | A boolean value (`true` or `false`) that indicates whether the response should be streamed in chunks or returned all at once.            |
| **maxTokens**| The maximum number of tokens to generate in the response.                                      |
| **temperature** | A value between 0 and 1 that controls the randomness of the output.                       |
| **topP**     | A value that controls the diversity of the generated output. Lower values make the output more deterministic.                         |

### Example in Different Languages

=== "Using cURL"
    
    ```bash
    curl --location 'http://192.168.10.202:18081/api/v1/ai/chat/completions' \
    --header 'Content-Type: application/json' \
    --header 'Authorization: Bearer ${TOKEN}' \
    --data '{
        "messages": [
            {
                "role": "system",
                "content": ""
            },
            {
                "role": "user",
                "content": "hi"
            }
        ],
        "model": "meta-llama-3-8b-instruct",
        "stream": false,
        "maxTokens": 1024,
        "temperature": 0.5,
        "topP": 0.02
    }'
    ```

=== "Using Python"
    
    Here’s how to make a request using Python's `requests` library:
    
    ```python
    import requests
    import os
    import openai

    API_KEY = os.getenv(" {{ user_name }} _API_KEY")

    client = openai.OpenAI(
        base_url="http://192.168.10.202:18081/api/v1/ai",
        api_key=API_KEY
    )

    completion = client.chat.completions.create(
        model="$model",
        messages=[
            {"role": "user", "content": "say hello"},
        ],
        max_tokens=128,
        stream=True,
    )

    for chunk in completion:
        if not chunk.choices:
            continue
        content = chunk.choices[0].delta.content
        if content:
            print(content, end="")
    ```

=== "Using Node.js"
    
    ```javascript
    import OpenAI from 'openai';

    const openai = new OpenAI({
      apiKey: process.env. {{ user_name }} _API_KEY,
      baseURL: 'http://192.168.10.202:18081/api/v1/ai',
      dangerouslyAllowBrowser: true,
    });

    async function main() {
      const completion = await openai.chat.completions.create({
        messages: [{ role: 'user', content: 'say hello' }],
        model: '$model', 
      });

      console.log(completion.choices);
      
    }
    
    main();
    ```

## Step 4: Handling the Response

After sending a request, the response from the model will typically contain text and meta-information such as token usage.

!!! tip
    When you are using OpenAI API to access the endpoint, you normally don't need to handle all the details of the response json. Instead you just need to access the returned object from the API.

### Response Structure

The response structure depends on whether the `stream` field is set to `true` or `false`.

=== "When `stream` is set to `false`"

    The response will contain the following fields:
    !!! example
        ```json
        {
            "code": 200,
            "msg": "Operation successful",
            "data": {
                "id": "chat-4efd9b46dc6643039b77f0cba5fd1643",
                "object": "chat.completion",
                "created": 1731468962,
                "model": "meta-llama-3-8b-instruct",
                "choices": [
                    {
                        "index": 0,
                        "message": {
                            "role": "assistant",
                            "content": "Hi! It's nice to meet you. Is there something I can help you with or would you like to chat?",
                            "tool_calls": []
                        },
                        "logprobs": null,
                        "finish_reason": "stop",
                        "stop_reason": null
                    }
                ],
                "usage": {
                    "prompt_tokens": 16,
                    "total_tokens": 41,
                    "completion_tokens": 25
                },
                "prompt_logprobs": null
            }
        }
        ```

    **Explanation**:

    - **code**: HTTP status code indicating success (200).
    - **msg**: Message indicating the operation's result.
    - **data**: Contains the detailed response information.
      - **id**: Unique identifier for the request.
      - **object**: Type of response object.
      - **created**: Unix timestamp for when the response was generated.
      - **model**: The model used to generate the response.
      - **choices**: An array of response options generated by the model.
        - **message**: Contains the generated content from the assistant.
        - **finish_reason**: Reason for stopping the generation.
      - **usage**: Information about the token usage.
    
    !!! tip
        The `usage` field can be helpful for monitoring API costs.

=== "When `stream` is set to `true`"

    The response is sent as multiple events, with each event providing a portion of the generated text:

    !!! example
        ```
        event:messages
        data:{"id":"chat-408025dcca3e4c3296b0d069081a26a1","object":"chat.completion.chunk","created":1731469002,"model":"meta-llama-3-8b-instruct","choices":[{"index":0,"delta":{"role":"assistant","content":""},"logprobs":null,"finish_reason":null}],"usage":{"prompt_tokens":16,"total_tokens":16,"completion_tokens":0}}

        event:messages
        data:{"id":"chat-408025dcca3e4c3296b0d069081a26a1","object":"chat.completion.chunk","created":1731469002,"model":"meta-llama-3-8b-instruct","choices":[{"index":0,"delta":{"content":"Hi"},"logprobs":null,"finish_reason":null}],"usage":{"prompt_tokens":16,"total_tokens":17,"completion_tokens":1}}

        event:messages
        data:{"id":"chat-408025dcca3e4c3296b0d069081a26a1","object":"chat.completion.chunk","created":1731469002,"model":"meta-llama-3-8b-instruct","choices":[{"index":0,"delta":{"content":"!"},"logprobs":null,"finish_reason":null}],"usage":{"prompt_tokens":16,"total_tokens":17,"completion_tokens":1}}
        ```
    
    !!! tip
        Use the `usage` field to monitor your API token consumption to optimize costs.

## Common Issues & Solutions

| Issue                      | Solution                                    |
|----------------------------|---------------------------------------------|
| Authentication error       | Ensure the API key is correct and active    |
| Request timeout            | Verify network connectivity and retry       |
| Unexpected response format | Confirm the model name and request payload  |

!!! note
    Always check for updates to the {{ user_name }} API documentation for new features and improvements.

## Next Steps

Now that you've made your first requests to the hosted LLM endpoints, try experimenting with different prompts and models. You can build applications that generate content, assist with customer service, or even automate tasks with  {{ user_name }} 's serverless LLM offerings.

Happy coding!
