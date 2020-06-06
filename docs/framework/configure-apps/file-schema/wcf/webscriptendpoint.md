---
title: <webScriptEndpoint>
ms.date: 03/30/2017
ms.assetid: 85cb5ecf-351b-45f3-aa29-aa2e4b64bcdd
ms.openlocfilehash: b4bc33cf8ff4e703973efe7df49e9f1d2189302e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70854815"
---
# \<webScriptEndpoint>
<span data-ttu-id="8733b-101">この構成要素は、 [\<webHttpBinding>](webhttpbinding.md) 動作を自動的に追加する固定バインドを持つ標準エンドポイントを定義し [\<enableWebScript>](enablewebscript.md) ます。</span><span class="sxs-lookup"><span data-stu-id="8733b-101">This configuration element defines a standard endpoint with a fixed [\<webHttpBinding>](webhttpbinding.md) binding that automatically adds the [\<enableWebScript>](enablewebscript.md) behavior.</span></span> <span data-ttu-id="8733b-102">このエンドポイントは、ASP.NET AJAX アプリケーションから呼び出されるサービスを作成する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="8733b-102">Use this endpoint when you are writing a service that is called from an ASP.NET AJAX application.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<webScriptEndpoint>**  
  
## <a name="syntax"></a><span data-ttu-id="8733b-103">構文</span><span class="sxs-lookup"><span data-stu-id="8733b-103">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <webScriptEndpoint>
      <standardEndpoint webEndpointType="String" />
    </webScriptEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8733b-104">属性および要素</span><span class="sxs-lookup"><span data-stu-id="8733b-104">Attributes and Elements</span></span>  
 <span data-ttu-id="8733b-105">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="8733b-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8733b-106">属性</span><span class="sxs-lookup"><span data-stu-id="8733b-106">Attributes</span></span>  
  
|<span data-ttu-id="8733b-107">属性</span><span class="sxs-lookup"><span data-stu-id="8733b-107">Attribute</span></span>|<span data-ttu-id="8733b-108">説明</span><span class="sxs-lookup"><span data-stu-id="8733b-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8733b-109">webEndpointType</span><span class="sxs-lookup"><span data-stu-id="8733b-109">webEndpointType</span></span>|<span data-ttu-id="8733b-110">エンドポイントの種類を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="8733b-110">A string that specifies the type of the endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8733b-111">子要素</span><span class="sxs-lookup"><span data-stu-id="8733b-111">Child Elements</span></span>  
 <span data-ttu-id="8733b-112">なし。</span><span class="sxs-lookup"><span data-stu-id="8733b-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8733b-113">親要素</span><span class="sxs-lookup"><span data-stu-id="8733b-113">Parent Elements</span></span>  
  
|<span data-ttu-id="8733b-114">要素</span><span class="sxs-lookup"><span data-stu-id="8733b-114">Element</span></span>|<span data-ttu-id="8733b-115">Description</span><span class="sxs-lookup"><span data-stu-id="8733b-115">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="8733b-116">1 つ以上のプロパティ (アドレス、バインディング、コントラクト) が固定されている、あらかじめ定義されたエンドポイントである標準エンドポイントのコレクション。</span><span class="sxs-lookup"><span data-stu-id="8733b-116">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8733b-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="8733b-117">See also</span></span>

- <xref:System.ServiceModel.Description.WebScriptEndpoint>
- <xref:System.ServiceModel.Configuration.WebScriptEndpointElement>
