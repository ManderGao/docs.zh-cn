---
title: 如何：设置客户端请求（WCF 数据服务）中的标头
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, customizing requests
ms.assetid: 3d55168d-5901-4f48-8117-6c93da3ab5ae
ms.openlocfilehash: e6b9b01f18e8412857a38a8e22fadfa88faf9d24
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33361781"
---
# <a name="how-to-set-headers-in-the-client-request-wcf-data-services"></a>如何：设置客户端请求（WCF 数据服务）中的标头
使用 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]客户端库访问支持 [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] 的数据服务时，客户端库会自动在发送给数据服务的请求消息中设置所需 HTTP 标头。 但是，在某些情况下客户端库不知道要设置所需的消息标头，例如当数据服务要求基于声明的身份验证或 Cookie 时。 有关详细信息，请参阅[WCF 数据服务的安全](../../../../docs/framework/data/wcf/securing-wcf-data-services.md#clientAuthentication)。 这时，必须先在请求消息中手动设置消息标头，然后再发送消息。 本主题中的示例揭示了如何处理 <xref:System.Data.Services.Client.DataServiceContext.SendingRequest> 事件以便在将请求消息发送至数据服务之前在其中添加新标头。  
  
 本主题中的示例使用罗斯文示例数据服务和自动生成的客户端数据服务类。 在完成时创建此服务和客户端数据类[WCF 数据服务快速入门](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)。 你还可以使用[Northwind 示例数据服务](http://go.microsoft.com/fwlink/?LinkId=187426)发布在[!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]网站; 此示例数据服务是只读的并在尝试保存更改返回错误。 上的示例数据服务[!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]网站允许匿名身份验证。  
  
## <a name="example"></a>示例  
 以下示例为 <xref:System.Data.Services.Client.DataServiceContext.SendingRequest> 事件注册一个处理程序，然后执行针对数据服务的查询。  
  
> [!NOTE]
>  如果数据服务要求为每个请求手动设置消息标头，则考虑在代表数据服务的实体容器（在本例中为 <xref:System.Data.Services.Client.DataServiceContext.SendingRequest>）中覆盖 `OnContextCreated` 分部方法，以此注册 `NorthwindEntities` 事件的处理程序。  
  
[!code-csharp[Astoria Northwind Client#RegisterHeadersQuery](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#registerheadersquery)]   
[!code-vb[Astoria Northwind Client#RegisterHeadersQuery](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#registerheadersquery)]
  
## <a name="example"></a>示例  
 以下方法将处理 <xref:System.Data.Services.Client.DataServiceContext.SendingRequest> 事件并为请求添加一个身份验证标头。  
  
 [!code-csharp[Astoria Northwind Client#OnSendingRequest](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#onsendingrequest)]  
 [!code-vb[Astoria Northwind Client#OnSendingRequest](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#onsendingrequest)]  
  
## <a name="see-also"></a>请参阅  
 [确保 WCF Data Services 的安全](../../../../docs/framework/data/wcf/securing-wcf-data-services.md)  
 [WCF Data Services 客户端库](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)
