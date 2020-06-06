---
title: <webHttpEndpoint>
ms.date: 03/30/2017
ms.assetid: ecaaeb6f-ebd0-411d-8b53-92477cd45347
ms.openlocfilehash: 8d4f55fd5b51ea77839b7fdbb930e937f5700417
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70854801"
---
# \<webHttpEndpoint>
<span data-ttu-id="baa0e-101">この構成要素は、 [\<webHttpBinding>](webhttpbinding.md) 動作を自動的に追加する固定バインドを持つ標準エンドポイントを定義し [\<webHttp>](webhttp.md) ます。</span><span class="sxs-lookup"><span data-stu-id="baa0e-101">This configuration element defines a standard endpoint with a fixed [\<webHttpBinding>](webhttpbinding.md) binding that automatically adds the [\<webHttp>](webhttp.md) behavior.</span></span> <span data-ttu-id="baa0e-102">このエンドポイントは、REST サービスを作成する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="baa0e-102">Use this endpoint when writing a REST service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<webHttpEndpoint>**  
  
## <a name="syntax"></a><span data-ttu-id="baa0e-103">構文</span><span class="sxs-lookup"><span data-stu-id="baa0e-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="baa0e-104">属性および要素</span><span class="sxs-lookup"><span data-stu-id="baa0e-104">Attributes and Elements</span></span>  
 <span data-ttu-id="baa0e-105">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="baa0e-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="baa0e-106">属性</span><span class="sxs-lookup"><span data-stu-id="baa0e-106">Attributes</span></span>  
  
|<span data-ttu-id="baa0e-107">属性</span><span class="sxs-lookup"><span data-stu-id="baa0e-107">Attribute</span></span>|<span data-ttu-id="baa0e-108">説明</span><span class="sxs-lookup"><span data-stu-id="baa0e-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="baa0e-109">automaticFormatSelectionEnabled</span><span class="sxs-lookup"><span data-stu-id="baa0e-109">automaticFormatSelectionEnabled</span></span>|<span data-ttu-id="baa0e-110">形式の自動選択が有効かどうかを示すブール値。</span><span class="sxs-lookup"><span data-stu-id="baa0e-110">A Boolean value that indicates whether automatic format selection is enabled.</span></span><br /><br /> <span data-ttu-id="baa0e-111">形式の自動選択が有効な場合、インフラストラクチャが要求メッセージの `Accept` ヘッダーを解析し、最適な応答形式を判断します。</span><span class="sxs-lookup"><span data-stu-id="baa0e-111">When automatic format selection is enabled, the infrastructure parses the `Accept` header of the request message and determines the most appropriate response format.</span></span> <span data-ttu-id="baa0e-112">適切な応答形式が `Accept` ヘッダーに指定されていなかった場合は、要求メッセージの `Content-Type` または操作の既定の応答形式がインフラストラクチャによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="baa0e-112">If the `Accept` header does not specify a suitable response format, the infrastructure uses the `Content-Type` of the request message or the default response format of the operation.</span></span>|  
|<span data-ttu-id="baa0e-113">defaultOutgoingResponseFormat</span><span class="sxs-lookup"><span data-stu-id="baa0e-113">defaultOutgoingResponseFormat</span></span>|<span data-ttu-id="baa0e-114">既定の送信応答形式を指定する属性。</span><span class="sxs-lookup"><span data-stu-id="baa0e-114">An attribute that specifies the default outgoing response format.</span></span> <span data-ttu-id="baa0e-115">この属性は <xref:System.ServiceModel.Web.WebMessageFormat> 型です。</span><span class="sxs-lookup"><span data-stu-id="baa0e-115">This attribute is of the <xref:System.ServiceModel.Web.WebMessageFormat> type</span></span>|  
|<span data-ttu-id="baa0e-116">helpEnabled</span><span class="sxs-lookup"><span data-stu-id="baa0e-116">helpEnabled</span></span>|<span data-ttu-id="baa0e-117">エンドポイントに対して HTTP ヘルプ ページが有効になっているかどうかを示すブール値。</span><span class="sxs-lookup"><span data-stu-id="baa0e-117">A Boolean value that indicates whether the HTTP help page is enabled for the endpoint.</span></span>|  
|<span data-ttu-id="baa0e-118">webEndpointType</span><span class="sxs-lookup"><span data-stu-id="baa0e-118">webEndpointType</span></span>|<span data-ttu-id="baa0e-119">エンドポイントの種類を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="baa0e-119">A string that specifies the type of the endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="baa0e-120">子要素</span><span class="sxs-lookup"><span data-stu-id="baa0e-120">Child Elements</span></span>  
 <span data-ttu-id="baa0e-121">なし。</span><span class="sxs-lookup"><span data-stu-id="baa0e-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="baa0e-122">親要素</span><span class="sxs-lookup"><span data-stu-id="baa0e-122">Parent Elements</span></span>  
  
|<span data-ttu-id="baa0e-123">要素</span><span class="sxs-lookup"><span data-stu-id="baa0e-123">Element</span></span>|<span data-ttu-id="baa0e-124">Description</span><span class="sxs-lookup"><span data-stu-id="baa0e-124">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="baa0e-125">1 つ以上のプロパティ (アドレス、バインディング、コントラクト) が固定されている、あらかじめ定義されたエンドポイントである標準エンドポイントのコレクション。</span><span class="sxs-lookup"><span data-stu-id="baa0e-125">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="baa0e-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="baa0e-126">See also</span></span>

- <xref:System.ServiceModel.Description.WebHttpEndpoint>
- <xref:System.ServiceModel.Configuration.WebHttpEndpointElement>
