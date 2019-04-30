---
title: XML 子軸プロパティ (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlPropertyChildAxis
helpviewer_keywords:
- Visual Basic code, accessing XML
- XML axis [Visual Basic], child
- child axis property [Visual Basic]
- XML child axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: 89a59d00-985e-4f5c-b59f-29b47bad11cb
ms.openlocfilehash: 8f8283e7ed09e657a20addab0b203b3d99420d3a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62025211"
---
# <a name="xml-child-axis-property-visual-basic"></a><span data-ttu-id="06ef4-102">XML 子軸プロパティ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="06ef4-102">XML Child Axis Property (Visual Basic)</span></span>
<span data-ttu-id="06ef4-103"><xref:System.Xml.Linq.XElement> オブジェクト、<xref:System.Xml.Linq.XDocument> オブジェクト、<xref:System.Xml.Linq.XElement> オブジェクトのコレクション、または <xref:System.Xml.Linq.XDocument> オブジェクトのコレクションのいずれかの子にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="06ef4-103">Provides access to the children of one of the following: an <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, a collection of <xref:System.Xml.Linq.XElement> objects, or a collection of <xref:System.Xml.Linq.XDocument> objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06ef4-104">構文</span><span class="sxs-lookup"><span data-stu-id="06ef4-104">Syntax</span></span>  
  
```  
object.<child>  
```  
  
## <a name="parts"></a><span data-ttu-id="06ef4-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="06ef4-105">Parts</span></span>  
  
|<span data-ttu-id="06ef4-106">用語</span><span class="sxs-lookup"><span data-stu-id="06ef4-106">Term</span></span>|<span data-ttu-id="06ef4-107">定義</span><span class="sxs-lookup"><span data-stu-id="06ef4-107">Definition</span></span>|  
|---|---|  
|`object`|<span data-ttu-id="06ef4-108">必須。</span><span class="sxs-lookup"><span data-stu-id="06ef4-108">Required.</span></span> <span data-ttu-id="06ef4-109"><xref:System.Xml.Linq.XElement> オブジェクト、<xref:System.Xml.Linq.XDocument> オブジェクト、<xref:System.Xml.Linq.XElement> オブジェクトのコレクション、または <xref:System.Xml.Linq.XDocument> オブジェクトのコレクションです。</span><span class="sxs-lookup"><span data-stu-id="06ef4-109">An <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, a collection of <xref:System.Xml.Linq.XElement> objects, or a collection of <xref:System.Xml.Linq.XDocument> objects.</span></span>|  
|<span data-ttu-id="06ef4-110">.<</span><span class="sxs-lookup"><span data-stu-id="06ef4-110">.<</span></span>|<span data-ttu-id="06ef4-111">必須。</span><span class="sxs-lookup"><span data-stu-id="06ef4-111">Required.</span></span> <span data-ttu-id="06ef4-112">子軸プロパティの開始を示します。</span><span class="sxs-lookup"><span data-stu-id="06ef4-112">Denotes the start of a child axis property.</span></span>|  
|`child`|<span data-ttu-id="06ef4-113">必須。</span><span class="sxs-lookup"><span data-stu-id="06ef4-113">Required.</span></span> <span data-ttu-id="06ef4-114">フォームにアクセスする子ノードの名前 [`prefix:]name`します。</span><span class="sxs-lookup"><span data-stu-id="06ef4-114">Name of the child nodes to access, of the form [`prefix:]name`.</span></span><br /><br /> <span data-ttu-id="06ef4-115">-   `Prefix` -省略可能。</span><span class="sxs-lookup"><span data-stu-id="06ef4-115">-   `Prefix` - Optional.</span></span> <span data-ttu-id="06ef4-116">子ノードの XML 名前空間プレフィックスです。</span><span class="sxs-lookup"><span data-stu-id="06ef4-116">XML namespace prefix for the child node.</span></span> <span data-ttu-id="06ef4-117">`Imports` ステートメントを使用して定義されているグローバル XML 名前空間を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="06ef4-117">Must be a global XML namespace defined with an `Imports` statement.</span></span><br /><span data-ttu-id="06ef4-118">-   `Name` 必須。</span><span class="sxs-lookup"><span data-stu-id="06ef4-118">-   `Name` - Required.</span></span> <span data-ttu-id="06ef4-119">ローカル子ノードの名前です。</span><span class="sxs-lookup"><span data-stu-id="06ef4-119">Local child node name.</span></span> <span data-ttu-id="06ef4-120">参照してください[宣言する XML 要素と属性の名前](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)します。</span><span class="sxs-lookup"><span data-stu-id="06ef4-120">See [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span>|  
|>|<span data-ttu-id="06ef4-121">必須。</span><span class="sxs-lookup"><span data-stu-id="06ef4-121">Required.</span></span> <span data-ttu-id="06ef4-122">子軸プロパティの終了を示します。</span><span class="sxs-lookup"><span data-stu-id="06ef4-122">Denotes the end of a child axis property.</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="06ef4-123">戻り値</span><span class="sxs-lookup"><span data-stu-id="06ef4-123">Return Value</span></span>  
 <span data-ttu-id="06ef4-124"><xref:System.Xml.Linq.XElement> オブジェクトのコレクション。</span><span class="sxs-lookup"><span data-stu-id="06ef4-124">A collection of <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="06ef4-125">Remarks</span><span class="sxs-lookup"><span data-stu-id="06ef4-125">Remarks</span></span>  
 <span data-ttu-id="06ef4-126">XML 子軸プロパティを使用すると、<xref:System.Xml.Linq.XElement> オブジェクト、<xref:System.Xml.Linq.XDocument> オブジェクト、<xref:System.Xml.Linq.XElement> オブジェクトのコレクション、または <xref:System.Xml.Linq.XDocument> オブジェクトのコレクションから子ノードに名前でアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="06ef4-126">You can use an XML child axis property to access child nodes by name from an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object, or from a collection of <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> objects.</span></span> <span data-ttu-id="06ef4-127">返されるコレクションの最初の子ノードの値にアクセスするには、XML の `Value` プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="06ef4-127">Use the XML `Value` property to access the value of the first child node in the returned collection.</span></span> <span data-ttu-id="06ef4-128">詳細については、次を参照してください。 [XML Value プロパティ](../../../visual-basic/language-reference/xml-axis/xml-value-property.md)します。</span><span class="sxs-lookup"><span data-stu-id="06ef4-128">For more information, see [XML Value Property](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span></span>  
  
 <span data-ttu-id="06ef4-129">Visual Basic コンパイラは、子軸プロパティをへの呼び出しに変換します、<xref:System.Xml.Linq.XContainer.Elements%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="06ef4-129">The Visual Basic compiler converts child axis properties to calls to the <xref:System.Xml.Linq.XContainer.Elements%2A> method.</span></span>  
  
## <a name="xml-namespaces"></a><span data-ttu-id="06ef4-130">XML 名前空間</span><span class="sxs-lookup"><span data-stu-id="06ef4-130">XML Namespaces</span></span>  
 <span data-ttu-id="06ef4-131">子軸プロパティの名前では、`Imports` ステートメントでグローバルに宣言されている XML 名前空間プレフィックスのみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="06ef4-131">The name in a child axis property can use only XML namespace prefixes declared globally with the `Imports` statement.</span></span> <span data-ttu-id="06ef4-132">XML 要素リテラル内でローカルに宣言されている XML 名前空間プレフィックスは使用できません。</span><span class="sxs-lookup"><span data-stu-id="06ef4-132">It cannot use XML namespace prefixes declared locally within XML element literals.</span></span> <span data-ttu-id="06ef4-133">詳細については、次を参照してください。 [Imports ステートメント (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)します。</span><span class="sxs-lookup"><span data-stu-id="06ef4-133">For more information, see [Imports Statement (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="06ef4-134">例</span><span class="sxs-lookup"><span data-stu-id="06ef4-134">Example</span></span>  
 <span data-ttu-id="06ef4-135">次の例は、`contact` オブジェクトの `phone` という名前の子ノードにアクセスする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="06ef4-135">The following example shows how to access the child nodes named `phone` from the `contact` object.</span></span>  
  
 [!code-vb[VbXMLSamples#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples7.vb#17)]  
  
 <span data-ttu-id="06ef4-136">このコードを実行すると、次のテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="06ef4-136">This code displays the following text:</span></span>  
  
 `Home Phone = 206-555-0144`  
  
## <a name="example"></a><span data-ttu-id="06ef4-137">例</span><span class="sxs-lookup"><span data-stu-id="06ef4-137">Example</span></span>  
 <span data-ttu-id="06ef4-138">次の例は、`contacts` オブジェクトの `contact` 子軸プロパティによって返されたコレクションの、`phone` という名前の子ノードにアクセスする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="06ef4-138">The following example shows how to access the child nodes named `phone` from the collection returned by the `contact` child axis property of the `contacts` object.</span></span>  
  
 [!code-vb[VbXMLSamples#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples7.vb#18)]  
  
 <span data-ttu-id="06ef4-139">このコードを実行すると、次のテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="06ef4-139">This code displays the following text:</span></span>  
  
 `Home Phone = 206-555-0144`  
  
## <a name="example"></a><span data-ttu-id="06ef4-140">例</span><span class="sxs-lookup"><span data-stu-id="06ef4-140">Example</span></span>  
 <span data-ttu-id="06ef4-141">次の例では、`ns` を名前空間プレフィックスとして宣言します。</span><span class="sxs-lookup"><span data-stu-id="06ef4-141">The following example declares `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="06ef4-142">その後、この名前空間のプレフィックスを使用して XML リテラルを作成し、修飾名 `ns:name` を持つ最初の子ノードにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="06ef4-142">It then uses the prefix of the namespace to create an XML literal and access the first child node with the qualified name `ns:name`.</span></span>  
  
 [!code-vb[VbXMLSamples#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples8.vb#19)]  
  
 <span data-ttu-id="06ef4-143">このコードを実行すると、次のテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="06ef4-143">This code displays the following text:</span></span>  
  
 `Patrick Hines`  
  
## <a name="see-also"></a><span data-ttu-id="06ef4-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="06ef4-144">See also</span></span>

- <xref:System.Xml.Linq.XElement>
- [<span data-ttu-id="06ef4-145">XML 軸プロパティ</span><span class="sxs-lookup"><span data-stu-id="06ef4-145">XML Axis Properties</span></span>](../../../visual-basic/language-reference/xml-axis/index.md)
- [<span data-ttu-id="06ef4-146">XML リテラル</span><span class="sxs-lookup"><span data-stu-id="06ef4-146">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="06ef4-147">Visual Basic での XML の作成</span><span class="sxs-lookup"><span data-stu-id="06ef4-147">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="06ef4-148">宣言する XML 要素と属性の名前</span><span class="sxs-lookup"><span data-stu-id="06ef4-148">Names of Declared XML Elements and Attributes</span></span>](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
