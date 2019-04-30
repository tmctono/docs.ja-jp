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
ms.openlocfilehash: c8044bc341ded6ef7b03bbdf701e724654460d54
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61938828"
---
# <a name="xxdata-intrinsic-xaml-type"></a><span data-ttu-id="553ad-102">x:XData 組み込み XAML 型</span><span class="sxs-lookup"><span data-stu-id="553ad-102">x:XData Intrinsic XAML Type</span></span>
<span data-ttu-id="553ad-103">XAML の運用環境での XML データ アイランドの配置を有効にします。</span><span class="sxs-lookup"><span data-stu-id="553ad-103">Enables placement of XML data islands within a XAML production.</span></span> <span data-ttu-id="553ad-104">内の XML 要素`x:XData`が動作する既定の XAML 名前空間の一部かその他の XAML 名前空間かのように XAML プロセッサで扱うことはできません。</span><span class="sxs-lookup"><span data-stu-id="553ad-104">XML elements within `x:XData` should not be treated by XAML processors as if they are a part of the acting default XAML namespace or any other XAML namespace.</span></span> <span data-ttu-id="553ad-105">`x:XData` 任意の整形式 XML を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="553ad-105">`x:XData` can contain arbitrary well-formed XML.</span></span>  
  
## <a name="xaml-object-element-usage"></a><span data-ttu-id="553ad-106">XAML オブジェクト要素の使用方法</span><span class="sxs-lookup"><span data-stu-id="553ad-106">XAML Object Element Usage</span></span>  
  
