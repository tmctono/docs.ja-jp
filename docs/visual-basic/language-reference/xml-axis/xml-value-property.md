---
title: XML Value プロパティ
ms.date: 07/20/2015
f1_keywords:
- vb.XmlPropertyExtensionValue
helpviewer_keywords:
- Value property [Visual Basic]
- Visual Basic code, accessing XML
- XML axis [Visual Basic], Value
- XML Value property [Visual Basic]
ms.assetid: 7ddd057a-a195-4e9b-ad8b-2ee0e615a20f
ms.openlocfilehash: 571d9130ef69df580bbba5d90bc8758b4b627196
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349418"
---
# <a name="xml-value-property-visual-basic"></a><span data-ttu-id="ebab3-102">XML Value プロパティ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ebab3-102">XML Value Property (Visual Basic)</span></span>

<span data-ttu-id="ebab3-103"><xref:System.Xml.Linq.XElement> オブジェクト コレクションの最初の要素の値にアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="ebab3-103">Provides access to the value of the first element of a collection of <xref:System.Xml.Linq.XElement> objects.</span></span>

## <a name="syntax"></a><span data-ttu-id="ebab3-104">構文</span><span class="sxs-lookup"><span data-stu-id="ebab3-104">Syntax</span></span>

```vb
object.Value
```

## <a name="parts"></a><span data-ttu-id="ebab3-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="ebab3-105">Parts</span></span>

|<span data-ttu-id="ebab3-106">用語</span><span class="sxs-lookup"><span data-stu-id="ebab3-106">Term</span></span>|<span data-ttu-id="ebab3-107">定義</span><span class="sxs-lookup"><span data-stu-id="ebab3-107">Definition</span></span>|  
|---|---|  
|`object`|<span data-ttu-id="ebab3-108">必須です。</span><span class="sxs-lookup"><span data-stu-id="ebab3-108">Required.</span></span> <span data-ttu-id="ebab3-109"><xref:System.Xml.Linq.XElement> オブジェクトのコレクション。</span><span class="sxs-lookup"><span data-stu-id="ebab3-109">Collection of <xref:System.Xml.Linq.XElement> objects.</span></span>|  

## <a name="return-value"></a><span data-ttu-id="ebab3-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="ebab3-110">Return Value</span></span>

 <span data-ttu-id="ebab3-111">コレクションの最初の要素の値を含む `String`、または `Nothing` (コレクションが空の場合)。</span><span class="sxs-lookup"><span data-stu-id="ebab3-111">A `String` that contains the value of the first element of the collection, or `Nothing` if the collection is empty.</span></span>

## <a name="remarks"></a><span data-ttu-id="ebab3-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="ebab3-112">Remarks</span></span>

 <span data-ttu-id="ebab3-113"><xref:System.Xml.Linq.XElement.Value%2A> プロパティは、<xref:System.Xml.Linq.XElement> オブジェクト コレクションの最初の要素の値にアクセスしやすくします。</span><span class="sxs-lookup"><span data-stu-id="ebab3-113">The <xref:System.Xml.Linq.XElement.Value%2A> property makes it easy to access the value of the first element in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="ebab3-114">このプロパティは、コレクションに少なくとも 1 つのオブジェクトが含まれるかどうかをまず確認します。</span><span class="sxs-lookup"><span data-stu-id="ebab3-114">This property first checks whether the collection contains at least one object.</span></span> <span data-ttu-id="ebab3-115">コレクションが空の場合、このプロパティは `Nothing` を返します。</span><span class="sxs-lookup"><span data-stu-id="ebab3-115">If the collection is empty, this property returns `Nothing`.</span></span> <span data-ttu-id="ebab3-116">それ以外の場合は、コレクションの最初の要素の <xref:System.Xml.Linq.XElement.Value%2A> プロパティ値を返します。</span><span class="sxs-lookup"><span data-stu-id="ebab3-116">Otherwise, this property returns the value of the <xref:System.Xml.Linq.XElement.Value%2A> property of the first element in the collection.</span></span>

