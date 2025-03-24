---
id: bcs-instance-overview
title: BCS 인스턴스 개요
description: 카카오클라우드 BCS 인스턴스 유형 선택지와 인스턴스 패밀리 등 BCS 인스턴스의 기본 정보를 설명합니다.
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';


클라우드 컴퓨팅 환경에서 인스턴스란 가상화된 컴퓨팅 리소스의 단위를 의미합니다. 인스턴스는 일반적으로 [Virtual Machine](/service/bcs/vm)으로 구현되지만,  경우에 따라 가상화되지 않은 물리 서버인 [Bare Metal Server](/service/bcs/bms)에서도 구현할 수 있습니다. 

모든 Beyond Compute Service(BCS) 인스턴스는 대부분 일반적인 프레임워크와 라이브러리를 지원할 뿐만 아니라, TensorRT, cuDNN, NCCL과 같은 NVIDIA 특화 라이브러리도 지원합니다. 또한, 클라우드 플랫폼에서 제공하는 다양한 기능과 서비스를 활용할 수 있으며, 필요에 따라 유연하게 인스턴스를 조정하거나, 여러 대의 인스턴스를 연결하여 병렬 처리를 수행할 수 있습니다.

## 인스턴스 유형 선택  {#choosing-instance-types}

클라우드 환경에서 비즈니스에 최적화된 인스턴스 유형을 선택하기 위해서는 CPU, 메모리, 스토리지, 네트워크 및 기타 리소스를 포함한 워크로드 요구 사항을 먼저 검토해야 합니다. 예를 들어, 애플리케이션의 성능 요구 사항, 데이터 세트의 크기, 지원해야 하는 사용자 또는 요청 수를 면밀하게 고려할 필요가 있습니다. 또한, 인스턴스 유형에 따라 성능과 비용 수준이 다를 수 있으므로, 지출할 수 있는 예산 범위를 결정해하기 위해 예산 제약 조건도 고려해야 합니다. 

워크로드 요구 사항과 예산을 파악한 후에는 카카오클라우드에서 사용할 수 있는 다양한 인스턴스 유형 제품군을 살펴보아야 합니다. 각 인스턴스 제품군은 CPU, 메모리 및 네트워크 리소스에 따라 다양한 유형의 워크로드에 최적화될 수 있기 때문에, 사용자는 비즈니스 목적에 맞는 인스턴스 유형을 고려해야 합니다. 카카오클라우드는 일반적인 인스턴스 유형과 컴퓨팅 집약적 또는 메모리 집약적인 특정 워크로드에 적합한 인스턴스 유형 또한 지원합니다.<br/>

카카오클라우드가 제공하는 인스턴스 유형은 다음과 같습니다. 

| 인스턴스 유형  | 인스턴스 패밀리 | 
| ---- | ----    |
| [범용 인스턴스](/service/bcs/bcs-instance/bcs-type/general-purpose)<br/> (General purpose instance)    | `m3az`, `m2a`, `t1i`<br/>- 다양한 워크로드에서 사용 가능한 범용 인스턴스    |
| [컴퓨팅 최적화 인스턴스](/service/bcs/bcs-instance/bcs-type/compute-optimized)<br/> (Compute optimized instance) | `c2a`<br/>- 컴퓨팅 집약적 워크로드에 적합한 인스턴스 |
| [메모리 최적화 인스턴스](/service/bcs/bcs-instance/bcs-type/memory-optimized)<br/> (Memory optimized instance) | `r2a` <br/>- 대규모 데이터 처리에 적합한 메모리 집약적 워크로드에 최적화<br/>- 코어당 더 많은 메모리 제공 |
| [가속 컴퓨팅 인스턴스](/service/bcs/bcs-instance/bcs-type/accelerated-computing)<br/> (Accelerated computing instance) | `p2a`, `p2i`, `p1i`, `gf1i`, `gn1i` <br/>- GPU, FPGA 등을 필요로 하는 머신러닝(ML), 고성능 컴퓨팅(HPC) 워크로드에 적합|
| [비디오 트랜스코딩 인스턴스](/service/bcs/bcs-instance/bcs-type/video-transcoding)<br/> (Video transcoding instance) | `vt1a`<br/>- 비디오 파일 변환과 같은 작업에 사용되며 다른 형식이나 해상도로 변환 가능 |

