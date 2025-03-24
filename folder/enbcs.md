---
id: bcs-instance-overview
title: BCS 인스턴스 개요
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

| 인스턴스 패밀리                                                                                                                                 | Virtual Machine &emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp; | Bare Metal Server |
| ---------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------- |
| `m3az`                                                                                                                                   | `m3az.large`, `m3az.xlarge`, `m3az.2xlarge`, `m3az.4xlarge`, `m3az.6xlarge`,<br/> `m3az.8xlarge`                                                                                                       |                   |
| `m2a` &emsp;&emsp;&emsp;&emsp;&emsp; | `m2a.large`, `m2a.xlarge`, `m2a.2xlarge`, `m2a.4xlarge`,<br/> `m2a.8xlarge`, `m2a.12xlarge`, `m2a.16xlarge`, `m2a.24xlarge`                                                                            |                   |
| `t1i`                                                                                                                                    | `t1i.nano`, `t1i.micro`, `t1i.small`, `t1i.medium`, `t1i.large`,<br/> `t1i.xlarge`, `t1i.2xlarge`                                                                                                      |                   |
| `c2a`                                                                                                                                    | `c2a.large`, `c2a.xlarge`, `c2a.2xlarge`, `c2a.4xlarge`,<br/> `c2a.8xlarge`, `c2a.12xlarge`, `c2a.16xlarge`, `c2a.24xlarge`                                                                            |                   |
| `r2a`                                                                                                                                    | `r2a.large`, `r2a.xlarge`, `r2a.2xlarge`, `r2a.4xlarge`,<br/> `r2a.8xlarge`, `r2a.12xlarge`, `r2a.16xlarge`, `r2a.24xlarge`                                                                            | `r2a.baremetal`   |
| `p2a`                                                                                                                                    |                                                                                                                                                                                                        | `p2a.baremetal`   |
| `p2i`                                                                                                                                    | `p2i.6xlarge`, `p2i.12xlarge`, `p2i.24xlarge`                                                                                                                                                          |                   |
| `p1i`                                                                                                                                    |                                                                                                                                                                                                        | `p1i.baremetal`   |
| `gf1i`                                                                                                                                   | `gf1i.6xlarge`, `gf1i.12xlarge`, `gf1i.24xlarge`                                                                                                                                                       |                   |
| `gn1i`                                                                                                                                   | `gn1i.xlarge`, `gn1i.2xlarge`, `gn1i.4xlarge`,<br/> `gn1i.8xlarge`, `gn1i.12xlarge`, `gn1i.16xlarge`                                                                                                   |                   |
| `vt1a`                                                                                                                                   | `vt1a.4xlarge`, `vt1a.8xlarge`, `vt1a.32xlarge`                                                                                                                                                        |                   |

<br/>

:::tip Bare Metal Server 인스턴스의 구분
Virtual Machine 인스턴스는 하이퍼바이저를 통해 가상화된 리소스를 사용하는 반면, Bare Metal Server 인스턴스는 <u>물리 서버에 직접 액세스할 수 있는 인스턴스</u>입니다. 즉, 사용자는 애플리케이션이 필요로 하는 메모리, 디스크, 네트워크 등의 물리적 리소스에 직접 접근할 수 있습니다.

카카오클라우드 Bare Metal 인스턴스는 `r2a.baremetal`, `p2a.baremetal` 등의 인스턴스 명칭에 `.baremetal`이 포함됩니다.
:::

## 인스턴스 명명 규칙 {#instance-naming-conventions}

각 인스턴스 유형의 명칭은 각 인스턴스 유형의 목적, 용도, 세대, 프로세서, 세부 정보와 크기를 조합하여 표기됩니다.

<table>
  <thead>
    <tr>
      <th>구분</th>
      <th>설명</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td rowSpan="7">인스턴스 패밀리</td>
      <td><code>m</code>: 범용, 등 인스턴스의 용도를 표시</td>
    </tr>
    <tr>
      <td><code>r</code>: 메모리 최적화</td>
    </tr>
    <tr>
      <td><code>c</code>: 컴퓨팅 최적화</td>
    </tr>
    <tr>
      <td><code>t</code>: 버스트 가능한 성능</td>
    </tr>
    <tr>
      <td><code>vt</code>: 비디오 트랜스코딩</td>
    </tr>
    <tr>
      <td><code>g</code>: 그래픽 집약적</td>
    </tr>
    <tr>
      <td><code>p</code>: GPU 가속</td>
    </tr>
    <tr>
      <td>인스턴스 세대</td>
      <td>숫자가 높을수록 최신 세대</td>
    </tr>
    <tr>
      <td rowSpan="2">인프로세서 패밀리</td>
      <td><code>i</code>: Intel 프로세서</td>
    </tr>
    <tr>
      <td><code>a</code>: AMD 프로세서</td>
    </tr>
    <tr>
       <td rowSpan="3">추가 가능</td>
      <td><code>n</code>: 네트워크 최적화</td>
    </tr>
    <tr>
      <td><code>z</code>: 고성능</td>
    </tr>
    <tr>
      <td><code>f</code>: NPU</td>
    </tr>
    <tr>
      <td>인스턴스 크기</td>
      <td>vCPU 수, Memory에 따라 달라짐<br/>- VM/GPU: nano, micro, small, medium, large, xlarge, 2xlarge 등<br/>- BM: baremetal</td>
    </tr>
  </tbody>
</table>