> [!NOTE]
> <span data-ttu-id="ebab3-117">"\@" 識別子を使用して XML 属性の値にアクセスすると、属性値は `String` として返されるため、<xref:System.Xml.Linq.XAttribute.Value%2A> プロパティを明示的に指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ebab3-117">When you access the value of an XML attribute using the '\@' identifier, the attribute value is returned as a `String` and you do not need to explicitly specify the <xref:System.Xml.Linq.XAttribute.Value%2A> property.</span></span>

 <span data-ttu-id="ebab3-118">コレクションの他の要素には、XML 拡張インデクサー プロパティを使用してアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="ebab3-118">To access other elements in a collection, you can use the XML extension indexer property.</span></span> <span data-ttu-id="ebab3-119">詳細については、「[拡張インデクサー プロパティ](extension-indexer-property.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ebab3-119">For more information, see [Extension Indexer Property](extension-indexer-property.md).</span></span>

## <a name="inheritance"></a><span data-ttu-id="ebab3-120">継承</span><span class="sxs-lookup"><span data-stu-id="ebab3-120">Inheritance</span></span>

 <span data-ttu-id="ebab3-121">ユーザーのほとんどが <xref:System.Collections.Generic.IEnumerable%601> を実装する必要がないため、このセクションは無視できます。</span><span class="sxs-lookup"><span data-stu-id="ebab3-121">Most users will not have to implement <xref:System.Collections.Generic.IEnumerable%601>, and can therefore ignore this section.</span></span>

 <span data-ttu-id="ebab3-122"><xref:System.Xml.Linq.XElement.Value%2A> プロパティは、`IEnumerable(Of XElement)` を実装する型の拡張プロパティです。</span><span class="sxs-lookup"><span data-stu-id="ebab3-122">The <xref:System.Xml.Linq.XElement.Value%2A> property is an extension property for types that implement `IEnumerable(Of XElement)`.</span></span> <span data-ttu-id="ebab3-123">この拡張プロパティのバインディングは、拡張メソッドのバインディングと似ています。つまり、いずれかのインターフェイスが型で実装され、"Value" という名前のプロパティが定義されていると、そのプロパティは拡張プロパティよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="ebab3-123">The binding of this extension property is like the binding of extension methods: if a type implements one of the interfaces and defines a property that has the name "Value", that property has precedence over the extension property.</span></span> <span data-ttu-id="ebab3-124">言い換えると、この <xref:System.Xml.Linq.XElement.Value%2A> プロパティは、`IEnumerable(Of XElement)` を実装するクラスで新しいプロパティを定義してオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="ebab3-124">In other words, this <xref:System.Xml.Linq.XElement.Value%2A> property can be overridden by defining a new property in a class that implements `IEnumerable(Of XElement)`.</span></span>

## <a name="example"></a><span data-ttu-id="ebab3-125">例</span><span class="sxs-lookup"><span data-stu-id="ebab3-125">Example</span></span>

 <span data-ttu-id="ebab3-126">次の例は、<xref:System.Xml.Linq.XElement.Value%2A> プロパティを使用して、<xref:System.Xml.Linq.XElement> オブジェクト コレクションの最初のノードにアクセスする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="ebab3-126">The following example shows how to use the <xref:System.Xml.Linq.XElement.Value%2A> property to access the first node in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="ebab3-127">この例では、子軸プロパティを使用して、`contact` オブジェクトにある `phone` という名前の子ノードすべてのコレクションを取得します。</span><span class="sxs-lookup"><span data-stu-id="ebab3-127">The example uses the child axis property to get the collection of all child nodes named `phone` that are in the `contact` object.</span></span>

 [!code-vb[VbXMLSamples#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples7.vb#15)]

 <span data-ttu-id="ebab3-128">このコードを実行すると、次のテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ebab3-128">This code displays the following text:</span></span>

 `Phone number: 206-555-0144`

## <a name="example"></a><span data-ttu-id="ebab3-129">例</span><span class="sxs-lookup"><span data-stu-id="ebab3-129">Example</span></span>

 <span data-ttu-id="ebab3-130">次の例は、<xref:System.Xml.Linq.XAttribute> オブジェクトのコレクションから XML 属性の値を取得する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="ebab3-130">The following example shows how to get the value of an XML attribute from a collection of <xref:System.Xml.Linq.XAttribute> objects.</span></span> <span data-ttu-id="ebab3-131">この例では、属性軸プロパティを使用して、`phone` 要素すべての `type` 属性の値を表示します。</span><span class="sxs-lookup"><span data-stu-id="ebab3-131">The example uses the attribute axis property to display the value of the `type` attribute for all of the `phone` elements.</span></span>

 [!code-vb[VbXMLSamples#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples7.vb#16)]

 <span data-ttu-id="ebab3-132">このコードを実行すると、次のテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ebab3-132">This code displays the following text:</span></span>

 ```console
 home
 work
```

## <a name="see-also"></a><span data-ttu-id="ebab3-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="ebab3-133">See also</span></span>

- <xref:System.Xml.Linq.XElement>
- <xref:System.Collections.Generic.IEnumerable%601>
- [<span data-ttu-id="ebab3-134">XML 軸プロパティ</span><span class="sxs-lookup"><span data-stu-id="ebab3-134">XML Axis Properties</span></span>](index.md)
- [<span data-ttu-id="ebab3-135">XML リテラル</span><span class="sxs-lookup"><span data-stu-id="ebab3-135">XML Literals</span></span>](../xml-literals/index.md)
- [<span data-ttu-id="ebab3-136">Visual Basic での XML の作成</span><span class="sxs-lookup"><span data-stu-id="ebab3-136">Creating XML in Visual Basic</span></span>](../../programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="ebab3-137">拡張メソッド</span><span class="sxs-lookup"><span data-stu-id="ebab3-137">Extension Methods</span></span>](../../programming-guide/language-features/procedures/extension-methods.md)
- [<span data-ttu-id="ebab3-138">拡張インデクサー プロパティ</span><span class="sxs-lookup"><span data-stu-id="ebab3-138">Extension Indexer Property</span></span>](extension-indexer-property.md)
- [<span data-ttu-id="ebab3-139">XML 子軸プロパティ</span><span class="sxs-lookup"><span data-stu-id="ebab3-139">XML Child Axis Property</span></span>](xml-child-axis-property.md)
- [<span data-ttu-id="ebab3-140">XML 属性軸プロパティ</span><span class="sxs-lookup"><span data-stu-id="ebab3-140">XML Attribute Axis Property</span></span>](xml-attribute-axis-property.md)
