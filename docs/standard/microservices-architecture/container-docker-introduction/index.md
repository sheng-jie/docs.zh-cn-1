---
title: 容器和 Docker 简介
description: 适用于容器化 .NET 应用程序的 .NET 微服务体系结构 | 容器和 Docker 简介
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: 8d9334785b2f3ee770c5f0e6bd2e13faa995b6f2
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/29/2018
ms.locfileid: "37106822"
---
# <a name="introduction-to-containers-and-docker"></a>容器和 Docker 简介

容器化是软件开发的一种方法，通过该方法可将应用程序或服务的依赖项及其配置（抽象化为部署清单文件）一起打包为容器镜像。 容器化应用程序可以作为一个单元进行测试，并可以作为容器镜像实例部署到主机操作系统 (OS)。

就像船只、火车或卡车运输集装箱而不论其内部的货物一样，软件容器充当软件的标准单元，其中可以包含不同的代码和依赖项。 按照这种方式容器化软件，开发人员和 IT 专业人员只需进行极少修改或不修改，即可将其部署到不同的环境。

容器还会在共享 OS 上将应用程序彼此隔离开。 容器化应用程序在容器主机上运行，而容器主机在 OS（Linux 或 Windows）上运行。 因此，容器的占用比虚拟机 (VM) 镜像小得多。

每个容器可以运行整个 Web 应用或服务，如图 2-1 所示。 在此示例中，Docker 主机是容器主机，而 App1、App2、Svc 1 和 Svc 2 是容器化应用程序或服务。

![](./media/image1.png)

**图 2-1**. 在一个容器主机上运行多个容器

容器化的另一个优势在于可伸缩性。 通过为短期任务创建新容器，可以快速扩大。 从应用程序的角度来看，实例化镜像（创建容器）类似于实例化 服务或 Web 应用等进程。 但出于可靠性考虑，在多个主机服务器上运行同一镜像的多个实例时，通常要使每个容器（镜像实例）在不同容错域中的不同主机服务器或 VM 中运行。

总而言之，容器在整个应用程序生命周期工作流中提供以下优点：隔离性、可移植性、灵活性、可伸缩性和可控性。 最重要的优点是可在开发和操作之间提供隔离。


>[!div class="step-by-step"]
[上一页](../index.md)
[下一页](docker-defined.md)
