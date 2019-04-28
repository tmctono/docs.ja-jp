---
title: <webHttpEndpoint>
ms.date: 03/30/2017
ms.assetid: ecaaeb6f-ebd0-411d-8b53-92477cd45347
ms.openlocfilehash: 6fb31fca6ac38f6cb92ef087cc277a4d5066521c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61769773"
---
# <a name="webhttpendpoint"></a><span data-ttu-id="9df6c-101">\<webHttpEndpoint></span><span class="sxs-lookup"><span data-stu-id="9df6c-101">\<webHttpEndpoint></span></span>
<span data-ttu-id="9df6c-102">この構成要素は、固定の標準エンドポイントを定義します。 [ \<webHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md)を自動的にバインドを追加、 [ \<webHttp >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md)動作します。</span><span class="sxs-lookup"><span data-stu-id="9df6c-102">This configuration element defines a standard endpoint with a fixed [\<webHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) binding that automatically adds the [\<webHttp>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md) behavior.</span></span> <span data-ttu-id="9df6c-103">このエンドポイントは、REST サービスを作成する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="9df6c-103">Use this endpoint when writing a REST service.</span></span>  
  
<span data-ttu-id="9df6c-104">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="9df6c-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="9df6c-105">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="9df6c-105">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9df6c-106">構文</span><span class="sxs-lookup"><span data-stu-id="9df6c-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <webHttpEndpoint>
      <standardEndpoint automaticFormatSelectionEnabled="String"
                        defaultOutgoingResponseFormat="Xml/Json"
                        helpEnabled="Boolean"
                        webEndpointType="String" />
    </webHttpEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9df6c-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="9df6c-107">Attributes and Elements</span></span>  
 <span data-ttu-id="9df6c-108">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="9df6c-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9df6c-109">属性</span><span class="sxs-lookup"><span data-stu-id="9df6c-109">Attributes</span></span>  
  
|<span data-ttu-id="9df6c-110">属性</span><span class="sxs-lookup"><span data-stu-id="9df6c-110">Attribute</span></span>|<span data-ttu-id="9df6c-111">説明</span><span class="sxs-lookup"><span data-stu-id="9df6c-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9df6c-112">automaticFormatSelectionEnabled</span><span class="sxs-lookup"><span data-stu-id="9df6c-112">automaticFormatSelectionEnabled</span></span>|<span data-ttu-id="9df6c-113">形式の自動選択が有効かどうかを示すブール値。</span><span class="sxs-lookup"><span data-stu-id="9df6c-113">A Boolean value that indicates whether automatic format selection is enabled.</span></span><br /><br /> <span data-ttu-id="9df6c-114">形式の自動選択が有効な場合、インフラストラクチャが要求メッセージの `Accept` ヘッダーを解析し、最適な応答形式を判断します。</span><span class="sxs-lookup"><span data-stu-id="9df6c-114">When automatic format selection is enabled, the infrastructure parses the `Accept` header of the request message and determines the most appropriate response format.</span></span> <span data-ttu-id="9df6c-115">適切な応答形式が `Accept` ヘッダーに指定されていなかった場合は、要求メッセージの `Content-Type` または操作の既定の応答形式がインフラストラクチャによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="9df6c-115">If the `Accept` header does not specify a suitable response format, the infrastructure uses the `Content-Type` of the request message or the default response format of the operation.</span></span>|  
|<span data-ttu-id="9df6c-116">defaultOutgoingResponseFormat</span><span class="sxs-lookup"><span data-stu-id="9df6c-116">defaultOutgoingResponseFormat</span></span>|<span data-ttu-id="9df6c-117">既定の送信応答形式を指定する属性。</span><span class="sxs-lookup"><span data-stu-id="9df6c-117">An attribute that specifies the default outgoing response format.</span></span> <span data-ttu-id="9df6c-118">この属性は <xref:System.ServiceModel.Web.WebMessageFormat> 型です。</span><span class="sxs-lookup"><span data-stu-id="9df6c-118">This attribute is of the <xref:System.ServiceModel.Web.WebMessageFormat> type</span></span>|  
|<span data-ttu-id="9df6c-119">helpEnabled</span><span class="sxs-lookup"><span data-stu-id="9df6c-119">helpEnabled</span></span>|<span data-ttu-id="9df6c-120">エンドポイントに対して HTTP ヘルプ ページが有効になっているかどうかを示すブール値。</span><span class="sxs-lookup"><span data-stu-id="9df6c-120">A Boolean value that indicates whether the HTTP help page is enabled for the endpoint.</span></span>|  
|<span data-ttu-id="9df6c-121">webEndpointType</span><span class="sxs-lookup"><span data-stu-id="9df6c-121">webEndpointType</span></span>|<span data-ttu-id="9df6c-122">エンドポイントの種類を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="9df6c-122">A string that specifies the type of the endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9df6c-123">子要素</span><span class="sxs-lookup"><span data-stu-id="9df6c-123">Child Elements</span></span>  
 <span data-ttu-id="9df6c-124">なし。</span><span class="sxs-lookup"><span data-stu-id="9df6c-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9df6c-125">親要素</span><span class="sxs-lookup"><span data-stu-id="9df6c-125">Parent Elements</span></span>  
  
|<span data-ttu-id="9df6c-126">要素</span><span class="sxs-lookup"><span data-stu-id="9df6c-126">Element</span></span>|<span data-ttu-id="9df6c-127">説明</span><span class="sxs-lookup"><span data-stu-id="9df6c-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9df6c-128">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="9df6c-128">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="9df6c-129">1 つ以上のプロパティ (アドレス、バインディング、コントラクト) が固定されている、あらかじめ定義されたエンドポイントである標準エンドポイントのコレクション。</span><span class="sxs-lookup"><span data-stu-id="9df6c-129">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9df6c-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="9df6c-130">See also</span></span>

- <xref:System.ServiceModel.Description.WebHttpEndpoint>
- <xref:System.ServiceModel.Configuration.WebHttpEndpointElement>
