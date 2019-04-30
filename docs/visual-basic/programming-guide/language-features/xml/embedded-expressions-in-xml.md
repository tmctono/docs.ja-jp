---
title: XML での埋め込み式 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlEmbeddedExpression
helpviewer_keywords:
- embedded expressions [Visual Basic]
- LINQ to XML [Visual Basic], embedded expressions
- XML literals [Visual Basic], embedded expressions
ms.assetid: bf2eb779-b751-4b7c-854f-9f2161482352
ms.openlocfilehash: 4c96665994a7e56bc70f72b66d5922f5a6472a13
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61961228"
---
# <a name="embedded-expressions-in-xml-visual-basic"></a><span data-ttu-id="d3133-102">XML での埋め込み式 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d3133-102">Embedded Expressions in XML (Visual Basic)</span></span>
<span data-ttu-id="d3133-103">埋め込み式を使用すると、実行時に評価される式が含まれる XML リテラルを作成できます。</span><span class="sxs-lookup"><span data-stu-id="d3133-103">Embedded expressions enable you to create XML literals that contain expressions that are evaluated at run time.</span></span> <span data-ttu-id="d3133-104">埋め込み式の構文は、 `<%=` `expression` `%>`で使用するための構文は同じ[!INCLUDE[vstecasp](~/includes/vstecasp-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="d3133-104">The syntax for an embedded expression is `<%=` `expression` `%>`, which is the same as the syntax used in [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)].</span></span>  
  
 <span data-ttu-id="d3133-105">などを作成する XML 要素リテラルには、埋め込み式のリテラル テキストの内容とを組み合わせることです。</span><span class="sxs-lookup"><span data-stu-id="d3133-105">For example, you can create an XML element literal, combining embedded expressions with literal text content.</span></span>  
  
 [!code-vb[VbXMLSamples#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#27)]  
  
 <span data-ttu-id="d3133-106">場合`isbnNumber`12345 整数が含まれると`modifiedDate`、日付が含まれる 3/5/2006、このコードが実行される場合、値の`book`は。</span><span class="sxs-lookup"><span data-stu-id="d3133-106">If `isbnNumber` contains the integer 12345 and `modifiedDate` contains the date 3/5/2006, when this code executes, the value of `book` is:</span></span>  
  
```xml  
<book category="fiction" isbn="12345">  
  <modifiedDate>3/5/2006</modifiedDate>  
</book>  
```  
  
## <a name="embedded-expression-location-and-validation"></a><span data-ttu-id="d3133-107">埋め込み式の位置と検証</span><span class="sxs-lookup"><span data-stu-id="d3133-107">Embedded Expression Location and Validation</span></span>  
 <span data-ttu-id="d3133-108">埋め込み式は、XML リテラル式の中で特定の場所でのみ記述できます。</span><span class="sxs-lookup"><span data-stu-id="d3133-108">Embedded expressions can appear only at certain locations within XML literal expressions.</span></span> <span data-ttu-id="d3133-109">式の型が式の場所のコントロールを返すことができ、どのように`Nothing`処理されます。</span><span class="sxs-lookup"><span data-stu-id="d3133-109">The expression location controls which types the expression can return and how `Nothing` is handled.</span></span> <span data-ttu-id="d3133-110">次の表では、許可されている場所と埋め込み式の型について説明します。</span><span class="sxs-lookup"><span data-stu-id="d3133-110">The following table describes the allowed locations and types of embedded expressions.</span></span>  
  
|<span data-ttu-id="d3133-111">リテラル内の場所</span><span class="sxs-lookup"><span data-stu-id="d3133-111">Location in literal</span></span>|<span data-ttu-id="d3133-112">式の型</span><span class="sxs-lookup"><span data-stu-id="d3133-112">Type of expression</span></span>|<span data-ttu-id="d3133-113">処理 `Nothing`</span><span class="sxs-lookup"><span data-stu-id="d3133-113">Handling of `Nothing`</span></span>|  
|---|---|---|  
|<span data-ttu-id="d3133-114">XML 要素名</span><span class="sxs-lookup"><span data-stu-id="d3133-114">XML element name</span></span>|<xref:System.Xml.Linq.XName>|<span data-ttu-id="d3133-115">Error</span><span class="sxs-lookup"><span data-stu-id="d3133-115">Error</span></span>|  
|<span data-ttu-id="d3133-116">XML 要素のコンテンツ</span><span class="sxs-lookup"><span data-stu-id="d3133-116">XML element content</span></span>|<span data-ttu-id="d3133-117">`Object` またはの配列 `Object`</span><span class="sxs-lookup"><span data-stu-id="d3133-117">`Object` or array of `Object`</span></span>|<span data-ttu-id="d3133-118">無視</span><span class="sxs-lookup"><span data-stu-id="d3133-118">Ignored</span></span>|  
|<span data-ttu-id="d3133-119">XML 要素の属性名</span><span class="sxs-lookup"><span data-stu-id="d3133-119">XML element attribute name</span></span>|<xref:System.Xml.Linq.XName>|<span data-ttu-id="d3133-120">エラー、属性の値もしない限り、 `Nothing`</span><span class="sxs-lookup"><span data-stu-id="d3133-120">Error, unless the attribute value is also `Nothing`</span></span>|  
|<span data-ttu-id="d3133-121">XML 要素の属性値</span><span class="sxs-lookup"><span data-stu-id="d3133-121">XML element attribute value</span></span>|`Object`|<span data-ttu-id="d3133-122">属性宣言を無視します</span><span class="sxs-lookup"><span data-stu-id="d3133-122">Attribute declaration ignored</span></span>|  
|<span data-ttu-id="d3133-123">XML 要素の属性</span><span class="sxs-lookup"><span data-stu-id="d3133-123">XML element attribute</span></span>|<span data-ttu-id="d3133-124"><xref:System.Xml.Linq.XAttribute> またはのコレクション <xref:System.Xml.Linq.XAttribute></span><span class="sxs-lookup"><span data-stu-id="d3133-124"><xref:System.Xml.Linq.XAttribute> or a collection of <xref:System.Xml.Linq.XAttribute></span></span>|<span data-ttu-id="d3133-125">無視</span><span class="sxs-lookup"><span data-stu-id="d3133-125">Ignored</span></span>|  
|<span data-ttu-id="d3133-126">XML ドキュメントのルート要素</span><span class="sxs-lookup"><span data-stu-id="d3133-126">XML document root element</span></span>|<span data-ttu-id="d3133-127"><xref:System.Xml.Linq.XElement> いずれかのコレクションまたは<xref:System.Xml.Linq.XElement>オブジェクトと任意の数の<xref:System.Xml.Linq.XProcessingInstruction>と<xref:System.Xml.Linq.XComment>オブジェクト</span><span class="sxs-lookup"><span data-stu-id="d3133-127"><xref:System.Xml.Linq.XElement> or a collection of one <xref:System.Xml.Linq.XElement> object and an arbitrary number of <xref:System.Xml.Linq.XProcessingInstruction> and <xref:System.Xml.Linq.XComment> objects</span></span>|<span data-ttu-id="d3133-128">無視</span><span class="sxs-lookup"><span data-stu-id="d3133-128">Ignored</span></span>|  
  
- <span data-ttu-id="d3133-129">XML 要素名での埋め込み式の例:</span><span class="sxs-lookup"><span data-stu-id="d3133-129">Example of an embedded expression in an XML element name:</span></span>  
  
     [!code-vb[VbXMLSamples#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#32)]  
  
- <span data-ttu-id="d3133-130">XML 要素のコンテンツの埋め込み式の例:</span><span class="sxs-lookup"><span data-stu-id="d3133-130">Example of an embedded expression in the content of an XML element:</span></span>  
  
     [!code-vb[VbXMLSamples#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#33)]  
  
- <span data-ttu-id="d3133-131">XML 要素の属性名での埋め込み式の例:</span><span class="sxs-lookup"><span data-stu-id="d3133-131">Example of an embedded expression in an XML element attribute name:</span></span>  
  
     [!code-vb[VbXMLSamples#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#34)]  
  
- <span data-ttu-id="d3133-132">XML 要素の属性値内の埋め込み式の例:</span><span class="sxs-lookup"><span data-stu-id="d3133-132">Example of an embedded expression in an XML element attribute value:</span></span>  
  
     [!code-vb[VbXMLSamples#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#35)]  
  
- <span data-ttu-id="d3133-133">XML 要素の属性での埋め込み式の例:</span><span class="sxs-lookup"><span data-stu-id="d3133-133">Example of an embedded expression in an XML element attribute:</span></span>  
  
     [!code-vb[VbXMLSamples#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#36)]  
  
- <span data-ttu-id="d3133-134">XML ドキュメントのルート要素の埋め込み式の例:</span><span class="sxs-lookup"><span data-stu-id="d3133-134">Example of an embedded expression in an XML document root element:</span></span>  
  
     [!code-vb[VbXMLSamples#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#37)]  
  
 <span data-ttu-id="d3133-135">有効にした場合`Option Strict`コンパイラは各埋め込み式の型が必要な型に拡大変換を確認します。</span><span class="sxs-lookup"><span data-stu-id="d3133-135">If you enable `Option Strict`, the compiler checks that the type of each embedded expression widens to the required type.</span></span> <span data-ttu-id="d3133-136">唯一の例外は、コードの実行時に検証される XML ドキュメントのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="d3133-136">The only exception is for the root element of an XML document, which is verified when the code runs.</span></span> <span data-ttu-id="d3133-137">せずにコンパイルする場合`Option Strict`、型の式を埋め込むことができます`Object`し、型が実行時に検証されます。</span><span class="sxs-lookup"><span data-stu-id="d3133-137">If you compile without `Option Strict`, you can embed expressions of type `Object` and their type is verified at run time.</span></span>  
  
 <span data-ttu-id="d3133-138">コンテンツが、省略可能な場所で埋め込み式が含まれている`Nothing`は無視されます。</span><span class="sxs-lookup"><span data-stu-id="d3133-138">In locations where content is optional, embedded expressions that contain `Nothing` are ignored.</span></span> <span data-ttu-id="d3133-139">これは、その要素のコンテンツの属性の値を確認する必要はありませんし、配列の要素がないことを意味`Nothing`XML リテラルを使用する前にします。</span><span class="sxs-lookup"><span data-stu-id="d3133-139">This means you do not have to check that element content, attribute values, and array elements are not `Nothing` before you use an XML literal.</span></span> <span data-ttu-id="d3133-140">要素および属性の名前などの値にすることはできません必要な`Nothing`します。</span><span class="sxs-lookup"><span data-stu-id="d3133-140">Required values, such as element and attribute names, cannot be `Nothing`.</span></span>  
  
 <span data-ttu-id="d3133-141">特定の種類のリテラルでの埋め込み式の使用に関する詳細については、次を参照してください。 [XML ドキュメント リテラル](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)、 [XML 要素リテラル](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)します。</span><span class="sxs-lookup"><span data-stu-id="d3133-141">For more information about using an embedded expression in a particular type of literal, see [XML Document Literal](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md), [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span></span>  
  
## <a name="scoping-rules"></a><span data-ttu-id="d3133-142">スコープの規則</span><span class="sxs-lookup"><span data-stu-id="d3133-142">Scoping Rules</span></span>  
 <span data-ttu-id="d3133-143">コンパイラは、各 XML リテラルを適切なリテラルの型のコンス トラクターの呼び出しに変換します。</span><span class="sxs-lookup"><span data-stu-id="d3133-143">The compiler converts each XML literal into a constructor call for the appropriate literal type.</span></span> <span data-ttu-id="d3133-144">リテラルの内容と、XML リテラルでの埋め込み式は、コンス トラクターに引数として渡されます。</span><span class="sxs-lookup"><span data-stu-id="d3133-144">The literal content and embedded expressions in an XML literal are passed as arguments to the constructor.</span></span> <span data-ttu-id="d3133-145">つまり、すべて Visual Basic プログラミング要素、XML リテラルに使用できますが、埋め込み式を使用できるもこと。</span><span class="sxs-lookup"><span data-stu-id="d3133-145">This means that all Visual Basic programming elements available to an XML literal are also available to its embedded expressions.</span></span>  
  
 <span data-ttu-id="d3133-146">XML リテラル内でプレフィックスが宣言されている XML 名前空間をアクセスすることができます、`Imports`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="d3133-146">Within an XML literal, you can access the XML namespace prefixes declared with the `Imports` statement.</span></span> <span data-ttu-id="d3133-147">新しい XML 名前空間プレフィックスを宣言したり、シャドウする要素を使用して、既存 XML 名前空間プレフィックス、`xmlns`属性。</span><span class="sxs-lookup"><span data-stu-id="d3133-147">You can declare a new XML namespace prefix, or shadow an existing XML namespace prefix, in an element by using the `xmlns` attribute.</span></span> <span data-ttu-id="d3133-148">新しい名前空間は埋め込み式の XML リテラルではなく、その要素の子ノードに使用できます。</span><span class="sxs-lookup"><span data-stu-id="d3133-148">The new namespace is available to the child nodes of that element, but not to XML literals in embedded expressions.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d3133-149">使用して XML 名前空間プレフィックスを宣言する場合、`xmlns`名前空間の属性、属性値に定数文字列を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d3133-149">When you declare an XML namespace prefix by using the `xmlns` namespace attribute, the attribute value must be a constant string.</span></span> <span data-ttu-id="d3133-150">この点を使用して、`xmlns`属性は使用と同様、 `Imports` XML 名前空間を宣言するステートメント。</span><span class="sxs-lookup"><span data-stu-id="d3133-150">In this regard, using the `xmlns` attribute is like using the `Imports` statement to declare an XML namespace.</span></span> <span data-ttu-id="d3133-151">埋め込み式を使用して、XML 名前空間の値を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="d3133-151">You cannot use an embedded expression to specify the XML namespace value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3133-152">関連項目</span><span class="sxs-lookup"><span data-stu-id="d3133-152">See also</span></span>

- [<span data-ttu-id="d3133-153">Visual Basic での XML の作成</span><span class="sxs-lookup"><span data-stu-id="d3133-153">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="d3133-154">XML ドキュメント リテラル</span><span class="sxs-lookup"><span data-stu-id="d3133-154">XML Document Literal</span></span>](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)
- [<span data-ttu-id="d3133-155">XML 要素リテラル</span><span class="sxs-lookup"><span data-stu-id="d3133-155">XML Element Literal</span></span>](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [<span data-ttu-id="d3133-156">Option Strict ステートメント</span><span class="sxs-lookup"><span data-stu-id="d3133-156">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="d3133-157">Imports ステートメント (.NET 名前空間および型)</span><span class="sxs-lookup"><span data-stu-id="d3133-157">Imports Statement (.NET Namespace and Type)</span></span>](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [<span data-ttu-id="d3133-158">XML リテラルの概要</span><span class="sxs-lookup"><span data-stu-id="d3133-158">XML Literals Overview</span></span>](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-overview.md)
