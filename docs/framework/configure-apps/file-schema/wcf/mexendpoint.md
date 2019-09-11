---
title: <mexEndpoint>
ms.date: 03/30/2017
ms.assetid: c9823060-0a5d-4f9d-99d4-4d113b758247
ms.openlocfilehash: 7760ee4d3b118e339944317e8ec8d8217b5d909d
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855113"
---
# <a name="mexendpoint"></a><span data-ttu-id="f0c6d-101">\<mexEndpoint ></span><span class="sxs-lookup"><span data-stu-id="f0c6d-101">\<mexEndpoint></span></span>
<span data-ttu-id="f0c6d-102">この構成要素は、固定 IMetadataExchange コントラクトが含まれた標準エンドポイントを定義します。</span><span class="sxs-lookup"><span data-stu-id="f0c6d-102">This configuration element defines a standard endpoint with a fixed IMetadataExchange contract.</span></span> <span data-ttu-id="f0c6d-103">IMetadataExchange はすべてのメタデータ交換エンドポイントでコントラクトとして指定されるため、独自のエンドポイントを定義せずにこの標準エンドポイントを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f0c6d-103">Since all metadata exchange endpoints specify IMetadataExchange as their contract, you can use this standard point instead of defining one for yourself.</span></span>  
  
<span data-ttu-id="f0c6d-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f0c6d-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f0c6d-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="f0c6d-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="f0c6d-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<standardEndpoints >** ](standardendpoints.md)</span><span class="sxs-lookup"><span data-stu-id="f0c6d-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)</span></span>\
<span data-ttu-id="f0c6d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<mexEndpoint >**</span><span class="sxs-lookup"><span data-stu-id="f0c6d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<mexEndpoint>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0c6d-108">構文</span><span class="sxs-lookup"><span data-stu-id="f0c6d-108">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <mexEndpoint>
      <standardEndpoint name="String" />
    </mexEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f0c6d-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="f0c6d-109">Attributes and Elements</span></span>  
 <span data-ttu-id="f0c6d-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="f0c6d-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f0c6d-111">属性</span><span class="sxs-lookup"><span data-stu-id="f0c6d-111">Attributes</span></span>  
  
|<span data-ttu-id="f0c6d-112">属性</span><span class="sxs-lookup"><span data-stu-id="f0c6d-112">Attribute</span></span>|<span data-ttu-id="f0c6d-113">説明</span><span class="sxs-lookup"><span data-stu-id="f0c6d-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f0c6d-114">name</span><span class="sxs-lookup"><span data-stu-id="f0c6d-114">name</span></span>|<span data-ttu-id="f0c6d-115">標準エンドポイントの構成名を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="f0c6d-115">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="f0c6d-116">この名前は、サービス エンドポイントの `endpointConfiguration` 属性で使用され、標準エンドポイントと構成を関連付けます。</span><span class="sxs-lookup"><span data-stu-id="f0c6d-116">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f0c6d-117">子要素</span><span class="sxs-lookup"><span data-stu-id="f0c6d-117">Child Elements</span></span>  
 <span data-ttu-id="f0c6d-118">なし。</span><span class="sxs-lookup"><span data-stu-id="f0c6d-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f0c6d-119">親要素</span><span class="sxs-lookup"><span data-stu-id="f0c6d-119">Parent Elements</span></span>  
  
|<span data-ttu-id="f0c6d-120">要素</span><span class="sxs-lookup"><span data-stu-id="f0c6d-120">Element</span></span>|<span data-ttu-id="f0c6d-121">説明</span><span class="sxs-lookup"><span data-stu-id="f0c6d-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f0c6d-122">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="f0c6d-122">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="f0c6d-123">1 つ以上のプロパティ (アドレス、バインディング、コントラクト) が固定されている、あらかじめ定義されたエンドポイントである標準エンドポイントのコレクション。</span><span class="sxs-lookup"><span data-stu-id="f0c6d-123">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|
