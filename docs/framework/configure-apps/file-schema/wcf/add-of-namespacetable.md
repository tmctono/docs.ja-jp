---
title: <add> の <namespaceTable>
ms.date: 03/30/2017
ms.assetid: cf7b5b75-63bd-49a6-abac-4bfdab377e36
ms.openlocfilehash: 32eff2e7bfdf1aee4c7d37a0e06166afba3cb398
ms.sourcegitcommit: 29a9b29d8b7d07b9c59d46628da754a8bff57fa4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/17/2019
ms.locfileid: "69566736"
---
# <a name="add-of-namespacetable"></a><span data-ttu-id="523df-102">\<namespaceTable > の\<> の追加</span><span class="sxs-lookup"><span data-stu-id="523df-102">\<add> of \<namespaceTable></span></span>
<span data-ttu-id="523df-103">名前空間とプレフィックスのマッピングを含む構成要素を表します。これは、ルーティングの XPath フィルターで使用されます。</span><span class="sxs-lookup"><span data-stu-id="523df-103">Represents a configuration element that contains a namespace to prefix mapping that can then be used in XPath filters for routing.</span></span>  
  
 <span data-ttu-id="523df-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="523df-104">\<system.serviceModel></span></span>  
<span data-ttu-id="523df-105">\<ルーティング ></span><span class="sxs-lookup"><span data-stu-id="523df-105">\<routing></span></span>  
<span data-ttu-id="523df-106">\<namespaceTable ></span><span class="sxs-lookup"><span data-stu-id="523df-106">\<namespaceTable></span></span>  
<span data-ttu-id="523df-107">\<add></span><span class="sxs-lookup"><span data-stu-id="523df-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="523df-108">構文</span><span class="sxs-lookup"><span data-stu-id="523df-108">Syntax</span></span>  
  
```xml  
<routing>
  <namespaceTable>
    <add namespace="String"
         prefix="String" />
  </namespaceTable>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="523df-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="523df-109">Attributes and Elements</span></span>  
 <span data-ttu-id="523df-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="523df-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="523df-111">属性</span><span class="sxs-lookup"><span data-stu-id="523df-111">Attributes</span></span>  
  
|<span data-ttu-id="523df-112">属性</span><span class="sxs-lookup"><span data-stu-id="523df-112">Attribute</span></span>|<span data-ttu-id="523df-113">説明</span><span class="sxs-lookup"><span data-stu-id="523df-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="523df-114">名前空間</span><span class="sxs-lookup"><span data-stu-id="523df-114">namespace</span></span>|<span data-ttu-id="523df-115">名前空間を示す文字列。</span><span class="sxs-lookup"><span data-stu-id="523df-115">A string containing the namespace.</span></span>|  
|<span data-ttu-id="523df-116">prefix</span><span class="sxs-lookup"><span data-stu-id="523df-116">prefix</span></span>|<span data-ttu-id="523df-117">この名前空間のプレフィックスを示す文字列。</span><span class="sxs-lookup"><span data-stu-id="523df-117">A string containing the prefix for this namespace.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="523df-118">子要素</span><span class="sxs-lookup"><span data-stu-id="523df-118">Child Elements</span></span>  
 <span data-ttu-id="523df-119">なし。</span><span class="sxs-lookup"><span data-stu-id="523df-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="523df-120">親要素</span><span class="sxs-lookup"><span data-stu-id="523df-120">Parent Elements</span></span>  
  
|<span data-ttu-id="523df-121">要素</span><span class="sxs-lookup"><span data-stu-id="523df-121">Element</span></span>|<span data-ttu-id="523df-122">説明</span><span class="sxs-lookup"><span data-stu-id="523df-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="523df-123">\<namespaceTable></span><span class="sxs-lookup"><span data-stu-id="523df-123">\<namespaceTable></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/namespacetable.md)|<span data-ttu-id="523df-124">名前空間とプレフィックスのマッピングを含む要素セットを定義する構成セクションを表します。これは、ルーティングの XPath フィルターで使用されます。</span><span class="sxs-lookup"><span data-stu-id="523df-124">Represents a configuration section for defining a set of elements that contain namespace to prefix mappings that can then be used in XPath filters for routing.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="523df-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="523df-125">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.NamespaceElement?displayProperty=nameWithType>
