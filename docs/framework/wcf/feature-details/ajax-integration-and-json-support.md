---
title: AJAX の統合と JSON のサポート
ms.date: 03/30/2017
helpviewer_keywords:
- AJAX integration and JSON support [WCF]
ms.assetid: 3851a8fc-d861-4ac1-873c-96af0343d3a7
ms.openlocfilehash: 54942386bb4fb88e72a86b5e25f12cee4776a126
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54625641"
---
# <a name="ajax-integration-and-json-support"></a><span data-ttu-id="2c93d-102">AJAX の統合と JSON のサポート</span><span class="sxs-lookup"><span data-stu-id="2c93d-102">AJAX Integration and JSON Support</span></span>
<span data-ttu-id="2c93d-103">ASP.NET Asynchronous JavaScript and XML (AJAX) の Windows Communication Foundation (WCF) のサポートと JavaScript Object Notation (JSON) データ形式は、AJAX クライアントに操作を公開する WCF サービスを許可します。</span><span class="sxs-lookup"><span data-stu-id="2c93d-103">The Windows Communication Foundation (WCF) support for ASP.NET Asynchronous JavaScript and XML (AJAX) and the JavaScript Object Notation (JSON) data format allow WCF services to expose operations to AJAX clients.</span></span> <span data-ttu-id="2c93d-104">AJAX クライアントは、JavaScript コードを実行して、HTTP 要求を使用してこれらの WCF サービスへのアクセスの Web ページです。</span><span class="sxs-lookup"><span data-stu-id="2c93d-104">AJAX clients are Web pages running JavaScript code and accessing these WCF services using HTTP requests.</span></span> <span data-ttu-id="2c93d-105">このセクションのトピックでは、このサポートと実装方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2c93d-105">The topics in this section provide information about this support and about how to implement it.</span></span>  
  
 <span data-ttu-id="2c93d-106">ASP.NET 2.0 との統合と ASP.NET AJAX の詳細については、[ASP.NET AJAX の概要](https://go.microsoft.com/fwlink/?LinkId=96725)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2c93d-106">For more information about ASP.NET AJAX and its integration with ASP.NET 2.0, see [ASP.NET AJAX Overview](https://go.microsoft.com/fwlink/?LinkId=96725).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2c93d-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="2c93d-107">In This Section</span></span>  
 [<span data-ttu-id="2c93d-108">ASP.NET AJAX 用の WCF サービスの作成</span><span class="sxs-lookup"><span data-stu-id="2c93d-108">Creating WCF Services for ASP.NET AJAX</span></span>](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md)  
 <span data-ttu-id="2c93d-109">WCF サービスを公開する方法 AJAX クライアントに構成を適切な AJAX エンドポイントを追加することで、または、サービス ホスト ファクトリを自動的に AJAX エンドポイントを構成するサービス ホストを生成するようにカスタマイズを使用して、について説明します。</span><span class="sxs-lookup"><span data-stu-id="2c93d-109">Describes how an WCF service can be exposed to AJAX clients by adding the appropriate AJAX endpoint either through configuration or by using a service host factory customized to generate a service host that configures the AJAX endpoint automatically.</span></span>  
  
 [<span data-ttu-id="2c93d-110">ASP.NET を使用せずに WCF AJAX サービスを作成する方法</span><span class="sxs-lookup"><span data-stu-id="2c93d-110">Creating WCF AJAX Services without ASP.NET</span></span>](../../../../docs/framework/wcf/feature-details/creating-wcf-ajax-services-without-aspnet.md)  
 <span data-ttu-id="2c93d-111">ASP.NET を使用せずに、WCF サービスを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2c93d-111">Describes how to create an WCF service without using ASP.NET.</span></span>  
  
 [<span data-ttu-id="2c93d-112">JSON などのデータ転送形式のサポート</span><span class="sxs-lookup"><span data-stu-id="2c93d-112">Support for JSON and Other Data Transfer Formats</span></span>](../../../../docs/framework/wcf/feature-details/support-for-json-and-other-data-transfer-formats.md)  
 <span data-ttu-id="2c93d-113">ASP.NET AJAX サービスとのメッセージングで、XML の代わりに一般に使用される JSON 形式のサポートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="2c93d-113">Describes the support of the JSON format typically used (instead of XML) for messaging with ASP.NET AJAX services.</span></span>  
  
 [<span data-ttu-id="2c93d-114">方法: AJAX 対応 ASP.NET Web サービスを WCF に移行します。</span><span class="sxs-lookup"><span data-stu-id="2c93d-114">How to: Migrate AJAX-Enabled ASP.NET Web Services to WCF</span></span>](../../../../docs/framework/wcf/feature-details/how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf.md)  
 <span data-ttu-id="2c93d-115">WCF Web サービスに AJAX 対応 ASP.NET Web サービスを移行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2c93d-115">Describes how to migrate an AJAX-enabled ASP.NET Web service to a WCF Web service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c93d-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="2c93d-116">See also</span></span>
- <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>
- [<span data-ttu-id="2c93d-117">WCF Web HTTP プログラミング モデル</span><span class="sxs-lookup"><span data-stu-id="2c93d-117">WCF Web HTTP Programming Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
