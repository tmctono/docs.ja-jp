---
title: <webHttpEndpoint>
ms.date: 03/30/2017
ms.assetid: ecaaeb6f-ebd0-411d-8b53-92477cd45347
ms.openlocfilehash: 8d4f55fd5b51ea77839b7fdbb930e937f5700417
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854801"
---
# <a name="webhttpendpoint"></a><span data-ttu-id="8e619-101">\<webHttpEndpoint ></span><span class="sxs-lookup"><span data-stu-id="8e619-101">\<webHttpEndpoint></span></span>
<span data-ttu-id="8e619-102">この構成要素は、 [ \<webhttp >](webhttp.md)動作を自動的に追加する固定[ \<の webHttpBinding >](webhttpbinding.md)バインドを持つ標準エンドポイントを定義します。</span><span class="sxs-lookup"><span data-stu-id="8e619-102">This configuration element defines a standard endpoint with a fixed [\<webHttpBinding>](webhttpbinding.md) binding that automatically adds the [\<webHttp>](webhttp.md) behavior.</span></span> <span data-ttu-id="8e619-103">このエンドポイントは、REST サービスを作成する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="8e619-103">Use this endpoint when writing a REST service.</span></span>  
  
<span data-ttu-id="8e619-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="8e619-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="8e619-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="8e619-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="8e619-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<standardEndpoints >** ](standardendpoints.md)</span><span class="sxs-lookup"><span data-stu-id="8e619-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)</span></span>\
<span data-ttu-id="8e619-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<webHttpEndpoint >**</span><span class="sxs-lookup"><span data-stu-id="8e619-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<webHttpEndpoint>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e619-108">構文</span><span class="sxs-lookup"><span data-stu-id="8e619-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8e619-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="8e619-109">Attributes and Elements</span></span>  
 <span data-ttu-id="8e619-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="8e619-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8e619-111">属性</span><span class="sxs-lookup"><span data-stu-id="8e619-111">Attributes</span></span>  
  
|<span data-ttu-id="8e619-112">属性</span><span class="sxs-lookup"><span data-stu-id="8e619-112">Attribute</span></span>|<span data-ttu-id="8e619-113">説明</span><span class="sxs-lookup"><span data-stu-id="8e619-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8e619-114">automaticFormatSelectionEnabled</span><span class="sxs-lookup"><span data-stu-id="8e619-114">automaticFormatSelectionEnabled</span></span>|<span data-ttu-id="8e619-115">形式の自動選択が有効かどうかを示すブール値。</span><span class="sxs-lookup"><span data-stu-id="8e619-115">A Boolean value that indicates whether automatic format selection is enabled.</span></span><br /><br /> <span data-ttu-id="8e619-116">形式の自動選択が有効な場合、インフラストラクチャが要求メッセージの `Accept` ヘッダーを解析し、最適な応答形式を判断します。</span><span class="sxs-lookup"><span data-stu-id="8e619-116">When automatic format selection is enabled, the infrastructure parses the `Accept` header of the request message and determines the most appropriate response format.</span></span> <span data-ttu-id="8e619-117">適切な応答形式が `Accept` ヘッダーに指定されていなかった場合は、要求メッセージの `Content-Type` または操作の既定の応答形式がインフラストラクチャによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="8e619-117">If the `Accept` header does not specify a suitable response format, the infrastructure uses the `Content-Type` of the request message or the default response format of the operation.</span></span>|  
|<span data-ttu-id="8e619-118">defaultOutgoingResponseFormat</span><span class="sxs-lookup"><span data-stu-id="8e619-118">defaultOutgoingResponseFormat</span></span>|<span data-ttu-id="8e619-119">既定の送信応答形式を指定する属性。</span><span class="sxs-lookup"><span data-stu-id="8e619-119">An attribute that specifies the default outgoing response format.</span></span> <span data-ttu-id="8e619-120">この属性は <xref:System.ServiceModel.Web.WebMessageFormat> 型です。</span><span class="sxs-lookup"><span data-stu-id="8e619-120">This attribute is of the <xref:System.ServiceModel.Web.WebMessageFormat> type</span></span>|  
|<span data-ttu-id="8e619-121">helpEnabled</span><span class="sxs-lookup"><span data-stu-id="8e619-121">helpEnabled</span></span>|<span data-ttu-id="8e619-122">エンドポイントに対して HTTP ヘルプ ページが有効になっているかどうかを示すブール値。</span><span class="sxs-lookup"><span data-stu-id="8e619-122">A Boolean value that indicates whether the HTTP help page is enabled for the endpoint.</span></span>|  
|<span data-ttu-id="8e619-123">webEndpointType</span><span class="sxs-lookup"><span data-stu-id="8e619-123">webEndpointType</span></span>|<span data-ttu-id="8e619-124">エンドポイントの種類を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="8e619-124">A string that specifies the type of the endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8e619-125">子要素</span><span class="sxs-lookup"><span data-stu-id="8e619-125">Child Elements</span></span>  
 <span data-ttu-id="8e619-126">なし。</span><span class="sxs-lookup"><span data-stu-id="8e619-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8e619-127">親要素</span><span class="sxs-lookup"><span data-stu-id="8e619-127">Parent Elements</span></span>  
  
|<span data-ttu-id="8e619-128">要素</span><span class="sxs-lookup"><span data-stu-id="8e619-128">Element</span></span>|<span data-ttu-id="8e619-129">説明</span><span class="sxs-lookup"><span data-stu-id="8e619-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8e619-130">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="8e619-130">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="8e619-131">1 つ以上のプロパティ (アドレス、バインディング、コントラクト) が固定されている、あらかじめ定義されたエンドポイントである標準エンドポイントのコレクション。</span><span class="sxs-lookup"><span data-stu-id="8e619-131">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8e619-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="8e619-132">See also</span></span>

- <xref:System.ServiceModel.Description.WebHttpEndpoint>
- <xref:System.ServiceModel.Configuration.WebHttpEndpointElement>
