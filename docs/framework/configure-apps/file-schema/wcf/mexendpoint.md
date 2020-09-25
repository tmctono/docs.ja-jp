---
title: <mexEndpoint>
ms.date: 03/30/2017
ms.assetid: c9823060-0a5d-4f9d-99d4-4d113b758247
ms.openlocfilehash: e8f0e0fa2ea1606bf980fd6fa1fcd47f12c3b540
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204750"
---
# \<mexEndpoint>

<span data-ttu-id="15e04-101">この構成要素は、固定 IMetadataExchange コントラクトが含まれた標準エンドポイントを定義します。</span><span class="sxs-lookup"><span data-stu-id="15e04-101">This configuration element defines a standard endpoint with a fixed IMetadataExchange contract.</span></span> <span data-ttu-id="15e04-102">IMetadataExchange はすべてのメタデータ交換エンドポイントでコントラクトとして指定されるため、独自のエンドポイントを定義せずにこの標準エンドポイントを使用できます。</span><span class="sxs-lookup"><span data-stu-id="15e04-102">Since all metadata exchange endpoints specify IMetadataExchange as their contract, you can use this standard point instead of defining one for yourself.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<mexEndpoint>**  
  
## <a name="syntax"></a><span data-ttu-id="15e04-103">構文</span><span class="sxs-lookup"><span data-stu-id="15e04-103">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <mexEndpoint>
      <standardEndpoint name="String" />
    </mexEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="15e04-104">属性および要素</span><span class="sxs-lookup"><span data-stu-id="15e04-104">Attributes and Elements</span></span>  

 <span data-ttu-id="15e04-105">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="15e04-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="15e04-106">属性</span><span class="sxs-lookup"><span data-stu-id="15e04-106">Attributes</span></span>  
  
|<span data-ttu-id="15e04-107">属性</span><span class="sxs-lookup"><span data-stu-id="15e04-107">Attribute</span></span>|<span data-ttu-id="15e04-108">説明</span><span class="sxs-lookup"><span data-stu-id="15e04-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="15e04-109">name</span><span class="sxs-lookup"><span data-stu-id="15e04-109">name</span></span>|<span data-ttu-id="15e04-110">標準エンドポイントの構成名を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="15e04-110">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="15e04-111">この名前は、サービス エンドポイントの `endpointConfiguration` 属性で使用され、標準エンドポイントと構成を関連付けます。</span><span class="sxs-lookup"><span data-stu-id="15e04-111">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="15e04-112">子要素</span><span class="sxs-lookup"><span data-stu-id="15e04-112">Child Elements</span></span>  

 <span data-ttu-id="15e04-113">なし。</span><span class="sxs-lookup"><span data-stu-id="15e04-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="15e04-114">親要素</span><span class="sxs-lookup"><span data-stu-id="15e04-114">Parent Elements</span></span>  
  
|<span data-ttu-id="15e04-115">要素</span><span class="sxs-lookup"><span data-stu-id="15e04-115">Element</span></span>|<span data-ttu-id="15e04-116">説明</span><span class="sxs-lookup"><span data-stu-id="15e04-116">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="15e04-117">1 つ以上のプロパティ (アドレス、バインディング、コントラクト) が固定されている、あらかじめ定義されたエンドポイントである標準エンドポイントのコレクション。</span><span class="sxs-lookup"><span data-stu-id="15e04-117">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|
