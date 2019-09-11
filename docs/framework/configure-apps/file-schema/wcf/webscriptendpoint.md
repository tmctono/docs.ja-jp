---
title: <webScriptEndpoint>
ms.date: 03/30/2017
ms.assetid: 85cb5ecf-351b-45f3-aa29-aa2e4b64bcdd
ms.openlocfilehash: b4bc33cf8ff4e703973efe7df49e9f1d2189302e
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854815"
---
# <a name="webscriptendpoint"></a><span data-ttu-id="17e14-101">\<webScriptEndpoint ></span><span class="sxs-lookup"><span data-stu-id="17e14-101">\<webScriptEndpoint></span></span>
<span data-ttu-id="17e14-102">この構成要素は、 [ \<enablewebscript >](enablewebscript.md)動作を自動的に追加する固定[ \<の webHttpBinding >](webhttpbinding.md)バインドを持つ標準エンドポイントを定義します。</span><span class="sxs-lookup"><span data-stu-id="17e14-102">This configuration element defines a standard endpoint with a fixed [\<webHttpBinding>](webhttpbinding.md) binding that automatically adds the [\<enableWebScript>](enablewebscript.md) behavior.</span></span> <span data-ttu-id="17e14-103">このエンドポイントは、ASP.NET AJAX アプリケーションから呼び出されるサービスを作成する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="17e14-103">Use this endpoint when you are writing a service that is called from an ASP.NET AJAX application.</span></span>  
  
<span data-ttu-id="17e14-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="17e14-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="17e14-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="17e14-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="17e14-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<standardEndpoints >** ](standardendpoints.md)</span><span class="sxs-lookup"><span data-stu-id="17e14-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)</span></span>\
<span data-ttu-id="17e14-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<webScriptEndpoint >**</span><span class="sxs-lookup"><span data-stu-id="17e14-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<webScriptEndpoint>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17e14-108">構文</span><span class="sxs-lookup"><span data-stu-id="17e14-108">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <webScriptEndpoint>
      <standardEndpoint webEndpointType="String" />
    </webScriptEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="17e14-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="17e14-109">Attributes and Elements</span></span>  
 <span data-ttu-id="17e14-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="17e14-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="17e14-111">属性</span><span class="sxs-lookup"><span data-stu-id="17e14-111">Attributes</span></span>  
  
|<span data-ttu-id="17e14-112">属性</span><span class="sxs-lookup"><span data-stu-id="17e14-112">Attribute</span></span>|<span data-ttu-id="17e14-113">説明</span><span class="sxs-lookup"><span data-stu-id="17e14-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="17e14-114">webEndpointType</span><span class="sxs-lookup"><span data-stu-id="17e14-114">webEndpointType</span></span>|<span data-ttu-id="17e14-115">エンドポイントの種類を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="17e14-115">A string that specifies the type of the endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="17e14-116">子要素</span><span class="sxs-lookup"><span data-stu-id="17e14-116">Child Elements</span></span>  
 <span data-ttu-id="17e14-117">なし。</span><span class="sxs-lookup"><span data-stu-id="17e14-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="17e14-118">親要素</span><span class="sxs-lookup"><span data-stu-id="17e14-118">Parent Elements</span></span>  
  
|<span data-ttu-id="17e14-119">要素</span><span class="sxs-lookup"><span data-stu-id="17e14-119">Element</span></span>|<span data-ttu-id="17e14-120">説明</span><span class="sxs-lookup"><span data-stu-id="17e14-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="17e14-121">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="17e14-121">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="17e14-122">1 つ以上のプロパティ (アドレス、バインディング、コントラクト) が固定されている、あらかじめ定義されたエンドポイントである標準エンドポイントのコレクション。</span><span class="sxs-lookup"><span data-stu-id="17e14-122">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="17e14-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="17e14-123">See also</span></span>

- <xref:System.ServiceModel.Description.WebScriptEndpoint>
- <xref:System.ServiceModel.Configuration.WebScriptEndpointElement>
