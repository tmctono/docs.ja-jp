---
title: <filter>
ms.date: 03/30/2017
ms.assetid: 3266700b-904b-44e4-93a7-e06a1a445100
ms.openlocfilehash: 6e78275aaeb202405e327302455d56fa431d7f27
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855251"
---
# \<filter>

<span data-ttu-id="0c3e8-101">受信メッセージを評価するときに使用する Windows Communication Foundation (WCF) の種類、 <xref:System.ServiceModel.Dispatcher.MessageFilter> およびフィルターに必要なサポートデータまたはパラメーターを決定するルーティングフィルターを定義します。</span><span class="sxs-lookup"><span data-stu-id="0c3e8-101">Defines a routing filter, which determines the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well any supporting data or parameters required by the filter.</span></span>

[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<filters>**](filters-of-routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filter>**  
  
## <a name="syntax"></a><span data-ttu-id="0c3e8-102">構文</span><span class="sxs-lookup"><span data-stu-id="0c3e8-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0c3e8-103">属性と要素</span><span class="sxs-lookup"><span data-stu-id="0c3e8-103">Attributes and elements</span></span>

<span data-ttu-id="0c3e8-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="0c3e8-104">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="0c3e8-105">属性</span><span class="sxs-lookup"><span data-stu-id="0c3e8-105">Attributes</span></span>

| <span data-ttu-id="0c3e8-106">属性</span><span class="sxs-lookup"><span data-stu-id="0c3e8-106">Attribute</span></span>  | <span data-ttu-id="0c3e8-107">説明</span><span class="sxs-lookup"><span data-stu-id="0c3e8-107">Description</span></span> |
| ---------- | ----------- |
| <span data-ttu-id="0c3e8-108">customType</span><span class="sxs-lookup"><span data-stu-id="0c3e8-108">customType</span></span> | <span data-ttu-id="0c3e8-109">フィルターとして使用されるカスタム型の完全修飾型名を示す文字列。</span><span class="sxs-lookup"><span data-stu-id="0c3e8-109">A string containing the fully qualified type name of the custom type to be used as a filter.</span></span> <span data-ttu-id="0c3e8-110">`filterType`がに設定されている場合 `custom` 、この属性には作成するクラスの完全修飾型名が含まれます。</span><span class="sxs-lookup"><span data-stu-id="0c3e8-110">If `filterType` is set to `custom`, this attribute contains the fully qualified type name of the class to create.</span></span>  <span data-ttu-id="0c3e8-111">`filterData`には、カスタム型フィルターの評価時に使用される値を含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="0c3e8-111">`filterData` may also contain values to be used during evaluation of the custom type filter.</span></span> |
| <span data-ttu-id="0c3e8-112">filterData</span><span class="sxs-lookup"><span data-stu-id="0c3e8-112">filterData</span></span> | <span data-ttu-id="0c3e8-113">フィルター データを示す文字列。</span><span class="sxs-lookup"><span data-stu-id="0c3e8-113">A string containing the filter data.</span></span> <span data-ttu-id="0c3e8-114">この属性を指定する方法の詳細については、「<xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c3e8-114">For more information on how to specify this attribute, see <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span></span> |
| <span data-ttu-id="0c3e8-115">filterType</span><span class="sxs-lookup"><span data-stu-id="0c3e8-115">filterType</span></span> | <span data-ttu-id="0c3e8-116">フィルターの種類を示す文字列。</span><span class="sxs-lookup"><span data-stu-id="0c3e8-116">A string containing the filter type.</span></span> <span data-ttu-id="0c3e8-117">この属性は <xref:System.ServiceModel.Routing.Configuration.FilterType> 型です。</span><span class="sxs-lookup"><span data-stu-id="0c3e8-117">This attribute is of <xref:System.ServiceModel.Routing.Configuration.FilterType> type.</span></span>  <span data-ttu-id="0c3e8-118">`filterData` 属性を使用する方法の詳細については、「<xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c3e8-118">For more information on how this works with the `filterData` attribute, see <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span></span> |
| <span data-ttu-id="0c3e8-119">name</span><span class="sxs-lookup"><span data-stu-id="0c3e8-119">name</span></span>       | <span data-ttu-id="0c3e8-120">フィルター要素の一意の名前を示す文字列。</span><span class="sxs-lookup"><span data-stu-id="0c3e8-120">A string containing the unique name of this filter element.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="0c3e8-121">子要素</span><span class="sxs-lookup"><span data-stu-id="0c3e8-121">Child elements</span></span>

<span data-ttu-id="0c3e8-122">なし。</span><span class="sxs-lookup"><span data-stu-id="0c3e8-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="0c3e8-123">親要素</span><span class="sxs-lookup"><span data-stu-id="0c3e8-123">Parent elements</span></span>

| <span data-ttu-id="0c3e8-124">要素</span><span class="sxs-lookup"><span data-stu-id="0c3e8-124">Element</span></span> | <span data-ttu-id="0c3e8-125">Description</span><span class="sxs-lookup"><span data-stu-id="0c3e8-125">Description</span></span> |
| ------- | ----------- |
| [\<routing>](routing.md) | <span data-ttu-id="0c3e8-126">一連のルーティングフィルターを定義するための構成セクション <xref:System.ServiceModel.Dispatcher.MessageFilter> 。受信メッセージを評価するときに使用する Windows Communication Foundation (WCF) の種類を決定します。</span><span class="sxs-lookup"><span data-stu-id="0c3e8-126">A configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages.</span></span> |

## <a name="see-also"></a><span data-ttu-id="0c3e8-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="0c3e8-127">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterType?displayProperty=nameWithType>
