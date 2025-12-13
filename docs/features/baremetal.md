# Bare Metal

## Overview

Bare Metal Service Management allows users to fully leverage the power and performance of physical servers while maintaining control and flexibility over their configurations and operations.

## Accessing Bare Metal Section

Navigate to the side navigation bar and click on the "Bare Metal" section.

![Accessing Bare Metal Section](images/{{ resource_dir_name }}/bm/bare_metal_menu.png){: style="width:30%"}

## Creating a New Bare Metal Instance

### Step 1: Click the Create Button
On the Bare Metal page, click the **Create** button to start the process of creating a new instance.

![Creating a New Bare Metal Instance](images/{{ resource_dir_name }}/bm/bare_metal_create.png)

### Step 2: Configure Instance Details
- **Cluster Name**: Provide a name for your cluster (alphanumeric characters and dashes only).
- **Duration (Weeks)**: Specify the duration for which you want to reserve the cluster.
- **Cluster Type**: Choose the type of cluster that suits your needs.
- **Region**: Select the region closest to you for reduced latency.
- **SSH Key**: Select an SSH key for secure access.

![Configure Bare Metal Instance](images/{{ resource_dir_name }}/bm/bare_metal_creation.png)

### Summary
Review the summary which includes details like GPU Type, GPU Memory, CPU, vCPU, Memory, and the total cost.

### Step 3: Confirm Creation
After verifying all details, click **Confirm** to create your Bare Metal instance.

## Managing Bare Metal Instances

### Step 4: Reviewing Instance List
Review the list of your instances to check their status, including Cluster Name, StartTime, EndTime, and Region.

### Step 5: Managing Instance Status
Manage the status of your instances by clicking on "Detail" to view more information, and perform actions such as activation, deactivation, or deletion.

## Next Steps

After setting up your organization, you can explore additional services such as [Storage](storage.md) to further enhance your application's capabilities.
