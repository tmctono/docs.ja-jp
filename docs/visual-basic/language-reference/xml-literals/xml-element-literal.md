---
title: XML 要素リテラル
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralElement
helpviewer_keywords:
- XML element literal [Visual Basic]
- element literal [Visual Basic]
- XML literals [Visual Basic], element
ms.assetid: 95039642-7893-48b7-b23f-45a6c55d8f67
ms.openlocfilehash: d6d900ca6868cfffe6b0e5b349321a79c5716c46
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347027"
---
# <a name="xml-element-literal-visual-basic"></a><span data-ttu-id="c1b4d-102">XML 要素リテラル (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c1b4d-102">XML Element Literal (Visual Basic)</span></span>

<span data-ttu-id="c1b4d-103">A literal that represents an <xref:System.Xml.Linq.XElement> object.</span><span class="sxs-lookup"><span data-stu-id="c1b4d-103">A literal that represents an <xref:System.Xml.Linq.XElement> object.</span></span>

## <a name="syntax"></a><span data-ttu-id="c1b4d-104">構文</span><span class="sxs-lookup"><span data-stu-id="c1b4d-104">Syntax</span></span>

```xml
<name [ attributeList ] />
-or-
<name [ attributeList ] > [ elementContents ] </[ name ]>
```

## <a name="parts"></a><span data-ttu-id="c1b4d-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="c1b4d-105">Parts</span></span>

- `<`

  <span data-ttu-id="c1b4d-106">必須です。</span><span class="sxs-lookup"><span data-stu-id="c1b4d-106">Required.</span></span> <span data-ttu-id="c1b4d-107">Opens the starting element tag.</span><span class="sxs-lookup"><span data-stu-id="c1b4d-107">Opens the starting element tag.</span></span>

