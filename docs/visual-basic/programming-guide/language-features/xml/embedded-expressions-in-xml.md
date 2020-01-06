---
title: XML での埋め込み式
ms.date: 07/20/2015
f1_keywords:
- vb.XmlEmbeddedExpression
helpviewer_keywords:
- embedded expressions [Visual Basic]
- LINQ to XML [Visual Basic], embedded expressions
- XML literals [Visual Basic], embedded expressions
ms.assetid: bf2eb779-b751-4b7c-854f-9f2161482352
ms.openlocfilehash: 0cdb960160457108ddf18c554dae5f5993269833
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74332354"
---
# <a name="embedded-expressions-in-xml-visual-basic"></a><span data-ttu-id="27e8d-102">XML での埋め込み式 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="27e8d-102">Embedded Expressions in XML (Visual Basic)</span></span>
<span data-ttu-id="27e8d-103">埋め込み式を使用すると、実行時に評価される式を含む XML リテラルを作成できます。</span><span class="sxs-lookup"><span data-stu-id="27e8d-103">Embedded expressions enable you to create XML literals that contain expressions that are evaluated at run time.</span></span> <span data-ttu-id="27e8d-104">埋め込み式の構文は `%>``expression` `<%=` ます。これは、ASP.NET で使用される構文と同じです。</span><span class="sxs-lookup"><span data-stu-id="27e8d-104">The syntax for an embedded expression is `<%=` `expression` `%>`, which is the same as the syntax used in ASP.NET.</span></span>  
  
 <span data-ttu-id="27e8d-105">たとえば、XML 要素リテラルを作成し、リテラルテキストコンテンツと共に埋め込み式を組み合わせることができます。</span><span class="sxs-lookup"><span data-stu-id="27e8d-105">For example, you can create an XML element literal, combining embedded expressions with literal text content.</span></span>  
  
 [!code-vb[VbXMLSamples#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#27)]  
  
 <span data-ttu-id="27e8d-106">`isbnNumber` に整数12345が含まれ、`modifiedDate` に日付3/5/2006 が含まれている場合、このコードが実行されると `book` の値は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="27e8d-106">If `isbnNumber` contains the integer 12345 and `modifiedDate` contains the date 3/5/2006, when this code executes, the value of `book` is:</span></span>  
  
```xml  
<book category="fiction" isbn="12345">  
  <modifiedDate>3/5/2006</modifiedDate>  
</book>  
```  
  
## <a name="embedded-expression-location-and-validation"></a><span data-ttu-id="27e8d-107">埋め込み式の位置と検証</span><span class="sxs-lookup"><span data-stu-id="27e8d-107">Embedded Expression Location and Validation</span></span>  
 <span data-ttu-id="27e8d-108">埋め込み式は、XML リテラル式内の特定の場所でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="27e8d-108">Embedded expressions can appear only at certain locations within XML literal expressions.</span></span> <span data-ttu-id="27e8d-109">式の場所は、式が返すことができる型と `Nothing` の処理方法を制御します。</span><span class="sxs-lookup"><span data-stu-id="27e8d-109">The expression location controls which types the expression can return and how `Nothing` is handled.</span></span> <span data-ttu-id="27e8d-110">次の表では、埋め込み式の許可される場所と型について説明します。</span><span class="sxs-lookup"><span data-stu-id="27e8d-110">The following table describes the allowed locations and types of embedded expressions.</span></span>  
  
|<span data-ttu-id="27e8d-111">リテラル内の場所</span><span class="sxs-lookup"><span data-stu-id="27e8d-111">Location in literal</span></span>|<span data-ttu-id="27e8d-112">式の種類</span><span class="sxs-lookup"><span data-stu-id="27e8d-112">Type of expression</span></span>|<span data-ttu-id="27e8d-113">`Nothing` の処理</span><span class="sxs-lookup"><span data-stu-id="27e8d-113">Handling of `Nothing`</span></span>|  
|---|---|---|  
|<span data-ttu-id="27e8d-114">XML 要素名</span><span class="sxs-lookup"><span data-stu-id="27e8d-114">XML element name</span></span>|<xref:System.Xml.Linq.XName>|<span data-ttu-id="27e8d-115">エラー</span><span class="sxs-lookup"><span data-stu-id="27e8d-115">Error</span></span>|  
|<span data-ttu-id="27e8d-116">XML 要素のコンテンツ</span><span class="sxs-lookup"><span data-stu-id="27e8d-116">XML element content</span></span>|<span data-ttu-id="27e8d-117">`Object` または `Object` の配列</span><span class="sxs-lookup"><span data-stu-id="27e8d-117">`Object` or array of `Object`</span></span>|<span data-ttu-id="27e8d-118">無視</span><span class="sxs-lookup"><span data-stu-id="27e8d-118">Ignored</span></span>|  
|<span data-ttu-id="27e8d-119">XML 要素の属性名</span><span class="sxs-lookup"><span data-stu-id="27e8d-119">XML element attribute name</span></span>|<xref:System.Xml.Linq.XName>|<span data-ttu-id="27e8d-120">属性値も `Nothing` ない限り、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="27e8d-120">Error, unless the attribute value is also `Nothing`</span></span>|  
|<span data-ttu-id="27e8d-121">XML 要素の属性値</span><span class="sxs-lookup"><span data-stu-id="27e8d-121">XML element attribute value</span></span>|`Object`|<span data-ttu-id="27e8d-122">属性宣言が無視されました</span><span class="sxs-lookup"><span data-stu-id="27e8d-122">Attribute declaration ignored</span></span>|  
|<span data-ttu-id="27e8d-123">XML 要素属性</span><span class="sxs-lookup"><span data-stu-id="27e8d-123">XML element attribute</span></span>|<span data-ttu-id="27e8d-124"><xref:System.Xml.Linq.XAttribute> または <xref:System.Xml.Linq.XAttribute> のコレクション</span><span class="sxs-lookup"><span data-stu-id="27e8d-124"><xref:System.Xml.Linq.XAttribute> or a collection of <xref:System.Xml.Linq.XAttribute></span></span>|<span data-ttu-id="27e8d-125">無視</span><span class="sxs-lookup"><span data-stu-id="27e8d-125">Ignored</span></span>|  
|<span data-ttu-id="27e8d-126">XML ドキュメントのルート要素</span><span class="sxs-lookup"><span data-stu-id="27e8d-126">XML document root element</span></span>|<span data-ttu-id="27e8d-127"><xref:System.Xml.Linq.XElement> または1つの <xref:System.Xml.Linq.XElement> オブジェクトと、任意の数の <xref:System.Xml.Linq.XProcessingInstruction> および <xref:System.Xml.Linq.XComment> オブジェクトのコレクション</span><span class="sxs-lookup"><span data-stu-id="27e8d-127"><xref:System.Xml.Linq.XElement> or a collection of one <xref:System.Xml.Linq.XElement> object and an arbitrary number of <xref:System.Xml.Linq.XProcessingInstruction> and <xref:System.Xml.Linq.XComment> objects</span></span>|<span data-ttu-id="27e8d-128">無視</span><span class="sxs-lookup"><span data-stu-id="27e8d-128">Ignored</span></span>|  
  
- <span data-ttu-id="27e8d-129">XML 要素名の埋め込み式の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="27e8d-129">Example of an embedded expression in an XML element name:</span></span>  
  
     [!code-vb[VbXMLSamples#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#32)]  
  
- <span data-ttu-id="27e8d-130">XML 要素のコンテンツ内の埋め込み式の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="27e8d-130">Example of an embedded expression in the content of an XML element:</span></span>  
  
     [!code-vb[VbXMLSamples#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#33)]  
  
- <span data-ttu-id="27e8d-131">XML 要素の属性名に含まれる埋め込み式の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="27e8d-131">Example of an embedded expression in an XML element attribute name:</span></span>  
  
     [!code-vb[VbXMLSamples#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#34)]  
  
- <span data-ttu-id="27e8d-132">XML 要素の属性値に含まれる埋め込み式の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="27e8d-132">Example of an embedded expression in an XML element attribute value:</span></span>  
  
     [!code-vb[VbXMLSamples#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#35)]  
  
- <span data-ttu-id="27e8d-133">XML 要素属性の埋め込み式の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="27e8d-133">Example of an embedded expression in an XML element attribute:</span></span>  
  
     [!code-vb[VbXMLSamples#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#36)]  
  
- <span data-ttu-id="27e8d-134">XML ドキュメントのルート要素内の埋め込み式の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="27e8d-134">Example of an embedded expression in an XML document root element:</span></span>  
  
     [!code-vb[VbXMLSamples#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#37)]  
  
 <span data-ttu-id="27e8d-135">`Option Strict`を有効にした場合、コンパイラは、埋め込み式の型が必要な型に拡大変換されるかどうかをチェックします。</span><span class="sxs-lookup"><span data-stu-id="27e8d-135">If you enable `Option Strict`, the compiler checks that the type of each embedded expression widens to the required type.</span></span> <span data-ttu-id="27e8d-136">唯一の例外は、コードの実行時に検証される XML ドキュメントのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="27e8d-136">The only exception is for the root element of an XML document, which is verified when the code runs.</span></span> <span data-ttu-id="27e8d-137">`Option Strict`せずにコンパイルする場合は `Object` 型の式を埋め込むことができ、その型は実行時に検証されます。</span><span class="sxs-lookup"><span data-stu-id="27e8d-137">If you compile without `Option Strict`, you can embed expressions of type `Object` and their type is verified at run time.</span></span>  
  
 <span data-ttu-id="27e8d-138">コンテンツが省略可能な場所では、`Nothing` を含む埋め込み式は無視されます。</span><span class="sxs-lookup"><span data-stu-id="27e8d-138">In locations where content is optional, embedded expressions that contain `Nothing` are ignored.</span></span> <span data-ttu-id="27e8d-139">これは、XML リテラルを使用する前に、要素の内容、属性値、および配列要素が `Nothing` ないことを確認する必要がないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="27e8d-139">This means you do not have to check that element content, attribute values, and array elements are not `Nothing` before you use an XML literal.</span></span> <span data-ttu-id="27e8d-140">要素名や属性名などの必須の値を `Nothing`することはできません。</span><span class="sxs-lookup"><span data-stu-id="27e8d-140">Required values, such as element and attribute names, cannot be `Nothing`.</span></span>  
  
 <span data-ttu-id="27e8d-141">特定の型のリテラルで埋め込み式を使用する方法の詳細については、「[XML ドキュメントリテラル](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)、 [XML 要素リテラル](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="27e8d-141">For more information about using an embedded expression in a particular type of literal, see [XML Document Literal](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md), [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span></span>  
  
## <a name="scoping-rules"></a><span data-ttu-id="27e8d-142">スコープの規則</span><span class="sxs-lookup"><span data-stu-id="27e8d-142">Scoping Rules</span></span>  
 <span data-ttu-id="27e8d-143">コンパイラは、各 XML リテラルを適切なリテラル型のコンストラクター呼び出しに変換します。</span><span class="sxs-lookup"><span data-stu-id="27e8d-143">The compiler converts each XML literal into a constructor call for the appropriate literal type.</span></span> <span data-ttu-id="27e8d-144">XML リテラル内のリテラルコンテンツと埋め込み式は、引数としてコンストラクターに渡されます。</span><span class="sxs-lookup"><span data-stu-id="27e8d-144">The literal content and embedded expressions in an XML literal are passed as arguments to the constructor.</span></span> <span data-ttu-id="27e8d-145">これは、XML リテラルで使用できるすべての Visual Basic プログラミング要素も、その埋め込み式で使用できることを意味します。</span><span class="sxs-lookup"><span data-stu-id="27e8d-145">This means that all Visual Basic programming elements available to an XML literal are also available to its embedded expressions.</span></span>  
  
 <span data-ttu-id="27e8d-146">XML リテラル内では、`Imports` ステートメントで宣言された XML 名前空間プレフィックスにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="27e8d-146">Within an XML literal, you can access the XML namespace prefixes declared with the `Imports` statement.</span></span> <span data-ttu-id="27e8d-147">`xmlns` 属性を使用して、新しい XML 名前空間プレフィックスを宣言したり、既存の XML 名前空間プレフィックスを要素内にシャドウしたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="27e8d-147">You can declare a new XML namespace prefix, or shadow an existing XML namespace prefix, in an element by using the `xmlns` attribute.</span></span> <span data-ttu-id="27e8d-148">新しい名前空間は、その要素の子ノードでは使用できますが、埋め込み式の XML リテラルには使用できません。</span><span class="sxs-lookup"><span data-stu-id="27e8d-148">The new namespace is available to the child nodes of that element, but not to XML literals in embedded expressions.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="27e8d-149">`xmlns` namespace 属性を使用して XML 名前空間プレフィックスを宣言する場合、属性値は定数文字列である必要があります。</span><span class="sxs-lookup"><span data-stu-id="27e8d-149">When you declare an XML namespace prefix by using the `xmlns` namespace attribute, the attribute value must be a constant string.</span></span> <span data-ttu-id="27e8d-150">この点で、`xmlns` 属性の使用は、`Imports` ステートメントを使用して XML 名前空間を宣言するのと似ています。</span><span class="sxs-lookup"><span data-stu-id="27e8d-150">In this regard, using the `xmlns` attribute is like using the `Imports` statement to declare an XML namespace.</span></span> <span data-ttu-id="27e8d-151">埋め込み式を使用して XML 名前空間の値を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="27e8d-151">You cannot use an embedded expression to specify the XML namespace value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27e8d-152">参照</span><span class="sxs-lookup"><span data-stu-id="27e8d-152">See also</span></span>

- [<span data-ttu-id="27e8d-153">Visual Basic での XML の作成</span><span class="sxs-lookup"><span data-stu-id="27e8d-153">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="27e8d-154">XML ドキュメント リテラル</span><span class="sxs-lookup"><span data-stu-id="27e8d-154">XML Document Literal</span></span>](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)
- [<span data-ttu-id="27e8d-155">XML 要素リテラル</span><span class="sxs-lookup"><span data-stu-id="27e8d-155">XML Element Literal</span></span>](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [<span data-ttu-id="27e8d-156">Option Strict ステートメント</span><span class="sxs-lookup"><span data-stu-id="27e8d-156">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="27e8d-157">Imports ステートメント (.NET 名前空間および型)</span><span class="sxs-lookup"><span data-stu-id="27e8d-157">Imports Statement (.NET Namespace and Type)</span></span>](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [<span data-ttu-id="27e8d-158">XML リテラルの概要</span><span class="sxs-lookup"><span data-stu-id="27e8d-158">XML Literals Overview</span></span>](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-overview.md)
