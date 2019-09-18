---
title: x:XData 組み込み XAML 型
ms.date: 03/30/2017
f1_keywords:
- x:XData
- XData
- xXData
helpviewer_keywords:
- XAML [XAML Services], x:XData directive element
- XData in XAML [XAML Services]
- x:XData XAML directive element [XAML Services]
ms.assetid: 7ce209c2-621b-4977-b643-565f7e663534
ms.openlocfilehash: c5f729837b9bb52ca7d232ca66b58e283a2bcefc
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053704"
---
# <a name="xxdata-intrinsic-xaml-type"></a><span data-ttu-id="e464b-102">x:XData 組み込み XAML 型</span><span class="sxs-lookup"><span data-stu-id="e464b-102">x:XData Intrinsic XAML Type</span></span>
<span data-ttu-id="e464b-103">XAML 運用環境内での XML データアイランドの配置を有効にします。</span><span class="sxs-lookup"><span data-stu-id="e464b-103">Enables placement of XML data islands within a XAML production.</span></span> <span data-ttu-id="e464b-104">内`x:XData`の XML 要素は、動作する既定の xaml 名前空間またはその他の xaml 名前空間の一部であるかのように、xaml プロセッサによって処理されないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e464b-104">XML elements within `x:XData` should not be treated by XAML processors as if they are a part of the acting default XAML namespace or any other XAML namespace.</span></span> <span data-ttu-id="e464b-105">`x:XData`任意の整形式の XML を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="e464b-105">`x:XData` can contain arbitrary well-formed XML.</span></span>  
  
## <a name="xaml-object-element-usage"></a><span data-ttu-id="e464b-106">XAML オブジェクト要素の使用方法</span><span class="sxs-lookup"><span data-stu-id="e464b-106">XAML Object Element Usage</span></span>  
  
