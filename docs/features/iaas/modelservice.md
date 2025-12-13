# Model Service

## Overview

Model Service on {{ user_name }} allows users to deploy machine learning models as API services. This service enables easy deployment, API access, auto-scaling, and monitoring of model performance.

## Deploying a Model

### Step 1: Access Model Service
Log in to the {{ user_name }} platform and navigate to the Model Service section.

![Access Model Service](../images/{{ resource_dir_name }}/modelservice/model_service_menu.png){: style="width:30%"}

### Step 2: Create a New Model Service
Click on the "New Model Service" button to start the deployment process.

![Create New Model Service](../images/{{ resource_dir_name }}/modelservice/new_model_service.png)

### Step 3: Configure Model Service
- **Name**: Enter a name for your model service.
- **Model**: Choose between an official or private model. Select the model from the dropdown menu.
- **Workers**: Specify the number of workers needed for your service.
- **Resources**: Select the appropriate resources for your model service, including CPU, memory, and GPU options.

!!! tip
    Choose the number of workers and resources based on the expected load and performance requirements.

### Step 4: Confirm Deployment
Review your selections and click "Confirm" to deploy the model service.

## Managing Model Services

### Viewing Model Services
You can view all your deployed model services in the Model Services list. Here you can see the service status, resource usage, and creation time.

![Viewing Model Services](../images/{{ resource_dir_name }}/modelservice/model_service_list.png)

### Deleting a Model Service
To delete a model service, click the "Delete" button next to the service you wish to remove.

!!! warning
    Deletion is permanent and cannot be undone. Ensure that you no longer need the service before deleting.

### Updating a Model Service
If you need to update the configuration of a model service, click the "Detail" button to access the service settings and make necessary changes.

![Model Service Detail](../images/{{ resource_dir_name }}/modelservice/model_service_detail.png)

### Step 5: Model Operations
Once the model is deployed, you can perform operations such as viewing API documentation, model fine-tuning, model evaluation, and online experience.

!!! tip "Integration"
    Use the provided API documentation to integrate the model seamlessly into your applications.

## Next Steps

After deploying your model service, you may want to explore [Training Services](../training/index.md) to further develop and train your models, enhancing their performance and capabilities.

We wish you a successful experience with Model Service on {{ user_name }}!