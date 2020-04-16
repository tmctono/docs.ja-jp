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
ms.openlocfilehash: b7f0954158988db107feb4a6c51ba81d5db11dcb
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432792"
---
# <a name="xxdata-intrinsic-xaml-type"></a><span data-ttu-id="97e55-102">x:XData 組み込み XAML 型</span><span class="sxs-lookup"><span data-stu-id="97e55-102">x:XData Intrinsic XAML Type</span></span>
<span data-ttu-id="97e55-103">XAML の運用環境内で XML データ アイランドを配置できるようにします。</span><span class="sxs-lookup"><span data-stu-id="97e55-103">Enables placement of XML data islands within a XAML production.</span></span> <span data-ttu-id="97e55-104">内部の`x:XData`XML 要素は、動作する既定の XAML 名前空間またはその他の XAML 名前空間の一部であるかのように XAML プロセッサによって扱われるべきではありません。</span><span class="sxs-lookup"><span data-stu-id="97e55-104">XML elements within `x:XData` should not be treated by XAML processors as if they are a part of the acting default XAML namespace or any other XAML namespace.</span></span> <span data-ttu-id="97e55-105">`x:XData`任意の整形式 XML を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="97e55-105">`x:XData` can contain arbitrary well-formed XML.</span></span>

## <a name="xaml-object-element-usage"></a><span data-ttu-id="97e55-106">XAML オブジェクト要素の使用方法</span><span class="sxs-lookup"><span data-stu-id="97e55-106">XAML Object Element Usage</span></span>

```xaml
<x:XData>
  <elementDataRoot>
    [elementData]
  </elementDataRoot>
</x:XData>
```

## <a name="xaml-values"></a><span data-ttu-id="97e55-107">XAML 値</span><span class="sxs-lookup"><span data-stu-id="97e55-107">XAML Values</span></span>

|||
|-|-|
|`elementDataRoot`|<span data-ttu-id="97e55-108">囲まれたデータ アイランドの単一のルート要素。</span><span class="sxs-lookup"><span data-stu-id="97e55-108">The single root element of the enclosed data island.</span></span> <span data-ttu-id="97e55-109">ほとんどの最終的なコンシューマーでは、ルートが 1 つもたない XML は無効と見なされます。</span><span class="sxs-lookup"><span data-stu-id="97e55-109">For most eventual consumers, XML that does not have a single root is considered invalid.</span></span> <span data-ttu-id="97e55-110">特に、WPF の XML データ`x:XData`ソースとして、またはデータ バインディングに XML ソースを使用するその他の多くのテクノロジを目的とする場合は、単一のルートが必要です。</span><span class="sxs-lookup"><span data-stu-id="97e55-110">In particular, a single root is required if the `x:XData` is intended as an XML data source for WPF or many other technologies that use XML sources for data binding.</span></span>|
|`[elementData]`|<span data-ttu-id="97e55-111">省略可能。</span><span class="sxs-lookup"><span data-stu-id="97e55-111">Optional.</span></span> <span data-ttu-id="97e55-112">XML データを表す XML。</span><span class="sxs-lookup"><span data-stu-id="97e55-112">XML that represents the XML data.</span></span> <span data-ttu-id="97e55-113">要素データとして任意の数の要素を含めることができ、入れ子になった要素は他の要素に含めることができます。ただし、XML の一般的な規則が適用されます。</span><span class="sxs-lookup"><span data-stu-id="97e55-113">Any number of elements can be contained as element data and nested elements can be contained in other elements; however, the general rules of XML apply.</span></span>|

## <a name="remarks"></a><span data-ttu-id="97e55-114">解説</span><span class="sxs-lookup"><span data-stu-id="97e55-114">Remarks</span></span>

<span data-ttu-id="97e55-115">オブジェクト内の`x:XData`XML 要素は、データ内の XMLDOM を含む名前空間とプレフィックスをすべて再宣言できます。</span><span class="sxs-lookup"><span data-stu-id="97e55-115">The XML elements within an `x:XData` object can re-declare all possible namespaces and prefixes of the containing XMLDOM within the data.</span></span>

