---
title: <mexEndpoint>
ms.date: 03/30/2017
ms.assetid: c9823060-0a5d-4f9d-99d4-4d113b758247
ms.openlocfilehash: 7760ee4d3b118e339944317e8ec8d8217b5d909d
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855113"
---
# \<mexEndpoint>
<span data-ttu-id="a61ee-101">この構成要素は、固定 IMetadataExchange コントラクトが含まれた標準エンドポイントを定義します。</span><span class="sxs-lookup"><span data-stu-id="a61ee-101">This configuration element defines a standard endpoint with a fixed IMetadataExchange contract.</span></span> <span data-ttu-id="a61ee-102">IMetadataExchange はすべてのメタデータ交換エンドポイントでコントラクトとして指定されるため、独自のエンドポイントを定義せずにこの標準エンドポイントを使用できます。</span><span class="sxs-lookup"><span data-stu-id="a61ee-102">Since all metadata exchange endpoints specify IMetadataExchange as their contract, you can use this standard point instead of defining one for yourself.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<mexEndpoint>**  
  
## <a name="syntax"></a><span data-ttu-id="a61ee-103">構文</span><span class="sxs-lookup"><span data-stu-id="a61ee-103">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <mexEndpoint>
      <standardEndpoint name="String" />
    </mexEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a61ee-104">属性および要素</span><span class="sxs-lookup"><span data-stu-id="a61ee-104">Attributes and Elements</span></span>  
 <span data-ttu-id="a61ee-105">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="a61ee-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a61ee-106">属性</span><span class="sxs-lookup"><span data-stu-id="a61ee-106">Attributes</span></span>  
  
|<span data-ttu-id="a61ee-107">属性</span><span class="sxs-lookup"><span data-stu-id="a61ee-107">Attribute</span></span>|<span data-ttu-id="a61ee-108">説明</span><span class="sxs-lookup"><span data-stu-id="a61ee-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a61ee-109">name</span><span class="sxs-lookup"><span data-stu-id="a61ee-109">name</span></span>|<span data-ttu-id="a61ee-110">標準エンドポイントの構成名を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="a61ee-110">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="a61ee-111">この名前は、サービス エンドポイントの `endpointConfiguration` 属性で使用され、標準エンドポイントと構成を関連付けます。</span><span class="sxs-lookup"><span data-stu-id="a61ee-111">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a61ee-112">子要素</span><span class="sxs-lookup"><span data-stu-id="a61ee-112">Child Elements</span></span>  
 <span data-ttu-id="a61ee-113">なし。</span><span class="sxs-lookup"><span data-stu-id="a61ee-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a61ee-114">親要素</span><span class="sxs-lookup"><span data-stu-id="a61ee-114">Parent Elements</span></span>  
  
|<span data-ttu-id="a61ee-115">要素</span><span class="sxs-lookup"><span data-stu-id="a61ee-115">Element</span></span>|<span data-ttu-id="a61ee-116">Description</span><span class="sxs-lookup"><span data-stu-id="a61ee-116">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="a61ee-117">1 つ以上のプロパティ (アドレス、バインディング、コントラクト) が固定されている、あらかじめ定義されたエンドポイントである標準エンドポイントのコレクション。</span><span class="sxs-lookup"><span data-stu-id="a61ee-117">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|
