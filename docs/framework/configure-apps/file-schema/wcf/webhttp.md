---
title: <webHttp>
ms.date: 03/30/2017
ms.assetid: 1f9d0754-d41e-44ce-a298-e51cb3096c64
ms.openlocfilehash: 716d960e2d5f896976c22a60d419d9b165b36178
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91202462"
---
# \<webHttp>

<span data-ttu-id="daa6b-101">この要素は、構成によってエンドポイントに <xref:System.ServiceModel.Description.WebHttpBehavior> を指定します。</span><span class="sxs-lookup"><span data-stu-id="daa6b-101">This element specifies the <xref:System.ServiceModel.Description.WebHttpBehavior> on an endpoint through configuration.</span></span> <span data-ttu-id="daa6b-102">この動作を標準のバインディングと組み合わせて使用すると [\<webHttpBinding>](webhttpbinding.md) 、Windows Communication Foundation (WCF) サービスの Web プログラミングモデルが有効になります。</span><span class="sxs-lookup"><span data-stu-id="daa6b-102">This behavior, when used in conjunction with the [\<webHttpBinding>](webhttpbinding.md) standard binding, enables the Web programming model for a Windows Communication Foundation (WCF) service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<webHttp>**  
  
## <a name="syntax"></a><span data-ttu-id="daa6b-103">構文</span><span class="sxs-lookup"><span data-stu-id="daa6b-103">Syntax</span></span>  
  
```xml  
<webHttp />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="daa6b-104">属性および要素</span><span class="sxs-lookup"><span data-stu-id="daa6b-104">Attributes and Elements</span></span>  

 <span data-ttu-id="daa6b-105">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="daa6b-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="daa6b-106">属性</span><span class="sxs-lookup"><span data-stu-id="daa6b-106">Attributes</span></span>  
  
|<span data-ttu-id="daa6b-107">属性</span><span class="sxs-lookup"><span data-stu-id="daa6b-107">Attribute</span></span>|<span data-ttu-id="daa6b-108">[説明]</span><span class="sxs-lookup"><span data-stu-id="daa6b-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="daa6b-109">automaticFormatSelectionEnabled</span><span class="sxs-lookup"><span data-stu-id="daa6b-109">automaticFormatSelectionEnabled</span></span>|<span data-ttu-id="daa6b-110">このプロパティが `true` に設定されている場合は、使用する最適な形式が WCF インフラストラクチャで決定されます。</span><span class="sxs-lookup"><span data-stu-id="daa6b-110">When this property is set to `true`, the WCF infrastructure determines the best format to use.</span></span> <span data-ttu-id="daa6b-111">形式の自動選択は、既定で、下位互換性のために無効になっています。</span><span class="sxs-lookup"><span data-stu-id="daa6b-111">Automatic format selection is disabled by default for backwards compatibility.</span></span> <span data-ttu-id="daa6b-112">形式の自動選択は、プログラムで有効にすることも、構成ファイルを使用して有効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="daa6b-112">Automatic format selection can be enabled programmatically or through configuration.</span></span>|  
|<span data-ttu-id="daa6b-113">defaultBodyStyle</span><span class="sxs-lookup"><span data-stu-id="daa6b-113">defaultBodyStyle</span></span>|<span data-ttu-id="daa6b-114">返されたメッセージの既定の本文のスタイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="daa6b-114">Specifies the default body style of returned messages.</span></span> <span data-ttu-id="daa6b-115">詳細については、「」 <xref:System.ServiceModel.Web.WebMessageBodyStyle> および「 [WCF Web HTTP 書式設定](../../../wcf/feature-details/wcf-web-http-formatting.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="daa6b-115">For more information, see <xref:System.ServiceModel.Web.WebMessageBodyStyle> and [WCF Web HTTP Formatting](../../../wcf/feature-details/wcf-web-http-formatting.md).</span></span>|  
|<span data-ttu-id="daa6b-116">defaultOutgoingResponseFormat</span><span class="sxs-lookup"><span data-stu-id="daa6b-116">defaultOutgoingResponseFormat</span></span>|<span data-ttu-id="daa6b-117">メッセージの既定の送信応答形式を指定します。</span><span class="sxs-lookup"><span data-stu-id="daa6b-117">Specifies the default outgoing response format for messages.</span></span> <span data-ttu-id="daa6b-118">詳細については、「 [WCF WEB HTTP 書式設定](../../../wcf/feature-details/wcf-web-http-formatting.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="daa6b-118">For more information, see [WCF Web HTTP Formatting](../../../wcf/feature-details/wcf-web-http-formatting.md).</span></span>|  
|<span data-ttu-id="daa6b-119">faultExceptionEnabled</span><span class="sxs-lookup"><span data-stu-id="daa6b-119">faultExceptionEnabled</span></span>|<span data-ttu-id="daa6b-120">内部サーバー エラー (HTTP ステータス コード: 500) が発生したときに FaultException が生成されるかどうかを指定するフラグを取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="daa6b-120">Gets or sets the flag that specifies whether a FaultException is generated when an internal server error (HTTP status code: 500) occurs.</span></span>|  
|<span data-ttu-id="daa6b-121">helpEnabled</span><span class="sxs-lookup"><span data-stu-id="daa6b-121">helpEnabled</span></span>|<span data-ttu-id="daa6b-122"> ヘルプ ページが有効かどうかを示す値を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="daa6b-122">Gets or sets a value that determines if the Help page is enabled.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="daa6b-123">子要素</span><span class="sxs-lookup"><span data-stu-id="daa6b-123">Child Elements</span></span>  

 <span data-ttu-id="daa6b-124">なし。</span><span class="sxs-lookup"><span data-stu-id="daa6b-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="daa6b-125">親要素</span><span class="sxs-lookup"><span data-stu-id="daa6b-125">Parent Elements</span></span>  
  
|<span data-ttu-id="daa6b-126">要素</span><span class="sxs-lookup"><span data-stu-id="daa6b-126">Element</span></span>|<span data-ttu-id="daa6b-127">説明</span><span class="sxs-lookup"><span data-stu-id="daa6b-127">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="daa6b-128">エンドポイントの動作のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="daa6b-128">Specifies the set of endpoint behaviors.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="daa6b-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="daa6b-129">See also</span></span>

- <xref:System.ServiceModel.Configuration.WebHttpElement>
- <xref:System.ServiceModel.Description.WebHttpBehavior>
- [<span data-ttu-id="daa6b-130">AJAX の統合と JSON のサポート</span><span class="sxs-lookup"><span data-stu-id="daa6b-130">AJAX Integration and JSON Support</span></span>](../../../wcf/feature-details/ajax-integration-and-json-support.md)
- [\<webHttpBinding>](webhttpbinding.md)
