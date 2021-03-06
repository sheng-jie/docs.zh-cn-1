---
title: 将 ASP.NET Web 服务迁移到 WCF
ms.date: 03/30/2017
ms.assetid: 1adbb931-f0b1-47f3-9caf-169e4edc9907
ms.openlocfilehash: 7d43c66952d17a91e38ae1b086478b9416321b8a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33494557"
---
# <a name="migrating-aspnet-web-services-to-wcf"></a>将 ASP.NET Web 服务迁移到 WCF
ASP.NET 提供 .NET Framework 类库和工具以用于生成 Web 服务，并提供用于在 Internet Information Services (IIS) 内承载服务的功能。 Windows Communication Foundation (WCF) 提供.NET Framework 类库、 工具和承载功能，使软件实体可以使用任何协议，包括由 Web 服务使用的协议进行通信。  将 ASP.NET Web 服务迁移到 WCF 允许你的应用程序充分利用新功能和特定于 WCF 的改进。  
  
 WCF 具有对于 ASP.NET Web 服务的多个重要优势。 尽管 ASP.NET Web 服务工具仅用于生成 Web 服务，WCF 提供了必须使软件实体之间相互通信时，可以使用的工具。 这会减少开发人员为适应不同软件通信方案而必需了解的技术的数量，从而降低软件开发资源的成本及完成软件开发项目所需的时间。  
  
 即使对于 Web 服务开发项目，WCF 支持协议比 ASP.NET Web 服务支持的更多 Web 服务。 这些附加协议提供更完善的解决方案，涉及可靠会话和事务等其他内容。  
  
 WCF 支持多个协议比 ASP.NET Web 服务的消息传输。 ASP.NET Web 服务仅支持使用超文本传输协议 (HTTP) 发送消息。 WCF 支持通过使用 HTTP，以及传输控制协议 (TCP)，命名管道和 Microsoft 消息队列 (MSMQ) 发送消息。 更重要的是，WCF 可以进行扩展以支持其他传输协议。 因此，使用 WCF 开发的软件可以进行适配以便与更广泛的其他软件，从而提高潜在的投资回报一起工作。  
  
 WCF 提供了用于部署多更丰富功能，并管理比 ASP.NET Web 服务的应用程序提供。 WCF 配置系统，ASP.NET 还提供了，除了提供配置编辑器，从发送方到接收方并通过任意数目的媒介、 跟踪查看器、 消息日志记录、 大量性能计数器的返回的活动跟踪和对 Windows Management Instrumentation 的支持。  
  
 给定这些潜在的好处的 WCF 相对于 ASP.NET Web 服务，如果你正在使用或正在考虑使用 ASP.NET Web 服务有几个选项：  
  
-   继续使用 ASP.NET Web 服务，放弃 WCF 提供的好处。  
  
-   继续使用 ASP.NET Web 服务，并打算在未来某个时刻采用 WCF。 此部分中的主题说明如何最大化才能使用新 ASP.NET Web 服务的应用程序以及将来的 WCF 应用程序的前景。 本部分中的主题还说明如何生成新的 ASP.NET Web 服务，以更加轻松地将它们迁移到 WCF。 但是，如果保证服务的安全，或者需要可靠性或事务保证是必需的或者如果自定义管理工具将需要构造，则它是更好的选择采用 WCF。 WCF 专为确切地说是这种情况。  
  
-   对于新开发，同时继续保持现有的 ASP.NET Web 服务应用程序采用 WCF。 这种选择很可能是最佳选择。 它的好处 WCF，同时可节省修改现有应用程序中，若要使用它的成本。 在此方案中，在现有的 ASP.NET 应用程序中新的 WCF 应用程序可以共存。 新的 WCF 应用程序将能够使用现有的 ASP.NET Web 服务，并可以使用 WCF 进行编程新操作功能编程到现有的 ASP.NET 应用程序，因为 WCF ASP.NET 兼容模式。  
  
-   采用 WCF 和现有 ASP.NET Web 服务应用程序迁移到 WCF。 你可以选择此选项以增强现有的应用程序与 WCF，提供的功能，或者以重现现有 ASP.NET Web 服务在新的功能、 更强大的 WCF 应用程序。  
  
> [!NOTE]
>  必须格外谨慎，如果承载 WCF 服务由 IIS 5.x 和 ASP.NET 被卸载。 当由 IIS 承载的 WCF 服务可能会在卸载 ASP.NET 请求 5.x，服务的代码。 运行 IIS 的操作系统上卸载 ASP.NET 卸载 5.x 和 WCF 带有.svc 扩展名的文件视为文本文件，其内容，包括任何源代码，会返回给请求者。  
  
 本部分介绍了这些选项在详细信息、 比较 ASP.NET Web 服务迁移到 WCF 和说明了如何将 ASP.NET Web 服务代码迁移到 WCF。  
  
## <a name="see-also"></a>请参阅  
 [预期采用 Windows Communication Foundation：便于以后迁移](../../../../docs/framework/wcf/feature-details/anticipating-adopting-wcf-migration.md)  
 [预期采用 Windows Communication Foundation：便于以后集成](../../../../docs/framework/wcf/feature-details/anticipating-adopting-the-wcf-easing-future-integration.md)  
 [采用 Windows Communication Foundation](../../../../docs/framework/wcf/feature-details/adopting-wcf.md)  
 [基于目标和使用的标准比较 ASP.NET Web 服务与 WCF](../../../../docs/framework/wcf/feature-details/comparing-aspnet-web-services-to-wcf-based-on-purpose-and-standards-used.md)  
 [从开发的角度比较 ASP.NET Web 服务与 WCF](../../../../docs/framework/wcf/feature-details/comparing-aspnet-web-services-to-wcf-based-on-development.md)
