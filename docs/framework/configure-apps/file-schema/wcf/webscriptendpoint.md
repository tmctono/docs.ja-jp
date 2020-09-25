---
title: <webScriptEndpoint>
ms.date: 03/30/2017
ms.assetid: 85cb5ecf-351b-45f3-aa29-aa2e4b64bcdd
ms.openlocfilehash: 5e3ca9c4a43432d7f5da6d8816b6a2b984851050
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177841"
---
# \<webScriptEndpoint>

<span data-ttu-id="f1055-101">この構成要素は、 [\<webHttpBinding>](webhttpbinding.md) 動作を自動的に追加する固定バインドを持つ標準エンドポイントを定義し [\<enableWebScript>](enablewebscript.md) ます。</span><span class="sxs-lookup"><span data-stu-id="f1055-101">This configuration element defines a standard endpoint with a fixed [\<webHttpBinding>](webhttpbinding.md) binding that automatically adds the [\<enableWebScript>](enablewebscript.md) behavior.</span></span> <span data-ttu-id="f1055-102">このエンドポイントは、ASP.NET AJAX アプリケーションから呼び出されるサービスを作成する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="f1055-102">Use this endpoint when you are writing a service that is called from an ASP.NET AJAX application.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<webScriptEndpoint>**  
  
## <a name="syntax"></a><span data-ttu-id="f1055-103">構文</span><span class="sxs-lookup"><span data-stu-id="f1055-103">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <webScriptEndpoint>
      <standardEndpoint webEndpointType="String" />
    </webScriptEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f1055-104">属性および要素</span><span class="sxs-lookup"><span data-stu-id="f1055-104">Attributes and Elements</span></span>  

 <span data-ttu-id="f1055-105">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="f1055-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f1055-106">属性</span><span class="sxs-lookup"><span data-stu-id="f1055-106">Attributes</span></span>  
  
|<span data-ttu-id="f1055-107">属性</span><span class="sxs-lookup"><span data-stu-id="f1055-107">Attribute</span></span>|<span data-ttu-id="f1055-108">[説明]</span><span class="sxs-lookup"><span data-stu-id="f1055-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f1055-109">webEndpointType</span><span class="sxs-lookup"><span data-stu-id="f1055-109">webEndpointType</span></span>|<span data-ttu-id="f1055-110">エンドポイントの種類を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="f1055-110">A string that specifies the type of the endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f1055-111">子要素</span><span class="sxs-lookup"><span data-stu-id="f1055-111">Child Elements</span></span>  

 <span data-ttu-id="f1055-112">なし。</span><span class="sxs-lookup"><span data-stu-id="f1055-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f1055-113">親要素</span><span class="sxs-lookup"><span data-stu-id="f1055-113">Parent Elements</span></span>  
  
|<span data-ttu-id="f1055-114">要素</span><span class="sxs-lookup"><span data-stu-id="f1055-114">Element</span></span>|<span data-ttu-id="f1055-115">説明</span><span class="sxs-lookup"><span data-stu-id="f1055-115">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="f1055-116">1 つ以上のプロパティ (アドレス、バインディング、コントラクト) が固定されている、あらかじめ定義されたエンドポイントである標準エンドポイントのコレクション。</span><span class="sxs-lookup"><span data-stu-id="f1055-116">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f1055-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="f1055-117">See also</span></span>

- <xref:System.ServiceModel.Description.WebScriptEndpoint>
- <xref:System.ServiceModel.Configuration.WebScriptEndpointElement>
