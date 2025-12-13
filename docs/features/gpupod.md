# GPU Pods 

## Overview

The GPU Pods Management section provides a comprehensive guide on creating, managing, and scaling GPU Pods within the {{ user_name }} platform. This section is designed to assist users in optimizing their AI applications by fully utilizing the capabilities of GPU resources.

## Accessing GPU Pods

To access the GPU Pods management interface, navigate to the sidebar menu and click on **GPU Pod**.

![Access GPU Pods](images/{{ resource_dir_name }}/gpu/gpu_pod_menu.png){: style="width:30%"}

## Creating New GPU Pod

### Step 1: Click the New Button
Click the **New** button on the GPU Pod page to start the creation process.
![New GPU Pod Button](images/{{ resource_dir_name }}/gpu/gpu_pod_new.png)

### Step 2: Fill in Pod Details
Enter a name for your Pod and select the region resources. Choose the image type (Public or Private) and set the image pull policy (Always or IfNotPresent).
![New Pod Creation Form](images/{{ resource_dir_name }}/gpu/new_gpu_pod.png)

### Summary
Before confirming, review the summary which includes details like GPU Type, GPU Memory, CPU, vCPU, Memory, Name, Instance Count, and Service Region.

### Advanced Settings
Configure advanced settings such as Start Command, File system mount, Environment Variable, Ports & Protocol, and Lifecycle scripts.

## Managing GPU Pods

You can manage your GPU Pods by performing various tasks such as viewing their status, analyzing logs, monitoring performance metrics, and troubleshooting.

### Viewing Pod Status
Check the operational status of your GPU Pods, including startup status, runtime, and resource usage.

### Log Analysis
Use log analysis tools to query logs based on keywords and time ranges.

### Performance Monitoring
Monitor performance metrics like network traffic and request response times.

### Troubleshooting
Use diagnostic tools to locate and resolve faults.

## Viewing Pod Details

For detailed information about a specific Pod, click on the **Detail** button.

### Job Info

| Attribute         | Description                     |
|-------------------|---------------------------------|
| Name              | Name of the GPU Pod             |
| With Jupyter Lab  | Status of Jupyter notebook      |
| Status            | Current status of the Pod       |
| Create Time       | Time when the Pod was created   |

### Resource Information

| Attribute         | Description                     |
|-------------------|---------------------------------|
| Name              | Name of the allocated resource  |
| CPU               | Type of CPU                     |
| vCPU              | Number of virtual CPUs          |
| Memory            | Amount of memory                |
| GPUs              | Number and type of GPUs         |
| GPU Memory        | Amount of GPU memory            |

![GPU Pod Details](images/{{ resource_dir_name }}/gpu/gpu_pod_details.png)

## Next Steps


For more information on how to optimize your GPU Pods, proceed to the [Bare Metal](baremetal.md) section.