```  
<x:XData>  
  <elementDataRoot>  
    [elementData]  
  </elementDataRoot>  
</x:XData>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="553ad-107">XAML 値</span><span class="sxs-lookup"><span data-stu-id="553ad-107">XAML Values</span></span>  
  
|||  
|-|-|  
|`elementDataRoot`|<span data-ttu-id="553ad-108">囲まれたデータ アイランドの単一のルート要素。</span><span class="sxs-lookup"><span data-stu-id="553ad-108">The single root element of the enclosed data island.</span></span> <span data-ttu-id="553ad-109">ほとんどの最終的なコンシューマーの単一のルートがない XML が無効と見なされます。</span><span class="sxs-lookup"><span data-stu-id="553ad-109">For most eventual consumers, XML that does not have a single root is considered invalid.</span></span> <span data-ttu-id="553ad-110">具体的には、単一のルートは、必要な場合、 `x:XData` WPF のデータ バインディングの XML ソースを使用する他の多くのテクノロジとして XML データ ソースを対象としています。</span><span class="sxs-lookup"><span data-stu-id="553ad-110">In particular, a single root is required if the `x:XData` is intended as an XML data source for WPF or many other technologies that use XML sources for data binding.</span></span>|  
|`[elementData]`|<span data-ttu-id="553ad-111">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="553ad-111">Optional.</span></span> <span data-ttu-id="553ad-112">XML データを表す XML。</span><span class="sxs-lookup"><span data-stu-id="553ad-112">XML that represents the XML data.</span></span> <span data-ttu-id="553ad-113">要素のデータとして格納できる要素の任意の数と、入れ子になった要素を他の要素に含めることができます。ただし、XML の一般的な規則が適用されます。</span><span class="sxs-lookup"><span data-stu-id="553ad-113">Any number of elements can be contained as element data and nested elements can be contained in other elements; however, the general rules of XML apply.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="553ad-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="553ad-114">Remarks</span></span>  
 <span data-ttu-id="553ad-115">内の XML 要素、`x:XData`オブジェクトすべての可能な名前空間と、データ内に含む XMLDOM のプレフィックスを再宣言できます。</span><span class="sxs-lookup"><span data-stu-id="553ad-115">The XML elements within an `x:XData` object can re-declare all possible namespaces and prefixes of the containing XMLDOM within the data.</span></span>  
  
 <span data-ttu-id="553ad-116">XML データにプログラムでアクセスし、`x:XData`組み込み XAML 型から .NET Framework XAML サービスでは、<xref:System.Windows.Markup.XData>クラス。</span><span class="sxs-lookup"><span data-stu-id="553ad-116">Programmatic access to XML data and the `x:XData` intrinsic XAML type is possible in .NET Framework XAML Services through the <xref:System.Windows.Markup.XData> class.</span></span>  
  
## <a name="wpf-usage-notes"></a><span data-ttu-id="553ad-117">WPF の使用上の注意</span><span class="sxs-lookup"><span data-stu-id="553ad-117">WPF Usage Notes</span></span>  
 <span data-ttu-id="553ad-118">`x:XData`オブジェクトの子オブジェクトとして主に使用、 <xref:System.Windows.Data.XmlDataProvider>、または代わりの子オブジェクトとして、<xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType>プロパティ (で XAML、これは通常表現プロパティ要素構文で)。</span><span class="sxs-lookup"><span data-stu-id="553ad-118">The `x:XData` object is primarily used as a child object of an <xref:System.Windows.Data.XmlDataProvider>, or alternatively, as the child object of the <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> property (in XAML, this is typically expressed in property element syntax).</span></span>  
  
 <span data-ttu-id="553ad-119">データには、ベースの XML 名前空間を新しい既定の XML 名前空間 (空の文字列に設定) にデータ アイランド内で通常再定義しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="553ad-119">The data should typically redefine the base XML namespace within the data island to be a new default XML namespace (set to an empty string).</span></span> <span data-ttu-id="553ad-120">これは、単純なデータ諸島ための最も簡単な<xref:System.Windows.Data.Binding.XPath%2A>参照およびデータにバインドするために使用する式は、プレフィックスを含めることを避けることができます。</span><span class="sxs-lookup"><span data-stu-id="553ad-120">This is easiest for simple data islands because the <xref:System.Windows.Data.Binding.XPath%2A> expressions that are used to reference and bind to the data can avoid inclusion of prefixes.</span></span> <span data-ttu-id="553ad-121">複雑なデータ アイランドは、データの複数のプレフィックスを定義して、ルートにある XML 名前空間の特定のプレフィックスを使用して、可能性があります。</span><span class="sxs-lookup"><span data-stu-id="553ad-121">More complex data islands might define multiple prefixes for the data and use a specific prefix for the XML namespace at the root.</span></span> <span data-ttu-id="553ad-122">この場合、すべて<xref:System.Windows.Data.Binding.XPath%2A>式の参照は、適切な名前空間マッピング プレフィックスを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="553ad-122">In this case, all <xref:System.Windows.Data.Binding.XPath%2A> expression references should include the appropriate namespace-mapped prefix.</span></span> <span data-ttu-id="553ad-123">詳しくは、「 [データ バインディングの概要](../wpf/data/data-binding-overview.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="553ad-123">For more information, see [Data Binding Overview](../wpf/data/data-binding-overview.md).</span></span>  
  
 <span data-ttu-id="553ad-124">技術的には、`x:XData`型のプロパティの内容として使用できる<xref:System.Xml.Serialization.IXmlSerializable>します。</span><span class="sxs-lookup"><span data-stu-id="553ad-124">Technically, `x:XData` can be used as the content of any property of type <xref:System.Xml.Serialization.IXmlSerializable>.</span></span> <span data-ttu-id="553ad-125">ただし、<xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType>のみ、著名な実装です。</span><span class="sxs-lookup"><span data-stu-id="553ad-125">However, <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> is the only prominent implementation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="553ad-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="553ad-126">See also</span></span>

- <xref:System.Windows.Data.XmlDataProvider>
- [<span data-ttu-id="553ad-127">データ バインディングの概要</span><span class="sxs-lookup"><span data-stu-id="553ad-127">Data Binding Overview</span></span>](../wpf/data/data-binding-overview.md)
- [<span data-ttu-id="553ad-128">バインドのマークアップ拡張機能</span><span class="sxs-lookup"><span data-stu-id="553ad-128">Binding Markup Extension</span></span>](../wpf/advanced/binding-markup-extension.md)
