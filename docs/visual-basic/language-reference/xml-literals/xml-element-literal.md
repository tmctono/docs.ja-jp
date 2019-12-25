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
# <a name="xml-element-literal-visual-basic"></a><span data-ttu-id="54045-102">XML 要素リテラル (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="54045-102">XML Element Literal (Visual Basic)</span></span>

<span data-ttu-id="54045-103"><xref:System.Xml.Linq.XElement> オブジェクトを表すリテラル。</span><span class="sxs-lookup"><span data-stu-id="54045-103">A literal that represents an <xref:System.Xml.Linq.XElement> object.</span></span>

## <a name="syntax"></a><span data-ttu-id="54045-104">構文</span><span class="sxs-lookup"><span data-stu-id="54045-104">Syntax</span></span>

```xml
<name [ attributeList ] />
-or-
<name [ attributeList ] > [ elementContents ] </[ name ]>
```

## <a name="parts"></a><span data-ttu-id="54045-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="54045-105">Parts</span></span>

- `<`

  <span data-ttu-id="54045-106">必須。</span><span class="sxs-lookup"><span data-stu-id="54045-106">Required.</span></span> <span data-ttu-id="54045-107">開始要素タグを開きます。</span><span class="sxs-lookup"><span data-stu-id="54045-107">Opens the starting element tag.</span></span>

