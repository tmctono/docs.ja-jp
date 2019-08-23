---
title: <add> の <namespaceTable>
ms.date: 03/30/2017
ms.assetid: cf7b5b75-63bd-49a6-abac-4bfdab377e36
ms.openlocfilehash: 7e2a2e26099f2d31116e4a89297fc1ac984c480d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920076"
---
# <a name="add-of-namespacetable"></a><span data-ttu-id="38f9e-102">\<namespaceTable > の\<> の追加</span><span class="sxs-lookup"><span data-stu-id="38f9e-102">\<add> of \<namespaceTable></span></span>
<span data-ttu-id="38f9e-103">名前空間とプレフィックスのマッピングを含む構成要素を表します。これは、ルーティングの XPath フィルターで使用されます。</span><span class="sxs-lookup"><span data-stu-id="38f9e-103">Represents a configuration element that contains a namespace to prefix mapping that can then be used in XPath filters for routing.</span></span>  
  
 <span data-ttu-id="38f9e-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="38f9e-104">\<system.serviceModel></span></span>  
<span data-ttu-id="38f9e-105">\<ルーティング ></span><span class="sxs-lookup"><span data-stu-id="38f9e-105">\<routing></span></span>  
<span data-ttu-id="38f9e-106">\<namespaceTable ></span><span class="sxs-lookup"><span data-stu-id="38f9e-106">\<namespaceTable></span></span>  
<span data-ttu-id="38f9e-107">\<add></span><span class="sxs-lookup"><span data-stu-id="38f9e-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38f9e-108">構文</span><span class="sxs-lookup"><span data-stu-id="38f9e-108">Syntax</span></span>  
  
```xml  
<routing>
  <namespaceTable>
    <add namespace="String"
         prefix="String" />
  </namespaceTable>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="38f9e-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="38f9e-109">Attributes and Elements</span></span>  
 <span data-ttu-id="38f9e-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="38f9e-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="38f9e-111">属性</span><span class="sxs-lookup"><span data-stu-id="38f9e-111">Attributes</span></span>  
  
|<span data-ttu-id="38f9e-112">属性</span><span class="sxs-lookup"><span data-stu-id="38f9e-112">Attribute</span></span>|<span data-ttu-id="38f9e-113">説明</span><span class="sxs-lookup"><span data-stu-id="38f9e-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="38f9e-114">名前空間</span><span class="sxs-lookup"><span data-stu-id="38f9e-114">namespace</span></span>|<span data-ttu-id="38f9e-115">名前空間を示す文字列。</span><span class="sxs-lookup"><span data-stu-id="38f9e-115">A string containing the namespace.</span></span>|  
|<span data-ttu-id="38f9e-116">prefix</span><span class="sxs-lookup"><span data-stu-id="38f9e-116">prefix</span></span>|<span data-ttu-id="38f9e-117">この名前空間のプレフィックスを示す文字列。</span><span class="sxs-lookup"><span data-stu-id="38f9e-117">A string containing the prefix for this namespace.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="38f9e-118">子要素</span><span class="sxs-lookup"><span data-stu-id="38f9e-118">Child Elements</span></span>  
 <span data-ttu-id="38f9e-119">なし。</span><span class="sxs-lookup"><span data-stu-id="38f9e-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="38f9e-120">親要素</span><span class="sxs-lookup"><span data-stu-id="38f9e-120">Parent Elements</span></span>  
  
|<span data-ttu-id="38f9e-121">要素</span><span class="sxs-lookup"><span data-stu-id="38f9e-121">Element</span></span>|<span data-ttu-id="38f9e-122">説明</span><span class="sxs-lookup"><span data-stu-id="38f9e-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="38f9e-123">\<namespaceTable></span><span class="sxs-lookup"><span data-stu-id="38f9e-123">\<namespaceTable></span></span>](namespacetable.md)|<span data-ttu-id="38f9e-124">名前空間とプレフィックスのマッピングを含む要素セットを定義する構成セクションを表します。これは、ルーティングの XPath フィルターで使用されます。</span><span class="sxs-lookup"><span data-stu-id="38f9e-124">Represents a configuration section for defining a set of elements that contain namespace to prefix mappings that can then be used in XPath filters for routing.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="38f9e-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="38f9e-125">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.NamespaceElement?displayProperty=nameWithType>
