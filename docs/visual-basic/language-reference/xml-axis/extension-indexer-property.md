---
title: 拡張インデクサー プロパティ
ms.date: 07/20/2015
f1_keywords:
- vb.XmlPropertyExtensionIndexer
helpviewer_keywords:
- Visual Basic code, accessing XML
- XML extension indexer [Visual Basic]
- extension indexer [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: a16a4b13-54be-432c-82b3-a87091464ada
ms.openlocfilehash: 5f91dc8a6b1a0d82daa4891cf826c16e2716839f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352695"
---
# <a name="extension-indexer-property-visual-basic"></a><span data-ttu-id="9bc2f-102">拡張インデクサー プロパティ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9bc2f-102">Extension Indexer Property (Visual Basic)</span></span>
<span data-ttu-id="9bc2f-103">コレクション内の個々の要素にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="9bc2f-103">Provides access to individual elements in a collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9bc2f-104">構文</span><span class="sxs-lookup"><span data-stu-id="9bc2f-104">Syntax</span></span>  
  
```vb  
object(index)  
```  
  
## <a name="parts"></a><span data-ttu-id="9bc2f-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="9bc2f-105">Parts</span></span>  
  
|<span data-ttu-id="9bc2f-106">用語</span><span class="sxs-lookup"><span data-stu-id="9bc2f-106">Term</span></span>|<span data-ttu-id="9bc2f-107">Definition</span><span class="sxs-lookup"><span data-stu-id="9bc2f-107">Definition</span></span>|  
|---|---|  
|`object`|<span data-ttu-id="9bc2f-108">必須。</span><span class="sxs-lookup"><span data-stu-id="9bc2f-108">Required.</span></span> <span data-ttu-id="9bc2f-109">クエリ可能なコレクション。</span><span class="sxs-lookup"><span data-stu-id="9bc2f-109">A queryable collection.</span></span> <span data-ttu-id="9bc2f-110">つまり、<xref:System.Collections.Generic.IEnumerable%601> または <xref:System.Linq.IQueryable%601>を実装するコレクションです。</span><span class="sxs-lookup"><span data-stu-id="9bc2f-110">That is, a collection that implements <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>.</span></span>|  
|<span data-ttu-id="9bc2f-111">(</span><span class="sxs-lookup"><span data-stu-id="9bc2f-111">(</span></span>|<span data-ttu-id="9bc2f-112">必須。</span><span class="sxs-lookup"><span data-stu-id="9bc2f-112">Required.</span></span> <span data-ttu-id="9bc2f-113">インデクサープロパティの開始を示します。</span><span class="sxs-lookup"><span data-stu-id="9bc2f-113">Denotes the start of the indexer property.</span></span>|  
|`index`|<span data-ttu-id="9bc2f-114">必須。</span><span class="sxs-lookup"><span data-stu-id="9bc2f-114">Required.</span></span> <span data-ttu-id="9bc2f-115">コレクションの要素の0から始まる位置を指定する整数式。</span><span class="sxs-lookup"><span data-stu-id="9bc2f-115">An integer expression that specifies the zero-based position of an element of the collection.</span></span>|  
|<span data-ttu-id="9bc2f-116">)</span><span class="sxs-lookup"><span data-stu-id="9bc2f-116">)</span></span>|<span data-ttu-id="9bc2f-117">必須。</span><span class="sxs-lookup"><span data-stu-id="9bc2f-117">Required.</span></span> <span data-ttu-id="9bc2f-118">インデクサープロパティの末尾を示します。</span><span class="sxs-lookup"><span data-stu-id="9bc2f-118">Denotes the end of the indexer property.</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="9bc2f-119">戻り値</span><span class="sxs-lookup"><span data-stu-id="9bc2f-119">Return Value</span></span>  
 <span data-ttu-id="9bc2f-120">コレクション内の指定した位置にあるオブジェクト。インデックスが範囲外の場合は `Nothing`。</span><span class="sxs-lookup"><span data-stu-id="9bc2f-120">The object from the specified location in the collection, or `Nothing` if the index is out of range.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9bc2f-121">コメント</span><span class="sxs-lookup"><span data-stu-id="9bc2f-121">Remarks</span></span>  
 <span data-ttu-id="9bc2f-122">拡張インデクサープロパティを使用して、コレクション内の個々の要素にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="9bc2f-122">You can use the extension indexer property to access individual elements in a collection.</span></span> <span data-ttu-id="9bc2f-123">このインデクサープロパティは、通常、XML 軸プロパティの出力に使用されます。</span><span class="sxs-lookup"><span data-stu-id="9bc2f-123">This indexer property is typically used on the output of XML axis properties.</span></span> <span data-ttu-id="9bc2f-124">XML 子および XML 子孫軸プロパティは、<xref:System.Xml.Linq.XElement> オブジェクトまたは属性値のコレクションを返します。</span><span class="sxs-lookup"><span data-stu-id="9bc2f-124">The XML child and XML descendent axis properties return collections of <xref:System.Xml.Linq.XElement> objects or an attribute value.</span></span>  
  
 <span data-ttu-id="9bc2f-125">Visual Basic コンパイラは、拡張インデクサープロパティを `ElementAtOrDefault` メソッドの呼び出しに変換します。</span><span class="sxs-lookup"><span data-stu-id="9bc2f-125">The Visual Basic compiler converts extension indexer properties to calls to the `ElementAtOrDefault` method.</span></span> <span data-ttu-id="9bc2f-126">配列インデクサーとは異なり、`ElementAtOrDefault` メソッドは、インデックスが範囲外の場合に `Nothing` を返します。</span><span class="sxs-lookup"><span data-stu-id="9bc2f-126">Unlike an array indexer, the `ElementAtOrDefault` method returns `Nothing` if the index is out of range.</span></span> <span data-ttu-id="9bc2f-127">この動作は、コレクション内の要素の数を簡単に判断できない場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="9bc2f-127">This behavior is useful when you cannot easily determine the number of elements in a collection.</span></span>  
  
 <span data-ttu-id="9bc2f-128">このインデクサープロパティは、<xref:System.Collections.Generic.IEnumerable%601> または <xref:System.Linq.IQueryable%601>を実装するコレクションの拡張プロパティに似ています。このプロパティは、コレクションにインデクサーまたは default プロパティがない場合にのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="9bc2f-128">This indexer property is like an extension property for collections that implement <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>: it is used only if the collection does not have an indexer or a default property.</span></span>  
  
 <span data-ttu-id="9bc2f-129"><xref:System.Xml.Linq.XElement> または <xref:System.Xml.Linq.XAttribute> オブジェクトのコレクション内の最初の要素の値にアクセスするには、XML `Value` プロパティを使用できます。</span><span class="sxs-lookup"><span data-stu-id="9bc2f-129">To access the value of the first element in a collection of <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute> objects, you can use the XML `Value` property.</span></span> <span data-ttu-id="9bc2f-130">詳細については、「 [XML 値プロパティ](../../../visual-basic/language-reference/xml-axis/xml-value-property.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9bc2f-130">For more information, see [XML Value Property](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9bc2f-131">例</span><span class="sxs-lookup"><span data-stu-id="9bc2f-131">Example</span></span>  
 <span data-ttu-id="9bc2f-132">次の例では、拡張インデクサーを使用して、<xref:System.Xml.Linq.XElement> オブジェクトのコレクション内の2番目の子ノードにアクセスする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="9bc2f-132">The following example shows how to use the extension indexer to access the second child node in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="9bc2f-133">コレクションにアクセスするには、子軸プロパティを使用します。このプロパティは、`contact` オブジェクト内の `phone` という名前のすべての子要素を取得します。</span><span class="sxs-lookup"><span data-stu-id="9bc2f-133">The collection is accessed by using the child axis property, which gets all child elements named `phone` in the `contact` object.</span></span>  
  
 [!code-vb[VbXMLSamples#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples11.vb#24)]  
  
 <span data-ttu-id="9bc2f-134">このコードを実行すると、次のテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9bc2f-134">This code displays the following text:</span></span>  
  
 `Second phone number: 425-555-0145`  
  
## <a name="see-also"></a><span data-ttu-id="9bc2f-135">参照</span><span class="sxs-lookup"><span data-stu-id="9bc2f-135">See also</span></span>

- <xref:System.Xml.Linq.XElement>
- [<span data-ttu-id="9bc2f-136">XML 軸プロパティ</span><span class="sxs-lookup"><span data-stu-id="9bc2f-136">XML Axis Properties</span></span>](../../../visual-basic/language-reference/xml-axis/index.md)
- [<span data-ttu-id="9bc2f-137">XML リテラル</span><span class="sxs-lookup"><span data-stu-id="9bc2f-137">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="9bc2f-138">Visual Basic での XML の作成</span><span class="sxs-lookup"><span data-stu-id="9bc2f-138">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="9bc2f-139">XML Value プロパティ</span><span class="sxs-lookup"><span data-stu-id="9bc2f-139">XML Value Property</span></span>](../../../visual-basic/language-reference/xml-axis/xml-value-property.md)
