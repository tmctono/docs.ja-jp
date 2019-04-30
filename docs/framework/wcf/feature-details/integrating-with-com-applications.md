---
title: COM アプリケーションとの統合
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation, COM integration
- COM [WCF], Windows Communication Foundation integration
- WCF, reusing code
- Windows Communication Foundation, reusing code
- COM [WCF]
- WCF, COM integration
ms.assetid: c98bda3e-6779-419e-8e6d-9aa94053026d
ms.openlocfilehash: 51626da6e97e346f43cfe606a5164024580a2ac7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62046997"
---
# <a name="integrating-with-com-applications"></a><span data-ttu-id="e1817-102">COM アプリケーションとの統合</span><span class="sxs-lookup"><span data-stu-id="e1817-102">Integrating with COM Applications</span></span>
<span data-ttu-id="e1817-103">Windows Communication Foundation (WCF) サービスは、WCF サービス モニカーを使用して、既存のコードに直接統合できます。</span><span class="sxs-lookup"><span data-stu-id="e1817-103">Windows Communication Foundation (WCF) services can be integrated directly into your existing code by using the WCF service moniker.</span></span> <span data-ttu-id="e1817-104">サービス モニカーは Office VBA、Visual Basic 6.0、または Visual C++ 6.0 などの幅広い COM ベースの開発環境で使用可能です。</span><span class="sxs-lookup"><span data-stu-id="e1817-104">The service moniker can be used from a wide range of COM-based development environments, such as Office VBA, Visual Basic 6.0, or Visual C++ 6.0.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e1817-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="e1817-105">In This Section</span></span>  
 [<span data-ttu-id="e1817-106">COM アプリケーションとの統合の概要</span><span class="sxs-lookup"><span data-stu-id="e1817-106">Integrating with COM Applications Overview</span></span>](../../../../docs/framework/wcf/feature-details/integrating-with-com-applications-overview.md)  
 <span data-ttu-id="e1817-107">統合プロセスの主要部分の概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="e1817-107">Gives an overview of the major parts of the integration process.</span></span>  
  
 [<span data-ttu-id="e1817-108">方法: 登録し、サービス モニカーの構成</span><span class="sxs-lookup"><span data-stu-id="e1817-108">How to: Register and Configure a Service Moniker</span></span>](../../../../docs/framework/wcf/feature-details/how-to-register-and-configure-a-service-moniker.md)  
 <span data-ttu-id="e1817-109">COM アプリケーション内で WCF サービス モニカーを使用するを COM に必要な属性型を登録し、必要なバインド構成で、COM アプリケーションとモニカーを構成します。</span><span class="sxs-lookup"><span data-stu-id="e1817-109">To use the WCF service moniker within a COM application, register the required attributed types with COM, and configure the COM application and the moniker with the required binding configuration.</span></span>  
  
 [<span data-ttu-id="e1817-110">方法: 登録しないと、Windows Communication Foundation サービス モニカーを使用して、</span><span class="sxs-lookup"><span data-stu-id="e1817-110">How to: Use the Windows Communication Foundation Service Moniker without Registration</span></span>](../../../../docs/framework/wcf/feature-details/use-the-wcf-service-moniker-without-registration.md)  
 <span data-ttu-id="e1817-111">WSDL (Web Services Definition Language) ドキュメントの形式で、または WS-MetadataExchange エンドポイントからコントラクトの定義を取得する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="e1817-111">Explains how to obtain the definition of the contract in the form of a Web Services Definition Language (WSDL) document or from a WS-MetadataExchange endpoint.</span></span>  
  
 [<span data-ttu-id="e1817-112">方法: WSDL コントラクトと共にサービス モニカーを使用します。</span><span class="sxs-lookup"><span data-stu-id="e1817-112">How to: Use a Service Moniker with WSDL Contracts</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-a-service-moniker-with-wsdl-contracts.md)  
 <span data-ttu-id="e1817-113">WCF WSDL モニカーを使用して、WCF のサンプルを呼び出す方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e1817-113">Describes how to call a WCF sample using a WCF WSDL moniker.</span></span>  
  
 [<span data-ttu-id="e1817-114">方法: Metadata Exchange コントラクトと共にサービス モニカーを使用します。</span><span class="sxs-lookup"><span data-stu-id="e1817-114">How to: Use a Service Moniker with Metadata Exchange Contracts</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-a-service-moniker-with-metadata-exchange-contracts.md)  
 <span data-ttu-id="e1817-115">Mex エンドポイントを指定する WCF モニカーを使用して、WCF のサンプルを呼び出す方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e1817-115">Describes how to call a WCF sample using a WCF moniker that specifies a Mex endpoint.</span></span>  
  
 [<span data-ttu-id="e1817-116">方法: チャネルのセキュリティ資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="e1817-116">How to: Specify Channel Security Credentials</span></span>](../../../../docs/framework/wcf/feature-details/how-to-specify-channel-security-credentials.md)  
 <span data-ttu-id="e1817-117">WCF サービス モニカーのサポート、`IChannelCredentials`インターフェイスにより、さまざまなチャネル資格情報を指定するための代替方法です。</span><span class="sxs-lookup"><span data-stu-id="e1817-117">The WCF service moniker supports the `IChannelCredentials` interface that allows a range of alternate methods for specifying channel credentials.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="e1817-118">参照</span><span class="sxs-lookup"><span data-stu-id="e1817-118">Reference</span></span>  
 <xref:System.ServiceModel>  
  
## <a name="see-also"></a><span data-ttu-id="e1817-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="e1817-119">See also</span></span>

- [<span data-ttu-id="e1817-120">COM+ アプリケーションとの統合</span><span class="sxs-lookup"><span data-stu-id="e1817-120">Integrating with COM+ Applications</span></span>](../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)
