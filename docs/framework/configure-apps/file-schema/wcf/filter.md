---
title: <filter>
ms.date: 03/30/2017
ms.assetid: 3266700b-904b-44e4-93a7-e06a1a445100
ms.openlocfilehash: 6e78275aaeb202405e327302455d56fa431d7f27
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855251"
---
# <a name="filter"></a><span data-ttu-id="048e5-101">\<フィルター ></span><span class="sxs-lookup"><span data-stu-id="048e5-101">\<filter></span></span>

<span data-ttu-id="048e5-102">受信メッセージを評価するときに使用する Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter>の種類、およびフィルターに必要なサポートデータまたはパラメーターを決定するルーティングフィルターを定義します。</span><span class="sxs-lookup"><span data-stu-id="048e5-102">Defines a routing filter, which determines the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well any supporting data or parameters required by the filter.</span></span>

<span data-ttu-id="048e5-103">[ **\<system.serviceModel>** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="048e5-103">[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="048e5-104">&nbsp;&nbsp;[ **\<ルーティング >** ](routing.md)</span><span class="sxs-lookup"><span data-stu-id="048e5-104">&nbsp;&nbsp;[**\<routing>**](routing.md)</span></span>\
<span data-ttu-id="048e5-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<フィルター >** ](filters-of-routing.md)</span><span class="sxs-lookup"><span data-stu-id="048e5-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<filters>**](filters-of-routing.md)</span></span>\
<span data-ttu-id="048e5-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<フィルター >**</span><span class="sxs-lookup"><span data-stu-id="048e5-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filter>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="048e5-107">構文</span><span class="sxs-lookup"><span data-stu-id="048e5-107">Syntax</span></span>  
  
```xml  
<routing>
  <filters>
    <filter customType="String"
            filterData="String"
            filterType="Action/Address/AddressPrefix/And/Custom/Endpoint/MatchAll/XPath"
            name="String" />
  </filters>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="048e5-108">属性と要素</span><span class="sxs-lookup"><span data-stu-id="048e5-108">Attributes and elements</span></span>

<span data-ttu-id="048e5-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="048e5-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="048e5-110">属性</span><span class="sxs-lookup"><span data-stu-id="048e5-110">Attributes</span></span>

| <span data-ttu-id="048e5-111">属性</span><span class="sxs-lookup"><span data-stu-id="048e5-111">Attribute</span></span>  | <span data-ttu-id="048e5-112">説明</span><span class="sxs-lookup"><span data-stu-id="048e5-112">Description</span></span> |
| ---------- | ----------- |
| <span data-ttu-id="048e5-113">customType</span><span class="sxs-lookup"><span data-stu-id="048e5-113">customType</span></span> | <span data-ttu-id="048e5-114">フィルターとして使用されるカスタム型の完全修飾型名を示す文字列。</span><span class="sxs-lookup"><span data-stu-id="048e5-114">A string containing the fully qualified type name of the custom type to be used as a filter.</span></span> <span data-ttu-id="048e5-115">が`filterType` に`custom`設定されている場合、この属性には作成するクラスの完全修飾型名が含まれます。</span><span class="sxs-lookup"><span data-stu-id="048e5-115">If `filterType` is set to `custom`, this attribute contains the fully qualified type name of the class to create.</span></span>  <span data-ttu-id="048e5-116">`filterData`には、カスタム型フィルターの評価時に使用される値を含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="048e5-116">`filterData` may also contain values to be used during evaluation of the custom type filter.</span></span> |
| <span data-ttu-id="048e5-117">filterData</span><span class="sxs-lookup"><span data-stu-id="048e5-117">filterData</span></span> | <span data-ttu-id="048e5-118">フィルター データを示す文字列。</span><span class="sxs-lookup"><span data-stu-id="048e5-118">A string containing the filter data.</span></span> <span data-ttu-id="048e5-119">この属性を指定する方法の詳細については、「<xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="048e5-119">For more information on how to specify this attribute, see <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span></span> |
| <span data-ttu-id="048e5-120">filterType</span><span class="sxs-lookup"><span data-stu-id="048e5-120">filterType</span></span> | <span data-ttu-id="048e5-121">フィルターの種類を示す文字列。</span><span class="sxs-lookup"><span data-stu-id="048e5-121">A string containing the filter type.</span></span> <span data-ttu-id="048e5-122">この属性は <xref:System.ServiceModel.Routing.Configuration.FilterType> 型です。</span><span class="sxs-lookup"><span data-stu-id="048e5-122">This attribute is of <xref:System.ServiceModel.Routing.Configuration.FilterType> type.</span></span>  <span data-ttu-id="048e5-123">`filterData` 属性を使用する方法の詳細については、「<xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="048e5-123">For more information on how this works with the `filterData` attribute, see <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span></span> |
| <span data-ttu-id="048e5-124">name</span><span class="sxs-lookup"><span data-stu-id="048e5-124">name</span></span>       | <span data-ttu-id="048e5-125">フィルター要素の一意の名前を示す文字列。</span><span class="sxs-lookup"><span data-stu-id="048e5-125">A string containing the unique name of this filter element.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="048e5-126">子要素</span><span class="sxs-lookup"><span data-stu-id="048e5-126">Child elements</span></span>

<span data-ttu-id="048e5-127">なし。</span><span class="sxs-lookup"><span data-stu-id="048e5-127">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="048e5-128">親要素</span><span class="sxs-lookup"><span data-stu-id="048e5-128">Parent elements</span></span>

| <span data-ttu-id="048e5-129">要素</span><span class="sxs-lookup"><span data-stu-id="048e5-129">Element</span></span> | <span data-ttu-id="048e5-130">説明</span><span class="sxs-lookup"><span data-stu-id="048e5-130">Description</span></span> |
| ------- | ----------- |
| [<span data-ttu-id="048e5-131">\<ルーティング ></span><span class="sxs-lookup"><span data-stu-id="048e5-131">\<routing></span></span>](routing.md) | <span data-ttu-id="048e5-132">一連のルーティングフィルターを定義するための構成セクション。受信メッセージを評価するときに使用<xref:System.ServiceModel.Dispatcher.MessageFilter>する Windows Communication Foundation (WCF) の種類を決定します。</span><span class="sxs-lookup"><span data-stu-id="048e5-132">A configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages.</span></span> |

## <a name="see-also"></a><span data-ttu-id="048e5-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="048e5-133">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterType?displayProperty=nameWithType>
