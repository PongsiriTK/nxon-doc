# Training Service

## Overview

The Training Service on {{ user_name }} provides a user-friendly interface for managing machine learning model training tasks. With this service, you can easily deploy, monitor, and manage your training jobs using the computational resources available on the platform.

## Accessing the Training Dashboard

To access the Training Service, navigate to the  {{ user_name }}  platform and select "Training" from the menu.

![Training Menu](../images/{{ resource_dir_name }}/training/training_menu.png){: style="width:30%"}

## Creating a New Training Task

To create a new training task, follow these steps:

1. Click the "New" button to create a new training task.

![Training List](../images/{{ resource_dir_name }}/training/training_list.png)

2. Fill in the necessary details for your training task using the following parameters:

   | Parameter           | Description                                                                 |
   |----------------------|-----------------------------------------------------------------------------|
   | Name                | A unique identifier for your training task.                                  |
   | Model               | Choose the model to be used for training.                                    |
   | Workers             | The number of workers for your task.                                        |
   | Shared Memory       | The amount of shared memory allocated for the task (e.g., in Gi).            |
   | Resources           | The location of the resources you wish to use (e.g., Thailand).              |
   | Image               | Select the image to be used for the task (public or private).                |
   | ImagePullPolicy     | The policy for pulling the image (Always or IfNotPresent).                   |
   | Enable Tensorboard  | Enable or disable Tensorboard for your task.                                |
   | Backoff Limit       | The number of times the task will be retried upon failure.                    |
   | Max Restarts        | The maximum number of restarts for the task.                                 |
   | MASTER PORT         | The port number for the master node.                                        |

![New Training Job](../images/{{ resource_dir_name }}/training/new_training_job.png)

3. Review your configurations and click "Confirm" to deploy the training task.

## Viewing Training Tasks

After creating a training task, you can view detailed information about its status, resource usage, and performance metrics by clicking on the task name.

![Training Job Details](../images/{{ resource_dir_name }}/training/training_job_details.png)

## Managing Training Tasks

### Deleting a Task
To delete a training task, click the "Delete" button next to the task in the list.

### TensorBoard Integration
For tasks that support TensorBoard, click the "TensorBoard" link to visualize training metrics and logs.

## Next Steps

After deploying your training tasks, you can use the Training Dashboard to monitor their progress and performance. Adjust your training configurations as needed to optimize results. For further assistance or to explore advanced features, refer to the related sections or visit our [support page](#) on the {{ user_name }} platform.

For more information on fine-tuning your models, proceed to the [Finetune Service](./finetune.md).