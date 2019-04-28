---
title: <mexEndpoint>
ms.date: 03/30/2017
ms.assetid: c9823060-0a5d-4f9d-99d4-4d113b758247
ms.openlocfilehash: 8fffcc05d5f53f719efce182083fbf103b1230ff
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61772477"
---
# <a name="mexendpoint"></a><span data-ttu-id="42918-101">\<mexEndpoint></span><span class="sxs-lookup"><span data-stu-id="42918-101">\<mexEndpoint></span></span>
<span data-ttu-id="42918-102">この構成要素は、固定 IMetadataExchange コントラクトが含まれた標準エンドポイントを定義します。</span><span class="sxs-lookup"><span data-stu-id="42918-102">This configuration element defines a standard endpoint with a fixed IMetadataExchange contract.</span></span> <span data-ttu-id="42918-103">IMetadataExchange はすべてのメタデータ交換エンドポイントでコントラクトとして指定されるため、独自のエンドポイントを定義せずにこの標準エンドポイントを使用できます。</span><span class="sxs-lookup"><span data-stu-id="42918-103">Since all metadata exchange endpoints specify IMetadataExchange as their contract, you can use this standard point instead of defining one for yourself.</span></span>  
  
 <span data-ttu-id="42918-104">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="42918-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="42918-105">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="42918-105">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42918-106">構文</span><span class="sxs-lookup"><span data-stu-id="42918-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <mexEndpoint>
      <standardEndpoint name="String" />
    </mexEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="42918-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="42918-107">Attributes and Elements</span></span>  
 <span data-ttu-id="42918-108">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="42918-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="42918-109">属性</span><span class="sxs-lookup"><span data-stu-id="42918-109">Attributes</span></span>  
  
|<span data-ttu-id="42918-110">属性</span><span class="sxs-lookup"><span data-stu-id="42918-110">Attribute</span></span>|<span data-ttu-id="42918-111">説明</span><span class="sxs-lookup"><span data-stu-id="42918-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="42918-112">name</span><span class="sxs-lookup"><span data-stu-id="42918-112">name</span></span>|<span data-ttu-id="42918-113">標準エンドポイントの構成名を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="42918-113">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="42918-114">この名前は、サービス エンドポイントの `endpointConfiguration` 属性で使用され、標準エンドポイントと構成を関連付けます。</span><span class="sxs-lookup"><span data-stu-id="42918-114">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="42918-115">子要素</span><span class="sxs-lookup"><span data-stu-id="42918-115">Child Elements</span></span>  
 <span data-ttu-id="42918-116">なし。</span><span class="sxs-lookup"><span data-stu-id="42918-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="42918-117">親要素</span><span class="sxs-lookup"><span data-stu-id="42918-117">Parent Elements</span></span>  
  
|<span data-ttu-id="42918-118">要素</span><span class="sxs-lookup"><span data-stu-id="42918-118">Element</span></span>|<span data-ttu-id="42918-119">説明</span><span class="sxs-lookup"><span data-stu-id="42918-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="42918-120">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="42918-120">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="42918-121">1 つ以上のプロパティ (アドレス、バインディング、コントラクト) が固定されている、あらかじめ定義されたエンドポイントである標準エンドポイントのコレクション。</span><span class="sxs-lookup"><span data-stu-id="42918-121">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|
