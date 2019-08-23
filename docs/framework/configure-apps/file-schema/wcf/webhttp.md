---
title: <webHttp>
ms.date: 03/30/2017
ms.assetid: 1f9d0754-d41e-44ce-a298-e51cb3096c64
ms.openlocfilehash: 366def5d0f4cc82b0ff0a5127701b0b5a6adb6a0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940505"
---
# <a name="webhttp"></a><span data-ttu-id="7f10c-101">\<webHttp ></span><span class="sxs-lookup"><span data-stu-id="7f10c-101">\<webHttp></span></span>
<span data-ttu-id="7f10c-102">この要素は、構成によってエンドポイントに <xref:System.ServiceModel.Description.WebHttpBehavior> を指定します。</span><span class="sxs-lookup"><span data-stu-id="7f10c-102">This element specifies the <xref:System.ServiceModel.Description.WebHttpBehavior> on an endpoint through configuration.</span></span> <span data-ttu-id="7f10c-103">この動作は、 [ \<webHttpBinding >](webhttpbinding.md)の標準バインディングと組み合わせて使用すると、Windows Communication Foundation (WCF) サービスの Web プログラミングモデルを有効にします。</span><span class="sxs-lookup"><span data-stu-id="7f10c-103">This behavior, when used in conjunction with the [\<webHttpBinding>](webhttpbinding.md) standard binding, enables the Web programming model for a Windows Communication Foundation (WCF) service.</span></span>  
  
 <span data-ttu-id="7f10c-104">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="7f10c-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="7f10c-105">\<<behaviors></span><span class="sxs-lookup"><span data-stu-id="7f10c-105">\<behaviors></span></span>  
<span data-ttu-id="7f10c-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="7f10c-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="7f10c-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="7f10c-107">\<behavior></span></span>  
<span data-ttu-id="7f10c-108">\<webHttp ></span><span class="sxs-lookup"><span data-stu-id="7f10c-108">\<webHttp></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f10c-109">構文</span><span class="sxs-lookup"><span data-stu-id="7f10c-109">Syntax</span></span>  
  
```xml  
<webHttp />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7f10c-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="7f10c-110">Attributes and Elements</span></span>  
 <span data-ttu-id="7f10c-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="7f10c-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7f10c-112">属性</span><span class="sxs-lookup"><span data-stu-id="7f10c-112">Attributes</span></span>  
  
|<span data-ttu-id="7f10c-113">属性</span><span class="sxs-lookup"><span data-stu-id="7f10c-113">Attribute</span></span>|<span data-ttu-id="7f10c-114">説明</span><span class="sxs-lookup"><span data-stu-id="7f10c-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7f10c-115">automaticFormatSelectionEnabled</span><span class="sxs-lookup"><span data-stu-id="7f10c-115">automaticFormatSelectionEnabled</span></span>|<span data-ttu-id="7f10c-116">このプロパティが `true` に設定されている場合は、使用する最適な形式が WCF インフラストラクチャで決定されます。</span><span class="sxs-lookup"><span data-stu-id="7f10c-116">When this property is set to `true`, the WCF infrastructure determines the best format to use.</span></span> <span data-ttu-id="7f10c-117">形式の自動選択は、既定で、下位互換性のために無効になっています。</span><span class="sxs-lookup"><span data-stu-id="7f10c-117">Automatic format selection is disabled by default for backwards compatibility.</span></span> <span data-ttu-id="7f10c-118">形式の自動選択は、プログラムで有効にすることも、構成ファイルを使用して有効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="7f10c-118">Automatic format selection can be enabled programmatically or through configuration.</span></span>|  
|<span data-ttu-id="7f10c-119">defaultBodyStyle</span><span class="sxs-lookup"><span data-stu-id="7f10c-119">defaultBodyStyle</span></span>|<span data-ttu-id="7f10c-120">返されたメッセージの既定の本文のスタイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="7f10c-120">Specifies the default body style of returned messages.</span></span> <span data-ttu-id="7f10c-121">詳細については<xref:System.ServiceModel.Web.WebMessageBodyStyle> 、「」および「 [WCF Web HTTP 書式設定](../../../wcf/feature-details/wcf-web-http-formatting.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7f10c-121">For more information, see <xref:System.ServiceModel.Web.WebMessageBodyStyle> and [WCF Web HTTP Formatting](../../../wcf/feature-details/wcf-web-http-formatting.md).</span></span>|  
|<span data-ttu-id="7f10c-122">defaultOutgoingResponseFormat</span><span class="sxs-lookup"><span data-stu-id="7f10c-122">defaultOutgoingResponseFormat</span></span>|<span data-ttu-id="7f10c-123">メッセージの既定の送信応答形式を指定します。</span><span class="sxs-lookup"><span data-stu-id="7f10c-123">Specifies the default outgoing response format for messages.</span></span> <span data-ttu-id="7f10c-124">詳細については、「 [WCF WEB HTTP 書式設定](../../../wcf/feature-details/wcf-web-http-formatting.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7f10c-124">For more information, see [WCF Web HTTP Formatting](../../../wcf/feature-details/wcf-web-http-formatting.md).</span></span>|  
|<span data-ttu-id="7f10c-125">faultExceptionEnabled</span><span class="sxs-lookup"><span data-stu-id="7f10c-125">faultExceptionEnabled</span></span>|<span data-ttu-id="7f10c-126">内部サーバー エラー (HTTP ステータス コード: 500) が発生したときに FaultException が生成されるかどうかを指定するフラグを取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="7f10c-126">Gets or sets the flag that specifies whether a FaultException is generated when an internal server error (HTTP status code: 500) occurs.</span></span>|  
|<span data-ttu-id="7f10c-127">helpEnabled</span><span class="sxs-lookup"><span data-stu-id="7f10c-127">helpEnabled</span></span>|<span data-ttu-id="7f10c-128">ヘルプ ページが有効かどうかを示す値を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="7f10c-128">Gets or sets a value that determines if the Help page is enabled.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7f10c-129">子要素</span><span class="sxs-lookup"><span data-stu-id="7f10c-129">Child Elements</span></span>  
 <span data-ttu-id="7f10c-130">なし。</span><span class="sxs-lookup"><span data-stu-id="7f10c-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7f10c-131">親要素</span><span class="sxs-lookup"><span data-stu-id="7f10c-131">Parent Elements</span></span>  
  
|<span data-ttu-id="7f10c-132">要素</span><span class="sxs-lookup"><span data-stu-id="7f10c-132">Element</span></span>|<span data-ttu-id="7f10c-133">説明</span><span class="sxs-lookup"><span data-stu-id="7f10c-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7f10c-134">\<behavior></span><span class="sxs-lookup"><span data-stu-id="7f10c-134">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="7f10c-135">エンドポイントの動作のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="7f10c-135">Specifies the set of endpoint behaviors.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7f10c-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="7f10c-136">See also</span></span>

- <xref:System.ServiceModel.Configuration.WebHttpElement>
- <xref:System.ServiceModel.Description.WebHttpBehavior>
- [<span data-ttu-id="7f10c-137">AJAX の統合と JSON のサポート</span><span class="sxs-lookup"><span data-stu-id="7f10c-137">AJAX Integration and JSON Support</span></span>](../../../wcf/feature-details/ajax-integration-and-json-support.md)
- [<span data-ttu-id="7f10c-138">\<webHttpBinding></span><span class="sxs-lookup"><span data-stu-id="7f10c-138">\<webHttpBinding></span></span>](webhttpbinding.md)