```xaml  
<x:XData>  
  <elementDataRoot>  
    [elementData]  
  </elementDataRoot>  
</x:XData>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="e464b-107">XAML 値</span><span class="sxs-lookup"><span data-stu-id="e464b-107">XAML Values</span></span>  
  
|||  
|-|-|  
|`elementDataRoot`|<span data-ttu-id="e464b-108">囲まれたデータアイランドの単一のルート要素。</span><span class="sxs-lookup"><span data-stu-id="e464b-108">The single root element of the enclosed data island.</span></span> <span data-ttu-id="e464b-109">最終的なコンシューマーの多くは、1つのルートを持たない XML は無効と見なされます。</span><span class="sxs-lookup"><span data-stu-id="e464b-109">For most eventual consumers, XML that does not have a single root is considered invalid.</span></span> <span data-ttu-id="e464b-110">特に、 `x:XData`が WPF の xml データソースである場合、またはデータバインディングに xml ソースを使用するその他の多くのテクノロジの場合は、単一のルートが必要です。</span><span class="sxs-lookup"><span data-stu-id="e464b-110">In particular, a single root is required if the `x:XData` is intended as an XML data source for WPF or many other technologies that use XML sources for data binding.</span></span>|  
|`[elementData]`|<span data-ttu-id="e464b-111">任意。</span><span class="sxs-lookup"><span data-stu-id="e464b-111">Optional.</span></span> <span data-ttu-id="e464b-112">XML データを表す XML です。</span><span class="sxs-lookup"><span data-stu-id="e464b-112">XML that represents the XML data.</span></span> <span data-ttu-id="e464b-113">要素データとして任意の数の要素を含めることができ、入れ子になった要素を他の要素に含めることができます。ただし、XML の一般的な規則が適用されます。</span><span class="sxs-lookup"><span data-stu-id="e464b-113">Any number of elements can be contained as element data and nested elements can be contained in other elements; however, the general rules of XML apply.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e464b-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="e464b-114">Remarks</span></span>  
 <span data-ttu-id="e464b-115">`x:XData`オブジェクト内の XML 要素は、データ内の格納されている XMLDOM のすべての可能な名前空間とプレフィックスを再宣言できます。</span><span class="sxs-lookup"><span data-stu-id="e464b-115">The XML elements within an `x:XData` object can re-declare all possible namespaces and prefixes of the containing XMLDOM within the data.</span></span>  
  
 <span data-ttu-id="e464b-116">XML データと`x:XData`組み込み xaml 型へのプログラムによるアクセスは、 <xref:System.Windows.Markup.XData> .NET Framework xaml サービスでクラスを使用して行うことができます。</span><span class="sxs-lookup"><span data-stu-id="e464b-116">Programmatic access to XML data and the `x:XData` intrinsic XAML type is possible in .NET Framework XAML Services through the <xref:System.Windows.Markup.XData> class.</span></span>  
  
## <a name="wpf-usage-notes"></a><span data-ttu-id="e464b-117">WPF の使用上の注意</span><span class="sxs-lookup"><span data-stu-id="e464b-117">WPF Usage Notes</span></span>  
 <span data-ttu-id="e464b-118">オブジェクトは<xref:System.Windows.Data.XmlDataProvider>、主にの子オブジェクトとして使用されるか、または<xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType>プロパティの子オブジェクトとして使用されます (XAML では、これは通常、プロパティ要素構文で表されます)。 `x:XData`</span><span class="sxs-lookup"><span data-stu-id="e464b-118">The `x:XData` object is primarily used as a child object of an <xref:System.Windows.Data.XmlDataProvider>, or alternatively, as the child object of the <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> property (in XAML, this is typically expressed in property element syntax).</span></span>  
  
 <span data-ttu-id="e464b-119">データは、通常、データアイランド内の基本 XML 名前空間を新しい既定の XML 名前空間 (空の文字列に設定) に再定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e464b-119">The data should typically redefine the base XML namespace within the data island to be a new default XML namespace (set to an empty string).</span></span> <span data-ttu-id="e464b-120">データの参照とバインドに使用される<xref:System.Windows.Data.Binding.XPath%2A>式ではプレフィックスが含まれないため、単純なデータアイランドではこの方法が最も簡単です。</span><span class="sxs-lookup"><span data-stu-id="e464b-120">This is easiest for simple data islands because the <xref:System.Windows.Data.Binding.XPath%2A> expressions that are used to reference and bind to the data can avoid inclusion of prefixes.</span></span> <span data-ttu-id="e464b-121">より複雑なデータアイランドでは、データに複数のプレフィックスを定義し、ルートで XML 名前空間に特定のプレフィックスを使用する場合があります。</span><span class="sxs-lookup"><span data-stu-id="e464b-121">More complex data islands might define multiple prefixes for the data and use a specific prefix for the XML namespace at the root.</span></span> <span data-ttu-id="e464b-122">この場合、すべて<xref:System.Windows.Data.Binding.XPath%2A>の式参照には、適切な名前空間にマップされたプレフィックスが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e464b-122">In this case, all <xref:System.Windows.Data.Binding.XPath%2A> expression references should include the appropriate namespace-mapped prefix.</span></span> <span data-ttu-id="e464b-123">詳しくは、「 [データ バインディングの概要](../wpf/data/data-binding-overview.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e464b-123">For more information, see [Data Binding Overview](../wpf/data/data-binding-overview.md).</span></span>  
  
 <span data-ttu-id="e464b-124">技術的に`x:XData`は、型<xref:System.Xml.Serialization.IXmlSerializable>の任意のプロパティのコンテンツとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="e464b-124">Technically, `x:XData` can be used as the content of any property of type <xref:System.Xml.Serialization.IXmlSerializable>.</span></span> <span data-ttu-id="e464b-125">ただし、 <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType>は唯一の実装です。</span><span class="sxs-lookup"><span data-stu-id="e464b-125">However, <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> is the only prominent implementation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e464b-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="e464b-126">See also</span></span>

- <xref:System.Windows.Data.XmlDataProvider>
- [<span data-ttu-id="e464b-127">データ バインディングの概要</span><span class="sxs-lookup"><span data-stu-id="e464b-127">Data Binding Overview</span></span>](../wpf/data/data-binding-overview.md)
- [<span data-ttu-id="e464b-128">バインドのマークアップ拡張機能</span><span class="sxs-lookup"><span data-stu-id="e464b-128">Binding Markup Extension</span></span>](../wpf/advanced/binding-markup-extension.md)