<br/>
요구사항에 적합한 인스턴스 유형인지 확인하기 위해서는, 인스턴스를 시작한 후 벤치마킹 도구를 사용하여 성능을 측정하는 것이 좋습니다. 이후, 리소스 사용량을 지속해서 모니터링하여 요구사항이 변경되거나 비용의 변화에 따라 인스턴스 유형을 신속하게 변경할 수 있습니다. <br/>

<br/>

:::info 리전별 인스턴스 개수 제한
한 리전에서 시작할 수 있는 인스턴스 총수에는 제한이 있으며, 일부 인스턴스 유형에는 또 다른 제한이 있습니다. 인스턴스는 네트워크 인터페이스, 볼륨 연결을 포함해 인스턴스별로 최대 28개까지 연결할 수 있습니다.
:::



## 인스턴스 패밀리 {#instance-families}

인스턴스 패밀리는 특정한 종류의 워크로드나 용도에 최적화되어 있으며, 비슷한 특성을 가진 여러 인스턴스를 포함하는 그룹입니다. <br/>
카카오클라우드가 제공하는 다양한 인스턴스 패밀리는 고유한 특징과 조건을 가지고 있으며, Virtual Machine과 Bare Metal Server를 포함한 다양한 형태로 제공됩니다.


| 인스턴스 패밀리 | Virtual Machine &emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp; | Bare Metal Server|
|---------|--------|---------|
| `m3az`  | `m3az.large`, `m3az.xlarge`, `m3az.2xlarge`, `m3az.4xlarge`, `m3az.6xlarge`,<br/> `m3az.8xlarge`|  |
| `m2a` &emsp;&emsp;&emsp;&emsp;&emsp;  | `m2a.large`, `m2a.xlarge`, `m2a.2xlarge`, `m2a.4xlarge`,<br/> `m2a.8xlarge`, `m2a.12xlarge`, `m2a.16xlarge`, `m2a.24xlarge` |  |
| `t1i`  | `t1i.nano`, `t1i.micro`, `t1i.small`, `t1i.medium`, `t1i.large`,<br/> `t1i.xlarge`, `t1i.2xlarge`|  |
| `c2a`    | `c2a.large`, `c2a.xlarge`, `c2a.2xlarge`, `c2a.4xlarge`,<br/> `c2a.8xlarge`, `c2a.12xlarge`, `c2a.16xlarge`, `c2a.24xlarge`|  |
| `r2a`    | `r2a.large`, `r2a.xlarge`, `r2a.2xlarge`, `r2a.4xlarge`,<br/> `r2a.8xlarge`, `r2a.12xlarge`, `r2a.16xlarge`, `r2a.24xlarge` | `r2a.baremetal` |
| `p2a`    | | `p2a.baremetal` |
| `p2i`    | `p2i.6xlarge`, `p2i.12xlarge`, `p2i.24xlarge` | |
| `p1i`    | | `p1i.baremetal` |
| `gf1i` | `gf1i.6xlarge`, `gf1i.12xlarge`, `gf1i.24xlarge` | |
| `gn1i` | `gn1i.xlarge`, `gn1i.2xlarge`, `gn1i.4xlarge`,<br/> `gn1i.8xlarge`, `gn1i.12xlarge`, `gn1i.16xlarge` | |
| `vt1a` | `vt1a.4xlarge`, `vt1a.8xlarge`, `vt1a.32xlarge` | |


<br/>

:::tip Bare Metal Server 인스턴스의 구분
Virtual Machine 인스턴스는 하이퍼바이저를 통해 가상화된 리소스를 사용하는 반면, Bare Metal Server 인스턴스는 <u>물리 서버에 직접 액세스할 수 있는 인스턴스</u>입니다. 즉, 사용자는 애플리케이션이 필요로 하는 메모리, 디스크, 네트워크 등의 물리적 리소스에 직접 접근할 수 있습니다.

카카오클라우드 Bare Metal 인스턴스는 `r2a.baremetal`, `p2a.baremetal` 등의 인스턴스 명칭에 `.baremetal`이 포함됩니다. 
:::