- `name`

  <span data-ttu-id="c1b4d-108">必須です。</span><span class="sxs-lookup"><span data-stu-id="c1b4d-108">Required.</span></span> <span data-ttu-id="c1b4d-109">要素名</span><span class="sxs-lookup"><span data-stu-id="c1b4d-109">Name of the element.</span></span> <span data-ttu-id="c1b4d-110">The format is one of the following:</span><span class="sxs-lookup"><span data-stu-id="c1b4d-110">The format is one of the following:</span></span>

  - <span data-ttu-id="c1b4d-111">Literal text for the element name, of the form `[ePrefix:]eName`, where:</span><span class="sxs-lookup"><span data-stu-id="c1b4d-111">Literal text for the element name, of the form `[ePrefix:]eName`, where:</span></span>

    |<span data-ttu-id="c1b4d-112">パーツ</span><span class="sxs-lookup"><span data-stu-id="c1b4d-112">Part</span></span>|<span data-ttu-id="c1b4d-113">説明</span><span class="sxs-lookup"><span data-stu-id="c1b4d-113">Description</span></span>|
    |---|---|
    |`ePrefix`|<span data-ttu-id="c1b4d-114">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="c1b4d-114">Optional.</span></span> <span data-ttu-id="c1b4d-115">XML namespace prefix for the element.</span><span class="sxs-lookup"><span data-stu-id="c1b4d-115">XML namespace prefix for the element.</span></span> <span data-ttu-id="c1b4d-116">Must be a global XML namespace that is defined with an `Imports` statement in the file or at the project level, or a local XML namespace that is defined in this element or a parent element.</span><span class="sxs-lookup"><span data-stu-id="c1b4d-116">Must be a global XML namespace that is defined with an `Imports` statement in the file or at the project level, or a local XML namespace that is defined in this element or a parent element.</span></span>|
    |`eName`|<span data-ttu-id="c1b4d-117">必須です。</span><span class="sxs-lookup"><span data-stu-id="c1b4d-117">Required.</span></span> <span data-ttu-id="c1b4d-118">要素名</span><span class="sxs-lookup"><span data-stu-id="c1b4d-118">Name of the element.</span></span> <span data-ttu-id="c1b4d-119">The format is one of the following:</span><span class="sxs-lookup"><span data-stu-id="c1b4d-119">The format is one of the following:</span></span><br /><br /> <span data-ttu-id="c1b4d-120">- Literal text.</span><span class="sxs-lookup"><span data-stu-id="c1b4d-120">- Literal text.</span></span> <span data-ttu-id="c1b4d-121">See [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="c1b4d-121">See [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span><br /><span data-ttu-id="c1b4d-122">- Embedded expression of the form `<%= eNameExp %>`.</span><span class="sxs-lookup"><span data-stu-id="c1b4d-122">- Embedded expression of the form `<%= eNameExp %>`.</span></span> <span data-ttu-id="c1b4d-123">The type of `eNameExp` must be `String` or a type that is implicitly convertible to <xref:System.Xml.Linq.XName>.</span><span class="sxs-lookup"><span data-stu-id="c1b4d-123">The type of `eNameExp` must be `String` or a type that is implicitly convertible to <xref:System.Xml.Linq.XName>.</span></span>|

  - <span data-ttu-id="c1b4d-124">Embedded expression of the form `<%= nameExp %>`.</span><span class="sxs-lookup"><span data-stu-id="c1b4d-124">Embedded expression of the form `<%= nameExp %>`.</span></span> <span data-ttu-id="c1b4d-125">The type of `nameExp` must be `String` or a type implicitly convertible to <xref:System.Xml.Linq.XName>.</span><span class="sxs-lookup"><span data-stu-id="c1b4d-125">The type of `nameExp` must be `String` or a type implicitly convertible to <xref:System.Xml.Linq.XName>.</span></span> <span data-ttu-id="c1b4d-126">An embedded expression is not allowed in a closing tag of an element.</span><span class="sxs-lookup"><span data-stu-id="c1b4d-126">An embedded expression is not allowed in a closing tag of an element.</span></span>

- `attributeList`

  <span data-ttu-id="c1b4d-127">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="c1b4d-127">Optional.</span></span> <span data-ttu-id="c1b4d-128">List of attributes declared in the literal.</span><span class="sxs-lookup"><span data-stu-id="c1b4d-128">List of attributes declared in the literal.</span></span>

  `attribute [ attribute ... ]`

  <span data-ttu-id="c1b4d-129">Each `attribute` has one of the following syntaxes:</span><span class="sxs-lookup"><span data-stu-id="c1b4d-129">Each `attribute` has one of the following syntaxes:</span></span>

  - <span data-ttu-id="c1b4d-130">Attribute assignment, of the form `[aPrefix:]aName=aValue`, where:</span><span class="sxs-lookup"><span data-stu-id="c1b4d-130">Attribute assignment, of the form `[aPrefix:]aName=aValue`, where:</span></span>

    |<span data-ttu-id="c1b4d-131">パーツ</span><span class="sxs-lookup"><span data-stu-id="c1b4d-131">Part</span></span>|<span data-ttu-id="c1b4d-132">説明</span><span class="sxs-lookup"><span data-stu-id="c1b4d-132">Description</span></span>|
    |---|---|
    |`aPrefix`|<span data-ttu-id="c1b4d-133">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="c1b4d-133">Optional.</span></span> <span data-ttu-id="c1b4d-134">XML namespace prefix for the attribute.</span><span class="sxs-lookup"><span data-stu-id="c1b4d-134">XML namespace prefix for the attribute.</span></span> <span data-ttu-id="c1b4d-135">Must be a global XML namespace that is defined with an `Imports` statement, or a local XML namespace that is defined in this element or a parent element.</span><span class="sxs-lookup"><span data-stu-id="c1b4d-135">Must be a global XML namespace that is defined with an `Imports` statement, or a local XML namespace that is defined in this element or a parent element.</span></span>|
    |`aName`|<span data-ttu-id="c1b4d-136">必須です。</span><span class="sxs-lookup"><span data-stu-id="c1b4d-136">Required.</span></span> <span data-ttu-id="c1b4d-137">属性の名前。</span><span class="sxs-lookup"><span data-stu-id="c1b4d-137">Name of the attribute.</span></span> <span data-ttu-id="c1b4d-138">The format is one of the following:</span><span class="sxs-lookup"><span data-stu-id="c1b4d-138">The format is one of the following:</span></span><br /><br /> <span data-ttu-id="c1b4d-139">- Literal text.</span><span class="sxs-lookup"><span data-stu-id="c1b4d-139">- Literal text.</span></span> <span data-ttu-id="c1b4d-140">See [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="c1b4d-140">See [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span><br /><span data-ttu-id="c1b4d-141">- Embedded expression of the form `<%= aNameExp %>`.</span><span class="sxs-lookup"><span data-stu-id="c1b4d-141">- Embedded expression of the form `<%= aNameExp %>`.</span></span> <span data-ttu-id="c1b4d-142">The type of `aNameExp` must be `String` or a type that is implicitly convertible to <xref:System.Xml.Linq.XName>.</span><span class="sxs-lookup"><span data-stu-id="c1b4d-142">The type of `aNameExp` must be `String` or a type that is implicitly convertible to <xref:System.Xml.Linq.XName>.</span></span>|
    |`aValue`|<span data-ttu-id="c1b4d-143">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="c1b4d-143">Optional.</span></span> <span data-ttu-id="c1b4d-144">Value of the attribute.</span><span class="sxs-lookup"><span data-stu-id="c1b4d-144">Value of the attribute.</span></span> <span data-ttu-id="c1b4d-145">The format is one of the following:</span><span class="sxs-lookup"><span data-stu-id="c1b4d-145">The format is one of the following:</span></span><br /><br /> <span data-ttu-id="c1b4d-146">- Literal text, enclosed in quotation marks.</span><span class="sxs-lookup"><span data-stu-id="c1b4d-146">- Literal text, enclosed in quotation marks.</span></span><br /><span data-ttu-id="c1b4d-147">- Embedded expression of the form `<%= aValueExp %>`.</span><span class="sxs-lookup"><span data-stu-id="c1b4d-147">- Embedded expression of the form `<%= aValueExp %>`.</span></span> <span data-ttu-id="c1b4d-148">Any type is allowed.</span><span class="sxs-lookup"><span data-stu-id="c1b4d-148">Any type is allowed.</span></span>|

  - <span data-ttu-id="c1b4d-149">Embedded expression of the form `<%= aExp %>`.</span><span class="sxs-lookup"><span data-stu-id="c1b4d-149">Embedded expression of the form `<%= aExp %>`.</span></span>

- `/>`

  <span data-ttu-id="c1b4d-150">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="c1b4d-150">Optional.</span></span> <span data-ttu-id="c1b4d-151">Indicates that the element is an empty element, without content.</span><span class="sxs-lookup"><span data-stu-id="c1b4d-151">Indicates that the element is an empty element, without content.</span></span>

- `>`

  <span data-ttu-id="c1b4d-152">必須です。</span><span class="sxs-lookup"><span data-stu-id="c1b4d-152">Required.</span></span> <span data-ttu-id="c1b4d-153">Ends the beginning or empty element tag.</span><span class="sxs-lookup"><span data-stu-id="c1b4d-153">Ends the beginning or empty element tag.</span></span>

- `elementContents`

  <span data-ttu-id="c1b4d-154">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="c1b4d-154">Optional.</span></span> <span data-ttu-id="c1b4d-155">Content of the element.</span><span class="sxs-lookup"><span data-stu-id="c1b4d-155">Content of the element.</span></span>

  `content [ content ... ]`

  <span data-ttu-id="c1b4d-156">Each `content` can be one of the following:</span><span class="sxs-lookup"><span data-stu-id="c1b4d-156">Each `content` can be one of the following:</span></span>

  - <span data-ttu-id="c1b4d-157">Literal text.</span><span class="sxs-lookup"><span data-stu-id="c1b4d-157">Literal text.</span></span> <span data-ttu-id="c1b4d-158">All the white space in `elementContents` becomes significant if there is any literal text.</span><span class="sxs-lookup"><span data-stu-id="c1b4d-158">All the white space in `elementContents` becomes significant if there is any literal text.</span></span>

  - <span data-ttu-id="c1b4d-159">Embedded expression of the form `<%= contentExp %>`.</span><span class="sxs-lookup"><span data-stu-id="c1b4d-159">Embedded expression of the form `<%= contentExp %>`.</span></span>

  - <span data-ttu-id="c1b4d-160">XML element literal.</span><span class="sxs-lookup"><span data-stu-id="c1b4d-160">XML element literal.</span></span>

  - <span data-ttu-id="c1b4d-161">XML comment literal.</span><span class="sxs-lookup"><span data-stu-id="c1b4d-161">XML comment literal.</span></span> <span data-ttu-id="c1b4d-162">See [XML Comment Literal](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).</span><span class="sxs-lookup"><span data-stu-id="c1b4d-162">See [XML Comment Literal](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).</span></span>

  - <span data-ttu-id="c1b4d-163">XML processing instruction literal.</span><span class="sxs-lookup"><span data-stu-id="c1b4d-163">XML processing instruction literal.</span></span> <span data-ttu-id="c1b4d-164">See [XML Processing Instruction Literal](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).</span><span class="sxs-lookup"><span data-stu-id="c1b4d-164">See [XML Processing Instruction Literal](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).</span></span>

  - <span data-ttu-id="c1b4d-165">XML CDATA literal.</span><span class="sxs-lookup"><span data-stu-id="c1b4d-165">XML CDATA literal.</span></span> <span data-ttu-id="c1b4d-166">See [XML CDATA Literal](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md).</span><span class="sxs-lookup"><span data-stu-id="c1b4d-166">See [XML CDATA Literal](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md).</span></span>

- `</[name]>`

  <span data-ttu-id="c1b4d-167">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="c1b4d-167">Optional.</span></span> <span data-ttu-id="c1b4d-168">Represents the closing tag for the element.</span><span class="sxs-lookup"><span data-stu-id="c1b4d-168">Represents the closing tag for the element.</span></span> <span data-ttu-id="c1b4d-169">The optional `name` parameter is not allowed when it is the result of an embedded expression.</span><span class="sxs-lookup"><span data-stu-id="c1b4d-169">The optional `name` parameter is not allowed when it is the result of an embedded expression.</span></span>

## <a name="return-value"></a><span data-ttu-id="c1b4d-170">戻り値</span><span class="sxs-lookup"><span data-stu-id="c1b4d-170">Return Value</span></span>

<span data-ttu-id="c1b4d-171"><xref:System.Xml.Linq.XElement> オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="c1b4d-171">An <xref:System.Xml.Linq.XElement> object.</span></span>

## <a name="remarks"></a><span data-ttu-id="c1b4d-172">Remarks</span><span class="sxs-lookup"><span data-stu-id="c1b4d-172">Remarks</span></span>

<span data-ttu-id="c1b4d-173">You can use the XML element literal syntax to create <xref:System.Xml.Linq.XElement> objects in your code.</span><span class="sxs-lookup"><span data-stu-id="c1b4d-173">You can use the XML element literal syntax to create <xref:System.Xml.Linq.XElement> objects in your code.</span></span>

> [!NOTE]
> <span data-ttu-id="c1b4d-174">An XML literal can span multiple lines without using line continuation characters.</span><span class="sxs-lookup"><span data-stu-id="c1b4d-174">An XML literal can span multiple lines without using line continuation characters.</span></span> <span data-ttu-id="c1b4d-175">This feature enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span><span class="sxs-lookup"><span data-stu-id="c1b4d-175">This feature enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>

<span data-ttu-id="c1b4d-176">Embedded expressions of the form `<%= exp %>` enable you to add dynamic information to an XML element literal.</span><span class="sxs-lookup"><span data-stu-id="c1b4d-176">Embedded expressions of the form `<%= exp %>` enable you to add dynamic information to an XML element literal.</span></span> <span data-ttu-id="c1b4d-177">For more information, see [Embedded Expressions in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span><span class="sxs-lookup"><span data-stu-id="c1b4d-177">For more information, see [Embedded Expressions in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span></span>

<span data-ttu-id="c1b4d-178">The Visual Basic compiler converts the XML element literal into calls to the <xref:System.Xml.Linq.XElement.%23ctor%2A> constructor and, if it is required, the <xref:System.Xml.Linq.XAttribute.%23ctor%2A> constructor.</span><span class="sxs-lookup"><span data-stu-id="c1b4d-178">The Visual Basic compiler converts the XML element literal into calls to the <xref:System.Xml.Linq.XElement.%23ctor%2A> constructor and, if it is required, the <xref:System.Xml.Linq.XAttribute.%23ctor%2A> constructor.</span></span>

## <a name="xml-namespaces"></a><span data-ttu-id="c1b4d-179">XML 名前空間</span><span class="sxs-lookup"><span data-stu-id="c1b4d-179">XML Namespaces</span></span>

<span data-ttu-id="c1b4d-180">XML namespace prefixes are useful when you have to create XML literals with elements from the same namespace many times in code.</span><span class="sxs-lookup"><span data-stu-id="c1b4d-180">XML namespace prefixes are useful when you have to create XML literals with elements from the same namespace many times in code.</span></span> <span data-ttu-id="c1b4d-181">You can use global XML namespace prefixes, which you define by using the `Imports` statement, or local prefixes, which you define by using the `xmlns:xmlPrefix="xmlNamespace"` attribute syntax.</span><span class="sxs-lookup"><span data-stu-id="c1b4d-181">You can use global XML namespace prefixes, which you define by using the `Imports` statement, or local prefixes, which you define by using the `xmlns:xmlPrefix="xmlNamespace"` attribute syntax.</span></span> <span data-ttu-id="c1b4d-182">For more information, see [Imports Statement (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="c1b4d-182">For more information, see [Imports Statement (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span></span>

<span data-ttu-id="c1b4d-183">In accordance with the scoping rules for XML namespaces, local prefixes take precedence over global prefixes.</span><span class="sxs-lookup"><span data-stu-id="c1b4d-183">In accordance with the scoping rules for XML namespaces, local prefixes take precedence over global prefixes.</span></span> <span data-ttu-id="c1b4d-184">However, if an XML literal defines an XML namespace, that namespace is not available to expressions that appear in an embedded expression.</span><span class="sxs-lookup"><span data-stu-id="c1b4d-184">However, if an XML literal defines an XML namespace, that namespace is not available to expressions that appear in an embedded expression.</span></span> <span data-ttu-id="c1b4d-185">The embedded expression can access only the global XML namespace.</span><span class="sxs-lookup"><span data-stu-id="c1b4d-185">The embedded expression can access only the global XML namespace.</span></span>

<span data-ttu-id="c1b4d-186">The Visual Basic compiler converts each global XML namespace that is used by an XML literal into a one local namespace definition in the generated code.</span><span class="sxs-lookup"><span data-stu-id="c1b4d-186">The Visual Basic compiler converts each global XML namespace that is used by an XML literal into a one local namespace definition in the generated code.</span></span> <span data-ttu-id="c1b4d-187">Global XML namespaces that are not used do not appear in the generated code.</span><span class="sxs-lookup"><span data-stu-id="c1b4d-187">Global XML namespaces that are not used do not appear in the generated code.</span></span>

## <a name="example"></a><span data-ttu-id="c1b4d-188">例</span><span class="sxs-lookup"><span data-stu-id="c1b4d-188">Example</span></span>

<span data-ttu-id="c1b4d-189">The following example shows how to create a simple XML element that has two nested empty elements.</span><span class="sxs-lookup"><span data-stu-id="c1b4d-189">The following example shows how to create a simple XML element that has two nested empty elements.</span></span>

[!code-vb[VbXMLSamples#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples9.vb#20)]

<span data-ttu-id="c1b4d-190">The example displays the following text.</span><span class="sxs-lookup"><span data-stu-id="c1b4d-190">The example displays the following text.</span></span> <span data-ttu-id="c1b4d-191">Notice that the literal preserves the structure of the empty elements.</span><span class="sxs-lookup"><span data-stu-id="c1b4d-191">Notice that the literal preserves the structure of the empty elements.</span></span>

```xml
<outer>
  <inner1></inner1>
  <inner2 />
</outer>
```

## <a name="example"></a><span data-ttu-id="c1b4d-192">例</span><span class="sxs-lookup"><span data-stu-id="c1b4d-192">Example</span></span>

<span data-ttu-id="c1b4d-193">The following example shows how to use embedded expressions to name an element and create attributes.</span><span class="sxs-lookup"><span data-stu-id="c1b4d-193">The following example shows how to use embedded expressions to name an element and create attributes.</span></span>

[!code-vb[VbXMLSamples#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples9.vb#21)]

<span data-ttu-id="c1b4d-194">このコードを実行すると、次のテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c1b4d-194">This code displays the following text:</span></span>

```xml
<book isbn="1234" author="My Author" year="1999" title="My Book" />
```

## <a name="example"></a><span data-ttu-id="c1b4d-195">例</span><span class="sxs-lookup"><span data-stu-id="c1b4d-195">Example</span></span>

<span data-ttu-id="c1b4d-196">次の例では、`ns` を名前空間プレフィックスとして宣言します。</span><span class="sxs-lookup"><span data-stu-id="c1b4d-196">The following example declares `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="c1b4d-197">It then uses the prefix of the namespace to create an XML literal and displays the element's final form.</span><span class="sxs-lookup"><span data-stu-id="c1b4d-197">It then uses the prefix of the namespace to create an XML literal and displays the element's final form.</span></span>

[!code-vb[VbXMLSamples#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples10.vb#22)]

<span data-ttu-id="c1b4d-198">このコードを実行すると、次のテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c1b4d-198">This code displays the following text:</span></span>

```xml
<ns:outer xmlns:ns="http://SomeNamespace">
  <ns:middle xmlns:ns="http://NewNamespace">
    <ns:inner1 />
    <inner2 xmlns="http://SomeNamespace" />
  </ns:middle>
</ns:outer>
```

<span data-ttu-id="c1b4d-199">Notice that the compiler converted the prefix of the global XML namespace into a prefix definition for the XML namespace.</span><span class="sxs-lookup"><span data-stu-id="c1b4d-199">Notice that the compiler converted the prefix of the global XML namespace into a prefix definition for the XML namespace.</span></span> <span data-ttu-id="c1b4d-200">The \<ns:middle> element redefines the XML namespace prefix for the \<ns:inner1> element.</span><span class="sxs-lookup"><span data-stu-id="c1b4d-200">The \<ns:middle> element redefines the XML namespace prefix for the \<ns:inner1> element.</span></span> <span data-ttu-id="c1b4d-201">However, the \<ns:inner2> element uses the namespace defined by the `Imports` statement.</span><span class="sxs-lookup"><span data-stu-id="c1b4d-201">However, the \<ns:inner2> element uses the namespace defined by the `Imports` statement.</span></span>

## <a name="see-also"></a><span data-ttu-id="c1b4d-202">関連項目</span><span class="sxs-lookup"><span data-stu-id="c1b4d-202">See also</span></span>

- <xref:System.Xml.Linq.XElement>
- [<span data-ttu-id="c1b4d-203">宣言する XML 要素と属性の名前</span><span class="sxs-lookup"><span data-stu-id="c1b4d-203">Names of Declared XML Elements and Attributes</span></span>](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
- [<span data-ttu-id="c1b4d-204">XML コメント リテラル</span><span class="sxs-lookup"><span data-stu-id="c1b4d-204">XML Comment Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md)
- [<span data-ttu-id="c1b4d-205">XML CDATA リテラル</span><span class="sxs-lookup"><span data-stu-id="c1b4d-205">XML CDATA Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md)
- [<span data-ttu-id="c1b4d-206">XML リテラル</span><span class="sxs-lookup"><span data-stu-id="c1b4d-206">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="c1b4d-207">Visual Basic での XML の作成</span><span class="sxs-lookup"><span data-stu-id="c1b4d-207">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="c1b4d-208">XML での埋め込み式</span><span class="sxs-lookup"><span data-stu-id="c1b4d-208">Embedded Expressions in XML</span></span>](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)
- [<span data-ttu-id="c1b4d-209">Imports ステートメント (XML 名前空間)</span><span class="sxs-lookup"><span data-stu-id="c1b4d-209">Imports Statement (XML Namespace)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)