- `name`

  <span data-ttu-id="54045-108">必須。</span><span class="sxs-lookup"><span data-stu-id="54045-108">Required.</span></span> <span data-ttu-id="54045-109">要素名</span><span class="sxs-lookup"><span data-stu-id="54045-109">Name of the element.</span></span> <span data-ttu-id="54045-110">形式は、次のいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="54045-110">The format is one of the following:</span></span>

  - <span data-ttu-id="54045-111">`[ePrefix:]eName`形式の要素名のリテラルテキスト。次のようになります。</span><span class="sxs-lookup"><span data-stu-id="54045-111">Literal text for the element name, of the form `[ePrefix:]eName`, where:</span></span>

    |<span data-ttu-id="54045-112">要素</span><span class="sxs-lookup"><span data-stu-id="54045-112">Part</span></span>|<span data-ttu-id="54045-113">説明</span><span class="sxs-lookup"><span data-stu-id="54045-113">Description</span></span>|
    |---|---|
    |`ePrefix`|<span data-ttu-id="54045-114">省略可。</span><span class="sxs-lookup"><span data-stu-id="54045-114">Optional.</span></span> <span data-ttu-id="54045-115">要素の XML 名前空間プレフィックス。</span><span class="sxs-lookup"><span data-stu-id="54045-115">XML namespace prefix for the element.</span></span> <span data-ttu-id="54045-116">は、ファイルまたはプロジェクトレベルで `Imports` ステートメントで定義されているグローバル XML 名前空間であるか、またはこの要素または親要素で定義されているローカル XML 名前空間である必要があります。</span><span class="sxs-lookup"><span data-stu-id="54045-116">Must be a global XML namespace that is defined with an `Imports` statement in the file or at the project level, or a local XML namespace that is defined in this element or a parent element.</span></span>|
    |`eName`|<span data-ttu-id="54045-117">必須。</span><span class="sxs-lookup"><span data-stu-id="54045-117">Required.</span></span> <span data-ttu-id="54045-118">要素名</span><span class="sxs-lookup"><span data-stu-id="54045-118">Name of the element.</span></span> <span data-ttu-id="54045-119">形式は、次のいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="54045-119">The format is one of the following:</span></span><br /><br /> <span data-ttu-id="54045-120">-リテラルテキスト。</span><span class="sxs-lookup"><span data-stu-id="54045-120">- Literal text.</span></span> <span data-ttu-id="54045-121">「[宣言された XML 要素と属性の名前」を](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="54045-121">See [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span><br /><span data-ttu-id="54045-122">-フォーム `<%= eNameExp %>`の埋め込み式。</span><span class="sxs-lookup"><span data-stu-id="54045-122">- Embedded expression of the form `<%= eNameExp %>`.</span></span> <span data-ttu-id="54045-123">`eNameExp` の型は `String` であるか、または <xref:System.Xml.Linq.XName>に暗黙的に変換できる型である必要があります。</span><span class="sxs-lookup"><span data-stu-id="54045-123">The type of `eNameExp` must be `String` or a type that is implicitly convertible to <xref:System.Xml.Linq.XName>.</span></span>|

  - <span data-ttu-id="54045-124">`<%= nameExp %>`形式の埋め込み式。</span><span class="sxs-lookup"><span data-stu-id="54045-124">Embedded expression of the form `<%= nameExp %>`.</span></span> <span data-ttu-id="54045-125">`nameExp` の型は、`String` または <xref:System.Xml.Linq.XName>に暗黙的に変換できる型である必要があります。</span><span class="sxs-lookup"><span data-stu-id="54045-125">The type of `nameExp` must be `String` or a type implicitly convertible to <xref:System.Xml.Linq.XName>.</span></span> <span data-ttu-id="54045-126">埋め込み式は、要素の終了タグでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="54045-126">An embedded expression is not allowed in a closing tag of an element.</span></span>

- `attributeList`

  <span data-ttu-id="54045-127">省略可。</span><span class="sxs-lookup"><span data-stu-id="54045-127">Optional.</span></span> <span data-ttu-id="54045-128">リテラルで宣言された属性のリスト。</span><span class="sxs-lookup"><span data-stu-id="54045-128">List of attributes declared in the literal.</span></span>

  `attribute [ attribute ... ]`

  <span data-ttu-id="54045-129">各 `attribute` には、次のいずれかの構文があります。</span><span class="sxs-lookup"><span data-stu-id="54045-129">Each `attribute` has one of the following syntaxes:</span></span>

  - <span data-ttu-id="54045-130">`[aPrefix:]aName=aValue`形式の属性の割り当て。次のようになります。</span><span class="sxs-lookup"><span data-stu-id="54045-130">Attribute assignment, of the form `[aPrefix:]aName=aValue`, where:</span></span>

    |<span data-ttu-id="54045-131">要素</span><span class="sxs-lookup"><span data-stu-id="54045-131">Part</span></span>|<span data-ttu-id="54045-132">説明</span><span class="sxs-lookup"><span data-stu-id="54045-132">Description</span></span>|
    |---|---|
    |`aPrefix`|<span data-ttu-id="54045-133">省略可。</span><span class="sxs-lookup"><span data-stu-id="54045-133">Optional.</span></span> <span data-ttu-id="54045-134">属性の XML 名前空間プレフィックス。</span><span class="sxs-lookup"><span data-stu-id="54045-134">XML namespace prefix for the attribute.</span></span> <span data-ttu-id="54045-135">は、`Imports` ステートメント、またはこの要素または親要素で定義されているローカル XML 名前空間で定義されているグローバル XML 名前空間である必要があります。</span><span class="sxs-lookup"><span data-stu-id="54045-135">Must be a global XML namespace that is defined with an `Imports` statement, or a local XML namespace that is defined in this element or a parent element.</span></span>|
    |`aName`|<span data-ttu-id="54045-136">必須。</span><span class="sxs-lookup"><span data-stu-id="54045-136">Required.</span></span> <span data-ttu-id="54045-137">属性の名前。</span><span class="sxs-lookup"><span data-stu-id="54045-137">Name of the attribute.</span></span> <span data-ttu-id="54045-138">形式は、次のいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="54045-138">The format is one of the following:</span></span><br /><br /> <span data-ttu-id="54045-139">-リテラルテキスト。</span><span class="sxs-lookup"><span data-stu-id="54045-139">- Literal text.</span></span> <span data-ttu-id="54045-140">「[宣言された XML 要素と属性の名前」を](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="54045-140">See [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span><br /><span data-ttu-id="54045-141">-フォーム `<%= aNameExp %>`の埋め込み式。</span><span class="sxs-lookup"><span data-stu-id="54045-141">- Embedded expression of the form `<%= aNameExp %>`.</span></span> <span data-ttu-id="54045-142">`aNameExp` の型は `String` であるか、または <xref:System.Xml.Linq.XName>に暗黙的に変換できる型である必要があります。</span><span class="sxs-lookup"><span data-stu-id="54045-142">The type of `aNameExp` must be `String` or a type that is implicitly convertible to <xref:System.Xml.Linq.XName>.</span></span>|
    |`aValue`|<span data-ttu-id="54045-143">省略可。</span><span class="sxs-lookup"><span data-stu-id="54045-143">Optional.</span></span> <span data-ttu-id="54045-144">属性の値。</span><span class="sxs-lookup"><span data-stu-id="54045-144">Value of the attribute.</span></span> <span data-ttu-id="54045-145">形式は、次のいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="54045-145">The format is one of the following:</span></span><br /><br /> <span data-ttu-id="54045-146">-リテラルテキスト (引用符で囲まれています)。</span><span class="sxs-lookup"><span data-stu-id="54045-146">- Literal text, enclosed in quotation marks.</span></span><br /><span data-ttu-id="54045-147">-フォーム `<%= aValueExp %>`の埋め込み式。</span><span class="sxs-lookup"><span data-stu-id="54045-147">- Embedded expression of the form `<%= aValueExp %>`.</span></span> <span data-ttu-id="54045-148">任意の型を使用できます。</span><span class="sxs-lookup"><span data-stu-id="54045-148">Any type is allowed.</span></span>|

  - <span data-ttu-id="54045-149">`<%= aExp %>`形式の埋め込み式。</span><span class="sxs-lookup"><span data-stu-id="54045-149">Embedded expression of the form `<%= aExp %>`.</span></span>

- `/>`

  <span data-ttu-id="54045-150">省略可。</span><span class="sxs-lookup"><span data-stu-id="54045-150">Optional.</span></span> <span data-ttu-id="54045-151">要素がコンテンツのない空の要素であることを示します。</span><span class="sxs-lookup"><span data-stu-id="54045-151">Indicates that the element is an empty element, without content.</span></span>

- `>`

  <span data-ttu-id="54045-152">必須。</span><span class="sxs-lookup"><span data-stu-id="54045-152">Required.</span></span> <span data-ttu-id="54045-153">開始または空の要素タグを終了します。</span><span class="sxs-lookup"><span data-stu-id="54045-153">Ends the beginning or empty element tag.</span></span>

- `elementContents`

  <span data-ttu-id="54045-154">省略可。</span><span class="sxs-lookup"><span data-stu-id="54045-154">Optional.</span></span> <span data-ttu-id="54045-155">要素の内容。</span><span class="sxs-lookup"><span data-stu-id="54045-155">Content of the element.</span></span>

  `content [ content ... ]`

  <span data-ttu-id="54045-156">各 `content` は、次のいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="54045-156">Each `content` can be one of the following:</span></span>

  - <span data-ttu-id="54045-157">リテラルテキスト。</span><span class="sxs-lookup"><span data-stu-id="54045-157">Literal text.</span></span> <span data-ttu-id="54045-158">リテラルテキストがある場合、`elementContents` のすべての空白が有意になります。</span><span class="sxs-lookup"><span data-stu-id="54045-158">All the white space in `elementContents` becomes significant if there is any literal text.</span></span>

  - <span data-ttu-id="54045-159">`<%= contentExp %>`形式の埋め込み式。</span><span class="sxs-lookup"><span data-stu-id="54045-159">Embedded expression of the form `<%= contentExp %>`.</span></span>

  - <span data-ttu-id="54045-160">XML 要素リテラル。</span><span class="sxs-lookup"><span data-stu-id="54045-160">XML element literal.</span></span>

  - <span data-ttu-id="54045-161">XML コメントリテラル。</span><span class="sxs-lookup"><span data-stu-id="54045-161">XML comment literal.</span></span> <span data-ttu-id="54045-162">「[XML コメントリテラル](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54045-162">See [XML Comment Literal](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).</span></span>

  - <span data-ttu-id="54045-163">XML 処理命令リテラル。</span><span class="sxs-lookup"><span data-stu-id="54045-163">XML processing instruction literal.</span></span> <span data-ttu-id="54045-164">「[XML 処理命令リテラル](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54045-164">See [XML Processing Instruction Literal](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).</span></span>

  - <span data-ttu-id="54045-165">XML CDATA リテラル。</span><span class="sxs-lookup"><span data-stu-id="54045-165">XML CDATA literal.</span></span> <span data-ttu-id="54045-166">「 [XML CDATA Literal](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54045-166">See [XML CDATA Literal](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md).</span></span>

- `</[name]>`

  <span data-ttu-id="54045-167">省略可。</span><span class="sxs-lookup"><span data-stu-id="54045-167">Optional.</span></span> <span data-ttu-id="54045-168">要素の終了タグを表します。</span><span class="sxs-lookup"><span data-stu-id="54045-168">Represents the closing tag for the element.</span></span> <span data-ttu-id="54045-169">埋め込み式の結果である場合、省略可能な `name` パラメーターは使用できません。</span><span class="sxs-lookup"><span data-stu-id="54045-169">The optional `name` parameter is not allowed when it is the result of an embedded expression.</span></span>

## <a name="return-value"></a><span data-ttu-id="54045-170">戻り値</span><span class="sxs-lookup"><span data-stu-id="54045-170">Return Value</span></span>

<span data-ttu-id="54045-171"><xref:System.Xml.Linq.XElement> オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="54045-171">An <xref:System.Xml.Linq.XElement> object.</span></span>

## <a name="remarks"></a><span data-ttu-id="54045-172">コメント</span><span class="sxs-lookup"><span data-stu-id="54045-172">Remarks</span></span>

<span data-ttu-id="54045-173">XML 要素リテラル構文を使用すると、コード内に <xref:System.Xml.Linq.XElement> オブジェクトを作成できます。</span><span class="sxs-lookup"><span data-stu-id="54045-173">You can use the XML element literal syntax to create <xref:System.Xml.Linq.XElement> objects in your code.</span></span>

> [!NOTE]
> <span data-ttu-id="54045-174">XML リテラルは、行連結文字を使用せずに、複数の行にまたがることができます。</span><span class="sxs-lookup"><span data-stu-id="54045-174">An XML literal can span multiple lines without using line continuation characters.</span></span> <span data-ttu-id="54045-175">この機能を使用すると、XML ドキュメントからコンテンツをコピーして、Visual Basic プログラムに直接貼り付けることができます。</span><span class="sxs-lookup"><span data-stu-id="54045-175">This feature enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>

<span data-ttu-id="54045-176">フォーム `<%= exp %>` の埋め込み式を使用すると、XML 要素リテラルに動的な情報を追加できます。</span><span class="sxs-lookup"><span data-stu-id="54045-176">Embedded expressions of the form `<%= exp %>` enable you to add dynamic information to an XML element literal.</span></span> <span data-ttu-id="54045-177">詳細については、「 [XML での埋め込み式](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54045-177">For more information, see [Embedded Expressions in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span></span>

<span data-ttu-id="54045-178">Visual Basic コンパイラは、XML 要素リテラルを <xref:System.Xml.Linq.XElement.%23ctor%2A> コンストラクターの呼び出しに変換します。また、必要に応じて、<xref:System.Xml.Linq.XAttribute.%23ctor%2A> コンストラクターを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="54045-178">The Visual Basic compiler converts the XML element literal into calls to the <xref:System.Xml.Linq.XElement.%23ctor%2A> constructor and, if it is required, the <xref:System.Xml.Linq.XAttribute.%23ctor%2A> constructor.</span></span>

## <a name="xml-namespaces"></a><span data-ttu-id="54045-179">XML 名前空間</span><span class="sxs-lookup"><span data-stu-id="54045-179">XML Namespaces</span></span>

<span data-ttu-id="54045-180">XML 名前空間プレフィックスは、同じ名前空間の要素を持つ XML リテラルをコード内で何回も作成する必要がある場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="54045-180">XML namespace prefixes are useful when you have to create XML literals with elements from the same namespace many times in code.</span></span> <span data-ttu-id="54045-181">グローバル XML 名前空間プレフィックスは、`Imports` ステートメントを使用して定義します。または、`xmlns:xmlPrefix="xmlNamespace"` 属性構文を使用して定義するローカルプレフィックスを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="54045-181">You can use global XML namespace prefixes, which you define by using the `Imports` statement, or local prefixes, which you define by using the `xmlns:xmlPrefix="xmlNamespace"` attribute syntax.</span></span> <span data-ttu-id="54045-182">詳細については、「 [Imports ステートメント (XML 名前空間)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54045-182">For more information, see [Imports Statement (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span></span>

<span data-ttu-id="54045-183">XML 名前空間のスコープ規則に従って、ローカルプレフィックスはグローバルプレフィックスよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="54045-183">In accordance with the scoping rules for XML namespaces, local prefixes take precedence over global prefixes.</span></span> <span data-ttu-id="54045-184">ただし、xml リテラルで XML 名前空間が定義されている場合、その名前空間は、埋め込み式に出現する式では使用できません。</span><span class="sxs-lookup"><span data-stu-id="54045-184">However, if an XML literal defines an XML namespace, that namespace is not available to expressions that appear in an embedded expression.</span></span> <span data-ttu-id="54045-185">埋め込み式は、グローバル XML 名前空間のみにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="54045-185">The embedded expression can access only the global XML namespace.</span></span>

<span data-ttu-id="54045-186">Visual Basic コンパイラは、XML リテラルによって使用される各グローバル XML 名前空間を、生成されたコード内の1つのローカル名前空間定義に変換します。</span><span class="sxs-lookup"><span data-stu-id="54045-186">The Visual Basic compiler converts each global XML namespace that is used by an XML literal into a one local namespace definition in the generated code.</span></span> <span data-ttu-id="54045-187">使用されていないグローバル XML 名前空間は、生成されたコードには表示されません。</span><span class="sxs-lookup"><span data-stu-id="54045-187">Global XML namespaces that are not used do not appear in the generated code.</span></span>

## <a name="example"></a><span data-ttu-id="54045-188">例</span><span class="sxs-lookup"><span data-stu-id="54045-188">Example</span></span>

<span data-ttu-id="54045-189">次の例は、2つの入れ子になった空の要素を持つ単純な XML 要素を作成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="54045-189">The following example shows how to create a simple XML element that has two nested empty elements.</span></span>

[!code-vb[VbXMLSamples#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples9.vb#20)]

<span data-ttu-id="54045-190">この例では、次のテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="54045-190">The example displays the following text.</span></span> <span data-ttu-id="54045-191">リテラルは空の要素の構造を保持することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="54045-191">Notice that the literal preserves the structure of the empty elements.</span></span>

```xml
<outer>
  <inner1></inner1>
  <inner2 />
</outer>
```

## <a name="example"></a><span data-ttu-id="54045-192">例</span><span class="sxs-lookup"><span data-stu-id="54045-192">Example</span></span>

<span data-ttu-id="54045-193">次の例では、埋め込み式を使用して要素に名前を指定し、属性を作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="54045-193">The following example shows how to use embedded expressions to name an element and create attributes.</span></span>

[!code-vb[VbXMLSamples#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples9.vb#21)]

<span data-ttu-id="54045-194">このコードを実行すると、次のテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="54045-194">This code displays the following text:</span></span>

```xml
<book isbn="1234" author="My Author" year="1999" title="My Book" />
```

## <a name="example"></a><span data-ttu-id="54045-195">例</span><span class="sxs-lookup"><span data-stu-id="54045-195">Example</span></span>

<span data-ttu-id="54045-196">次の例では、`ns` を名前空間プレフィックスとして宣言します。</span><span class="sxs-lookup"><span data-stu-id="54045-196">The following example declares `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="54045-197">次に、名前空間のプレフィックスを使用して XML リテラルを作成し、要素の最終的な形式を表示します。</span><span class="sxs-lookup"><span data-stu-id="54045-197">It then uses the prefix of the namespace to create an XML literal and displays the element's final form.</span></span>

[!code-vb[VbXMLSamples#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples10.vb#22)]

<span data-ttu-id="54045-198">このコードを実行すると、次のテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="54045-198">This code displays the following text:</span></span>

```xml
<ns:outer xmlns:ns="http://SomeNamespace">
  <ns:middle xmlns:ns="http://NewNamespace">
    <ns:inner1 />
    <inner2 xmlns="http://SomeNamespace" />
  </ns:middle>
</ns:outer>
```

<span data-ttu-id="54045-199">コンパイラによって、グローバル XML 名前空間のプレフィックスが XML 名前空間のプレフィックス定義に変換されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="54045-199">Notice that the compiler converted the prefix of the global XML namespace into a prefix definition for the XML namespace.</span></span> <span data-ttu-id="54045-200">\<ns: ミドル > 要素は、\<ns: inner1 > 要素の XML 名前空間プレフィックスを再定義します。</span><span class="sxs-lookup"><span data-stu-id="54045-200">The \<ns:middle> element redefines the XML namespace prefix for the \<ns:inner1> element.</span></span> <span data-ttu-id="54045-201">ただし、\<ns: inner2 > 要素は、`Imports` ステートメントで定義されている名前空間を使用します。</span><span class="sxs-lookup"><span data-stu-id="54045-201">However, the \<ns:inner2> element uses the namespace defined by the `Imports` statement.</span></span>

## <a name="see-also"></a><span data-ttu-id="54045-202">参照</span><span class="sxs-lookup"><span data-stu-id="54045-202">See also</span></span>

- <xref:System.Xml.Linq.XElement>
- [<span data-ttu-id="54045-203">宣言する XML 要素と属性の名前</span><span class="sxs-lookup"><span data-stu-id="54045-203">Names of Declared XML Elements and Attributes</span></span>](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
- [<span data-ttu-id="54045-204">XML コメント リテラル</span><span class="sxs-lookup"><span data-stu-id="54045-204">XML Comment Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md)
- [<span data-ttu-id="54045-205">XML CDATA リテラル</span><span class="sxs-lookup"><span data-stu-id="54045-205">XML CDATA Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md)
- [<span data-ttu-id="54045-206">XML リテラル</span><span class="sxs-lookup"><span data-stu-id="54045-206">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="54045-207">Visual Basic での XML の作成</span><span class="sxs-lookup"><span data-stu-id="54045-207">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="54045-208">XML での埋め込み式</span><span class="sxs-lookup"><span data-stu-id="54045-208">Embedded Expressions in XML</span></span>](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)
- [<span data-ttu-id="54045-209">Imports ステートメント (XML 名前空間)</span><span class="sxs-lookup"><span data-stu-id="54045-209">Imports Statement (XML Namespace)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)