<span data-ttu-id="97e55-116">XML データおよび`x:XData`組み込み XAML 型へのプログラムによるアクセスは、クラスを<xref:System.Windows.Markup.XData>通じて .NET XAML サービスで可能です。</span><span class="sxs-lookup"><span data-stu-id="97e55-116">Programmatic access to XML data and the `x:XData` intrinsic XAML type is possible in .NET XAML Services through the <xref:System.Windows.Markup.XData> class.</span></span>

## <a name="wpf-usage-notes"></a><span data-ttu-id="97e55-117">WPF の使用上の注意</span><span class="sxs-lookup"><span data-stu-id="97e55-117">WPF Usage Notes</span></span>

<span data-ttu-id="97e55-118">オブジェクト`x:XData`は主に<xref:System.Windows.Data.XmlDataProvider>、 の子オブジェクトとして使用されるか、または<xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType>プロパティの子オブジェクトとして使用されます (XAML では、通常はプロパティ要素構文で表されます)。</span><span class="sxs-lookup"><span data-stu-id="97e55-118">The `x:XData` object is primarily used as a child object of an <xref:System.Windows.Data.XmlDataProvider>, or alternatively, as the child object of the <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> property (in XAML, this is typically expressed in property element syntax).</span></span>

<span data-ttu-id="97e55-119">通常、データ アイランド内の基本 XML 名前空間を新しい既定の XML 名前空間 (空の文字列に設定) に再定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="97e55-119">The data should typically redefine the base XML namespace within the data island to be a new default XML namespace (set to an empty string).</span></span> <span data-ttu-id="97e55-120">データの参照とバインドに使用される式<xref:System.Windows.Data.Binding.XPath%2A>はプレフィックスを含めることを避けることができるので、これは単純なデータ アイランドにとって最も簡単です。</span><span class="sxs-lookup"><span data-stu-id="97e55-120">This is easiest for simple data islands because the <xref:System.Windows.Data.Binding.XPath%2A> expressions that are used to reference and bind to the data can avoid inclusion of prefixes.</span></span> <span data-ttu-id="97e55-121">より複雑なデータ アイランドでは、データに対して複数のプレフィックスを定義し、ルートにある XML 名前空間に特定のプレフィックスを使用する場合があります。</span><span class="sxs-lookup"><span data-stu-id="97e55-121">More complex data islands might define multiple prefixes for the data and use a specific prefix for the XML namespace at the root.</span></span> <span data-ttu-id="97e55-122">この場合、すべての<xref:System.Windows.Data.Binding.XPath%2A>式参照には、適切な名前空間マップのプレフィックスを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="97e55-122">In this case, all <xref:System.Windows.Data.Binding.XPath%2A> expression references should include the appropriate namespace-mapped prefix.</span></span> <span data-ttu-id="97e55-123">詳細については、「[データ バインディングの概要](../data/data-binding-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="97e55-123">For more information, see [Data Binding Overview](../data/data-binding-overview.md).</span></span>

<span data-ttu-id="97e55-124">技術的には`x:XData`、 型<xref:System.Xml.Serialization.IXmlSerializable>の任意のプロパティの内容として使用できます。</span><span class="sxs-lookup"><span data-stu-id="97e55-124">Technically, `x:XData` can be used as the content of any property of type <xref:System.Xml.Serialization.IXmlSerializable>.</span></span> <span data-ttu-id="97e55-125">しかし、<xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType>唯一の顕著な実装です。</span><span class="sxs-lookup"><span data-stu-id="97e55-125">However, <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> is the only prominent implementation.</span></span>

## <a name="see-also"></a><span data-ttu-id="97e55-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="97e55-126">See also</span></span>

- <xref:System.Windows.Data.XmlDataProvider>
- [<span data-ttu-id="97e55-127">データ バインディングの概要</span><span class="sxs-lookup"><span data-stu-id="97e55-127">Data Binding Overview</span></span>](../data/data-binding-overview.md)
- [<span data-ttu-id="97e55-128">バインドのマークアップ拡張機能</span><span class="sxs-lookup"><span data-stu-id="97e55-128">Binding Markup Extension</span></span>](../../framework/wpf/advanced/binding-markup-extension.md)
