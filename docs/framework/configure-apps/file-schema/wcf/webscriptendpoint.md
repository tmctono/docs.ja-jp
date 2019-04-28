---
title: <webScriptEndpoint>
ms.date: 03/30/2017
ms.assetid: 85cb5ecf-351b-45f3-aa29-aa2e4b64bcdd
ms.openlocfilehash: 9619c27c8c6d41250eeaeccabebe611e94b7d874
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61769734"
---
# <a name="webscriptendpoint"></a><span data-ttu-id="3e4f8-101">\<webScriptEndpoint></span><span class="sxs-lookup"><span data-stu-id="3e4f8-101">\<webScriptEndpoint></span></span>
<span data-ttu-id="3e4f8-102">この構成要素は、固定の標準エンドポイントを定義します。 [ \<webHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md)を自動的にバインドを追加、 [ \<enableWebScript >](../../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md)動作します。</span><span class="sxs-lookup"><span data-stu-id="3e4f8-102">This configuration element defines a standard endpoint with a fixed [\<webHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) binding that automatically adds the [\<enableWebScript>](../../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md) behavior.</span></span> <span data-ttu-id="3e4f8-103">このエンドポイントは、ASP.NET AJAX アプリケーションから呼び出されるサービスを作成する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="3e4f8-103">Use this endpoint when you are writing a service that is called from an ASP.NET AJAX application.</span></span>  
  
<span data-ttu-id="3e4f8-104">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="3e4f8-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="3e4f8-105">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="3e4f8-105">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e4f8-106">構文</span><span class="sxs-lookup"><span data-stu-id="3e4f8-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <webScriptEndpoint>
      <standardEndpoint webEndpointType="String" />
    </webScriptEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3e4f8-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="3e4f8-107">Attributes and Elements</span></span>  
 <span data-ttu-id="3e4f8-108">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="3e4f8-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3e4f8-109">属性</span><span class="sxs-lookup"><span data-stu-id="3e4f8-109">Attributes</span></span>  
  
|<span data-ttu-id="3e4f8-110">属性</span><span class="sxs-lookup"><span data-stu-id="3e4f8-110">Attribute</span></span>|<span data-ttu-id="3e4f8-111">説明</span><span class="sxs-lookup"><span data-stu-id="3e4f8-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3e4f8-112">webEndpointType</span><span class="sxs-lookup"><span data-stu-id="3e4f8-112">webEndpointType</span></span>|<span data-ttu-id="3e4f8-113">エンドポイントの種類を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="3e4f8-113">A string that specifies the type of the endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3e4f8-114">子要素</span><span class="sxs-lookup"><span data-stu-id="3e4f8-114">Child Elements</span></span>  
 <span data-ttu-id="3e4f8-115">なし。</span><span class="sxs-lookup"><span data-stu-id="3e4f8-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3e4f8-116">親要素</span><span class="sxs-lookup"><span data-stu-id="3e4f8-116">Parent Elements</span></span>  
  
|<span data-ttu-id="3e4f8-117">要素</span><span class="sxs-lookup"><span data-stu-id="3e4f8-117">Element</span></span>|<span data-ttu-id="3e4f8-118">説明</span><span class="sxs-lookup"><span data-stu-id="3e4f8-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3e4f8-119">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="3e4f8-119">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="3e4f8-120">1 つ以上のプロパティ (アドレス、バインディング、コントラクト) が固定されている、あらかじめ定義されたエンドポイントである標準エンドポイントのコレクション。</span><span class="sxs-lookup"><span data-stu-id="3e4f8-120">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3e4f8-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="3e4f8-121">See also</span></span>

- <xref:System.ServiceModel.Description.WebScriptEndpoint>
- <xref:System.ServiceModel.Configuration.WebScriptEndpointElement>
