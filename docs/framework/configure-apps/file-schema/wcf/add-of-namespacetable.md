---
title: <add> の <namespaceTable>
ms.date: 03/30/2017
ms.assetid: cf7b5b75-63bd-49a6-abac-4bfdab377e36
ms.openlocfilehash: 3b3b4a1584b37601269368ee0e4e973626ddf9cf
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850388"
---
# <a name="add-of-namespacetable"></a><span data-ttu-id="4d382-102">\<add> の \<namespaceTable></span><span class="sxs-lookup"><span data-stu-id="4d382-102">\<add> of \<namespaceTable></span></span>
<span data-ttu-id="4d382-103">名前空間とプレフィックスのマッピングを含む構成要素を表します。これは、ルーティングの XPath フィルターで使用されます。</span><span class="sxs-lookup"><span data-stu-id="4d382-103">Represents a configuration element that contains a namespace to prefix mapping that can then be used in XPath filters for routing.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namespaceTable>**](namespacetable.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="4d382-104">構文</span><span class="sxs-lookup"><span data-stu-id="4d382-104">Syntax</span></span>  
  
```xml  
<routing>
  <namespaceTable>
    <add namespace="String"
         prefix="String" />
  </namespaceTable>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4d382-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="4d382-105">Attributes and Elements</span></span>  
 <span data-ttu-id="4d382-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="4d382-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4d382-107">属性</span><span class="sxs-lookup"><span data-stu-id="4d382-107">Attributes</span></span>  
  
|<span data-ttu-id="4d382-108">属性</span><span class="sxs-lookup"><span data-stu-id="4d382-108">Attribute</span></span>|<span data-ttu-id="4d382-109">説明</span><span class="sxs-lookup"><span data-stu-id="4d382-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4d382-110">namespace</span><span class="sxs-lookup"><span data-stu-id="4d382-110">namespace</span></span>|<span data-ttu-id="4d382-111">名前空間を示す文字列。</span><span class="sxs-lookup"><span data-stu-id="4d382-111">A string containing the namespace.</span></span>|  
|<span data-ttu-id="4d382-112">prefix</span><span class="sxs-lookup"><span data-stu-id="4d382-112">prefix</span></span>|<span data-ttu-id="4d382-113">この名前空間のプレフィックスを示す文字列。</span><span class="sxs-lookup"><span data-stu-id="4d382-113">A string containing the prefix for this namespace.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4d382-114">子要素</span><span class="sxs-lookup"><span data-stu-id="4d382-114">Child Elements</span></span>  
 <span data-ttu-id="4d382-115">なし。</span><span class="sxs-lookup"><span data-stu-id="4d382-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4d382-116">親要素</span><span class="sxs-lookup"><span data-stu-id="4d382-116">Parent Elements</span></span>  
  
|<span data-ttu-id="4d382-117">要素</span><span class="sxs-lookup"><span data-stu-id="4d382-117">Element</span></span>|<span data-ttu-id="4d382-118">Description</span><span class="sxs-lookup"><span data-stu-id="4d382-118">Description</span></span>|  
|-------------|-----------------|  
|[\<namespaceTable>](namespacetable.md)|<span data-ttu-id="4d382-119">名前空間とプレフィックスのマッピングを含む要素セットを定義する構成セクションを表します。これは、ルーティングの XPath フィルターで使用されます。</span><span class="sxs-lookup"><span data-stu-id="4d382-119">Represents a configuration section for defining a set of elements that contain namespace to prefix mappings that can then be used in XPath filters for routing.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4d382-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="4d382-120">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.NamespaceElement?displayProperty=nameWithType>
