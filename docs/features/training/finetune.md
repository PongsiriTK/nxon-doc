# Fine-tune Service

## Overview

The Fine-tune Service on {{ user_name }} provides a platform for fine-tuning pre-trained models with custom datasets. This service is designed to help users adapt models to specific tasks or domains, enhancing their performance and accuracy.

## Key Features

- **Custom Dataset Integration**: Easily upload and integrate your datasets for fine-tuning.
- **Parameter Customization**: Flexibly set fine-tuning parameters such as learning rates and epochs.
- **Performance Evaluation**: Utilize tools to evaluate the performance of fine-tuned models to ensure they meet your standards.
- **Resource Optimization**: Leverage {{ user_name }}'s infrastructure to optimize resource allocation for your fine-tuning tasks.

## Accessing Fine-tune Service

To access the Fine-tune Service, navigate to the NXON.AI platform and select "Fine-tune" from the Training Service menu.

![Menu Fine-tune](../images/{{ resource_dir_name }}/finetune_/menu_fine_tune.png){: style="width:30%" }

## Creating a New Fine-tune Job

![New Fine-tune Job](../images/{{ resource_dir_name }}/finetune_/fine_tune_job.png)

### Step 1: Name
Please enter the name of your fine-tune job.

### Step 2: Model
Select a pre-trained model from the dropdown menu.

### Step 3: Method
Choose the fine-tuning method, either "Full" or "Lora".

### Step 4: Epoch
Set the number of training epochs.

### Step 5: Learning Rate
Set the learning rate, for example, 0.00001.

### Step 6: Data Path
Upload the data path that you have stored in object storage.

### Step 7: Validation Ratio
Set the proportion of the dataset to be used for validation, for example, 0.01.

### Step 8: Resources
Select the location of the resources you wish to use for the fine-tune job, such as Malaysia.

### Step 9: Confirm
Review the estimated cost and confirm the creation of the fine-tune job.

## Fine-tune Job List

![Fine-tune Job List](../images/{{ resource_dir_name }}/finetune_/fine_tune_table.png)

In the fine-tune job list, you can view the name, method, model, status, resource, creation time, and operation options for all fine-tune jobs.

## Next Steps

After completing the fine-tuning, you can proceed to explore the [Training Service](training.md) to continue your model development process.

!!! tip "Get Started Today"
    For more information, refer to the related sections or visit our [support page](#) to begin using the platform today.