---
title: <webScriptEndpoint>
ms.date: 03/30/2017
ms.assetid: 85cb5ecf-351b-45f3-aa29-aa2e4b64bcdd
ms.openlocfilehash: cc69029d9830fd12df5a4070f11847fadf4c60bb
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940402"
---
# <a name="webscriptendpoint"></a><span data-ttu-id="a01cd-101">\<webScriptEndpoint ></span><span class="sxs-lookup"><span data-stu-id="a01cd-101">\<webScriptEndpoint></span></span>
<span data-ttu-id="a01cd-102">この構成要素は、 [ \<enablewebscript >](enablewebscript.md)動作を自動的に追加する固定[ \<の webHttpBinding >](webhttpbinding.md)バインドを持つ標準エンドポイントを定義します。</span><span class="sxs-lookup"><span data-stu-id="a01cd-102">This configuration element defines a standard endpoint with a fixed [\<webHttpBinding>](webhttpbinding.md) binding that automatically adds the [\<enableWebScript>](enablewebscript.md) behavior.</span></span> <span data-ttu-id="a01cd-103">このエンドポイントは、ASP.NET AJAX アプリケーションから呼び出されるサービスを作成する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="a01cd-103">Use this endpoint when you are writing a service that is called from an ASP.NET AJAX application.</span></span>  
  
<span data-ttu-id="a01cd-104">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="a01cd-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="a01cd-105">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="a01cd-105">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a01cd-106">構文</span><span class="sxs-lookup"><span data-stu-id="a01cd-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <webScriptEndpoint>
      <standardEndpoint webEndpointType="String" />
    </webScriptEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a01cd-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="a01cd-107">Attributes and Elements</span></span>  
 <span data-ttu-id="a01cd-108">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="a01cd-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a01cd-109">属性</span><span class="sxs-lookup"><span data-stu-id="a01cd-109">Attributes</span></span>  
  
|<span data-ttu-id="a01cd-110">属性</span><span class="sxs-lookup"><span data-stu-id="a01cd-110">Attribute</span></span>|<span data-ttu-id="a01cd-111">説明</span><span class="sxs-lookup"><span data-stu-id="a01cd-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a01cd-112">webEndpointType</span><span class="sxs-lookup"><span data-stu-id="a01cd-112">webEndpointType</span></span>|<span data-ttu-id="a01cd-113">エンドポイントの種類を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="a01cd-113">A string that specifies the type of the endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a01cd-114">子要素</span><span class="sxs-lookup"><span data-stu-id="a01cd-114">Child Elements</span></span>  
 <span data-ttu-id="a01cd-115">なし。</span><span class="sxs-lookup"><span data-stu-id="a01cd-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a01cd-116">親要素</span><span class="sxs-lookup"><span data-stu-id="a01cd-116">Parent Elements</span></span>  
  
|<span data-ttu-id="a01cd-117">要素</span><span class="sxs-lookup"><span data-stu-id="a01cd-117">Element</span></span>|<span data-ttu-id="a01cd-118">説明</span><span class="sxs-lookup"><span data-stu-id="a01cd-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a01cd-119">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="a01cd-119">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="a01cd-120">1 つ以上のプロパティ (アドレス、バインディング、コントラクト) が固定されている、あらかじめ定義されたエンドポイントである標準エンドポイントのコレクション。</span><span class="sxs-lookup"><span data-stu-id="a01cd-120">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a01cd-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="a01cd-121">See also</span></span>

- <xref:System.ServiceModel.Description.WebScriptEndpoint>
- <xref:System.ServiceModel.Configuration.WebScriptEndpointElement>
