---
id: bcs-instance-overview
title: BCS instance overview
description: This document describes basic information about BCS instances, including options for selecting instance types and Instance family.
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

In a cloud computing environment, an instance refers to a unit of virtualized computing resources.  Instances are typically implemented as [Virtual Machine](/service/bcs/vm). In some cases, however, they can also be implemented as [Bare Metal Servers](/service/bcs/bms), which are non-virtualized physical servers.

All Beyond Compute Service (BCS) instances not only support common frameworks and libraries but also NVIDIA specialized libraries such as TensorRT, cuDNN, and NCCL. Additionally, you can leverage various features and services provided by the cloud platform and adjust instances flexibly or connect multiple instances for parallel processing as needed.

## ## BCS instance type {#bcs-instance-type}

To choose the instance type optimized for your business, you need to review workload requirements, including CPU, memory, storage, network, and other resources.  For example, you should carefully consider performance requirements of your applications, size of datasets, and the number of users or requests to be supported.  Furthermore, since different instance types may vary in performance and cost, you should consider budget constraints to determine the affordable range of spending.

After identifying workload requirements and budget, you should examine the various instance types available in KakaoCloud. Each instance type may be optimized for different types of workloads based on CPU, memory, and network resources, so you need to consider the instance type that best suits their business purposes.  KakaoCloud supports both general-purpose instance types and those specialized for compute-intensive or memory-intensive workloads.

The instance types offered by KakaoCloud include:

| Instance type                                                                               | Instance family                                                                                                                                                                                           |
| ------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [General purpose instances](/service/bcs/bcs-instance/bcs-type/general-purpose)             | `m3az`, `m2a`, `t1i`<br/>- General-purpose instances suitable for various workloads                                                                                                                       |
| [Compute optimized instances](/service/bcs/bcs-instance/bcs-type/compute-optimized)         | `c2a`<br/>- Instances suitable for compute-intensive workloads                                                                                                                                            |
| [Memory optimized instances](/service/bcs/bcs-instance/bcs-type/memory-optimized)           | `r2a` <br/>- Optimized for memory-intensive workloads, suitable for large-scale data processing<br/>- Provides more memory per core                                                                       |
| [Accelerated computing instances](/service/bcs/bcs-instance/bcs-type/accelerated-computing) | `p2a`, `p2i`, `p1i`, `gf1i`, `gn1i` <br/>- Suitable for machine learning (ML), high-performance computing (HPC) workloads requiring GPU, FPGA, etc. |
| [Video transcoding instances](/service/bcs/bcs-instance/bcs-type/video-transcoding)         | `vt1a`<br/>- Used for tasks like video file conversion, supporting conversion to different formats or resolutions                                                                                         |

<br/>
To ensure the selected instance type meets the requirements, it is recommended to measure performance using benchmarking tools after starting the instance. Subsequently, it is advisable to continuously monitor resource usage and promptly change instance types if requirements change or there are fluctuations in costs. <br/>

<br/>

:::info Instance Limits per region
There are limits on the total number of instances that can be launched in a region, and some instance types have additional limits. Each instance can connect to a maximum of 28 resources, including network interfaces and volume attachments.
:::

## ## Instance family {#instance-family}

An instance family consists of several instances with similar characteristics and conditions, optimized for specific types of workloads or purposes. <br/>
KakaoCloud offers various Instance family with unique features and conditions, available in different forms including Virtual Machine and Bare Metal Server.

| Instance family                                                                                                                          | Virtual Machine &emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp; | Bare Metal Server |
| ---------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------- |
| `m3az`                                                                                                                                   | `m3az.large`, `m3az.xlarge`, `m3az.2xlarge`, `m3az.4xlarge`, `m3az.6xlarge`,<br/> `m3az.8xlarge`                                                                                                       |                   |
| `m2a` &emsp;&emsp;&emsp;&emsp;&emsp; | `m2a.large`, `m2a.xlarge`, `m2a.2xlarge`, `m2a.4xlarge`,<br/> `m2a.8xlarge`, `m2a.12xlarge`, `m2a.16xlarge`, `m2a.24xlarge`                                                                            |                   |
| `t1i`                                                                                                                                    | `t1i.nano`, `t1i.micro`, `t1i.small`, `t1i.medium`, `t1i.large`,<br/> `t1i.xlarge`, `t1i.2xlarge`                                                                                                      |                   |
| `c2a`                                                                                                                                    | `c2a.large`, `c2a.xlarge`, `c2a.2xlarge`, `c2a.4xlarge`,<br/> `c2a.8xlarge`, `c2a.12xlarge`, `c2a.16xlarge`, `c2a.24xlarge`                                                                            |                   |

<br/>

:::tip Virtual Machine and Bare Metal Server instances
Virtual Machine instances utilize virtualized resources through a hypervisor, whereas Bare Metal Server instances provide <u>direct access to physical servers</u>, allowing you to directly access physical resources such as memory, disk, and network. It allows you to directly access physical resources such as memory, disk, and network.

KakaoCloud Bare Metal Server instances are indicated by adding `.baremetal` to the instance name, such as `r2a.baremetal`, `p2a.baremetal`, etc.
:::
