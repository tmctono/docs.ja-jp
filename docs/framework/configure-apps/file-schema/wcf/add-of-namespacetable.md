---
title: <add> の <namespaceTable>
ms.date: 03/30/2017
ms.assetid: cf7b5b75-63bd-49a6-abac-4bfdab377e36
ms.openlocfilehash: 3b3b4a1584b37601269368ee0e4e973626ddf9cf
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850388"
---
# <a name="add-of-namespacetable"></a><span data-ttu-id="3ee41-102">\<namespaceTable > の\<> の追加</span><span class="sxs-lookup"><span data-stu-id="3ee41-102">\<add> of \<namespaceTable></span></span>
<span data-ttu-id="3ee41-103">名前空間とプレフィックスのマッピングを含む構成要素を表します。これは、ルーティングの XPath フィルターで使用されます。</span><span class="sxs-lookup"><span data-stu-id="3ee41-103">Represents a configuration element that contains a namespace to prefix mapping that can then be used in XPath filters for routing.</span></span>  
  
<span data-ttu-id="3ee41-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="3ee41-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="3ee41-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="3ee41-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="3ee41-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<ルーティング >** ](routing.md)</span><span class="sxs-lookup"><span data-stu-id="3ee41-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)</span></span>\
<span data-ttu-id="3ee41-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<namespaceTable >** ](namespacetable.md)</span><span class="sxs-lookup"><span data-stu-id="3ee41-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namespaceTable>**](namespacetable.md)</span></span>\
<span data-ttu-id="3ee41-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<add>**</span><span class="sxs-lookup"><span data-stu-id="3ee41-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ee41-109">構文</span><span class="sxs-lookup"><span data-stu-id="3ee41-109">Syntax</span></span>  
  
```xml  
<routing>
  <namespaceTable>
    <add namespace="String"
         prefix="String" />
  </namespaceTable>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3ee41-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="3ee41-110">Attributes and Elements</span></span>  
 <span data-ttu-id="3ee41-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="3ee41-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3ee41-112">属性</span><span class="sxs-lookup"><span data-stu-id="3ee41-112">Attributes</span></span>  
  
|<span data-ttu-id="3ee41-113">属性</span><span class="sxs-lookup"><span data-stu-id="3ee41-113">Attribute</span></span>|<span data-ttu-id="3ee41-114">説明</span><span class="sxs-lookup"><span data-stu-id="3ee41-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3ee41-115">名前空間</span><span class="sxs-lookup"><span data-stu-id="3ee41-115">namespace</span></span>|<span data-ttu-id="3ee41-116">名前空間を示す文字列。</span><span class="sxs-lookup"><span data-stu-id="3ee41-116">A string containing the namespace.</span></span>|  
|<span data-ttu-id="3ee41-117">prefix</span><span class="sxs-lookup"><span data-stu-id="3ee41-117">prefix</span></span>|<span data-ttu-id="3ee41-118">この名前空間のプレフィックスを示す文字列。</span><span class="sxs-lookup"><span data-stu-id="3ee41-118">A string containing the prefix for this namespace.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3ee41-119">子要素</span><span class="sxs-lookup"><span data-stu-id="3ee41-119">Child Elements</span></span>  
 <span data-ttu-id="3ee41-120">なし。</span><span class="sxs-lookup"><span data-stu-id="3ee41-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3ee41-121">親要素</span><span class="sxs-lookup"><span data-stu-id="3ee41-121">Parent Elements</span></span>  
  
|<span data-ttu-id="3ee41-122">要素</span><span class="sxs-lookup"><span data-stu-id="3ee41-122">Element</span></span>|<span data-ttu-id="3ee41-123">説明</span><span class="sxs-lookup"><span data-stu-id="3ee41-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3ee41-124">\<namespaceTable></span><span class="sxs-lookup"><span data-stu-id="3ee41-124">\<namespaceTable></span></span>](namespacetable.md)|<span data-ttu-id="3ee41-125">名前空間とプレフィックスのマッピングを含む要素セットを定義する構成セクションを表します。これは、ルーティングの XPath フィルターで使用されます。</span><span class="sxs-lookup"><span data-stu-id="3ee41-125">Represents a configuration section for defining a set of elements that contain namespace to prefix mappings that can then be used in XPath filters for routing.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3ee41-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="3ee41-126">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.NamespaceElement?displayProperty=nameWithType>
