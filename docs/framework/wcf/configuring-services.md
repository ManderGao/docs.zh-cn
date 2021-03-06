---
title: 正在配置服务
ms.date: 03/30/2017
helpviewer_keywords:
- configuration [WCF]
ms.assetid: beac771e-f28e-4f84-9ff1-ad9251c726d3
ms.openlocfilehash: 7718edaefbad18afa11b3e3680fac39da585a610
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2018
ms.locfileid: "33803275"
---
# <a name="configuring-services"></a>正在配置服务
在设计和实现服务协定后，即可配置服务。 在其中可以定义和自定义如何向客户端公开服务，包括指定可以找到服务的地址、服务用于发送和接收消息的传输和消息编码，以及服务需要的安全类型。  
  
 此处使用的配置包括在代码中以强制方式或通过使用配置文件定义和自定义服务的各个方面的所有方法，例如指定其终结点地址、使用的传输及其安全方案。 在实践中，编写配置是一个较大编程 WCF 应用程序的一部分。  
  
## <a name="in-this-section"></a>本节内容  
 [简化配置](../../../docs/framework/wcf/simplified-configuration.md)  
 从开始[!INCLUDE[netfx40_long](../../../includes/netfx40-long-md.md)]，WCF 附带一个新的默认配置模型，简化了 WCF 配置要求。 如果你不提供针对特定服务的任何 WCF 配置，运行时自动使用默认终结点、 绑定和行为配置你的服务。  
  
 [使用配置文件配置服务](../../../docs/framework/wcf/configuring-services-using-configuration-files.md)  
 Windows Communication Foundation (WCF) 服务是可配置使用[!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]技术的配置。 通常情况下，到承载 WCF 服务的 Internet 信息服务 (IIS) 网站的 Web.config 文件添加 XML 元素。 这些元素允许您更改详细信息，例如每台计算机上的终结点地址（用于与服务进行通信的实际地址）。  
  
 [绑定](../../../docs/framework/wcf/bindings.md)  
 此外，WCF 允许你用于快速选择最基本的功能的客户端和服务的通信方式，如传输、 安全性和消息编码使用的绑定的形式包括几个系统提供的常见配置。  
  
 [终结点](../../../docs/framework/wcf/endpoints.md)  
 与 WCF 服务的所有通信都是通过*终结点*的服务。 终结点包含协定、在绑定中指定的配置信息，以及指示查找服务或获取该服务相关信息的位置的地址。  
  
 [保护服务](../../../docs/framework/wcf/securing-services.md)  
 使用 WCF 和现有安全机制，你可以实现保密性、 完整性、 身份验证和授权到任何服务。 还可以审核安全成功和安全失败。  
  
 [创建 WS-I 基本配置文件 1.1 交互服务](../../../docs/framework/wcf/creating-ws-i-basic-profile-1-1-interoperable-services.md)  
 WS-I 基本配置文件 1.1 规范中概述了部署服务的需求，该服务可与其他任何平台或操作系统上的服务和客户端进行互操作。  
  
## <a name="reference"></a>参考  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Description>  
  
## <a name="related-sections"></a>相关章节  
 [基本编程生命周期](../../../docs/framework/wcf/basic-programming-lifecycle.md)  
  
 [设计和实现服务](../../../docs/framework/wcf/designing-and-implementing-services.md)  
  
 [托管服务](../../../docs/framework/wcf/hosting-services.md)  
  
 [生成客户端](../../../docs/framework/wcf/building-clients.md)  
  
 [扩展性简介](../../../docs/framework/wcf/introduction-to-extensibility.md)  
  
 [管理和诊断](../../../docs/framework/wcf/diagnostics/index.md)  
  
## <a name="see-also"></a>请参阅  
 [基本 WCF 编程](../../../docs/framework/wcf/basic-wcf-programming.md)  
 [概念性概述](../../../docs/framework/wcf/conceptual-overview.md)  
 [WCF 功能详细信息](../../../docs/framework/wcf/feature-details/index.md)
