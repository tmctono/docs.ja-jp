---
title: Imports ステートメント-XML 名前空間
ms.date: 07/20/2015
f1_keywords:
- vb.ImportsXmlns
helpviewer_keywords:
- XML namespace [Visual Basic], importing
- imports [Visual Basic]
- Imports statement [Visual Basic]
- namespaces [Visual Basic], importing
ms.assetid: 1f4d50a6-08c7-4c2e-8206-ccae35fcd1b4
ms.openlocfilehash: 52864e4d1c8183b6243025e72368d23627049c84
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351060"
---
# <a name="imports-statement-xml-namespace"></a><span data-ttu-id="11f07-102">Imports ステートメント (XML 名前空間)</span><span class="sxs-lookup"><span data-stu-id="11f07-102">Imports Statement (XML Namespace)</span></span>

<span data-ttu-id="11f07-103">Xml リテラルおよび XML 軸プロパティで使用する XML 名前空間プレフィックスをインポートします。</span><span class="sxs-lookup"><span data-stu-id="11f07-103">Imports XML namespace prefixes for use in XML literals and XML axis properties.</span></span>

## <a name="syntax"></a><span data-ttu-id="11f07-104">構文</span><span class="sxs-lookup"><span data-stu-id="11f07-104">Syntax</span></span>

```vb
Imports <xmlns:xmlNamespacePrefix = "xmlNamespaceName">
```

## <a name="parts"></a><span data-ttu-id="11f07-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="11f07-105">Parts</span></span>

`xmlNamespacePrefix`  
<span data-ttu-id="11f07-106">省略可能。</span><span class="sxs-lookup"><span data-stu-id="11f07-106">Optional.</span></span> <span data-ttu-id="11f07-107">XML 要素と属性が `xmlNamespaceName`を参照できる文字列です。</span><span class="sxs-lookup"><span data-stu-id="11f07-107">The string by which XML elements and attributes can refer to `xmlNamespaceName`.</span></span> <span data-ttu-id="11f07-108">`xmlNamespacePrefix` が指定されていない場合、インポートされた XML 名前空間が既定の XML 名前空間になります。</span><span class="sxs-lookup"><span data-stu-id="11f07-108">If no `xmlNamespacePrefix` is supplied, the imported XML namespace is the default XML namespace.</span></span> <span data-ttu-id="11f07-109">有効な XML 識別子である必要があります。</span><span class="sxs-lookup"><span data-stu-id="11f07-109">Must be a valid XML identifier.</span></span> <span data-ttu-id="11f07-110">詳細については、「[宣言する XML 要素と属性の名前](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="11f07-110">For more information, see [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span>

`xmlNamespaceName`  
<span data-ttu-id="11f07-111">必須。</span><span class="sxs-lookup"><span data-stu-id="11f07-111">Required.</span></span> <span data-ttu-id="11f07-112">インポートされる XML 名前空間を識別する文字列。</span><span class="sxs-lookup"><span data-stu-id="11f07-112">The string identifying the XML namespace being imported.</span></span>

## <a name="remarks"></a><span data-ttu-id="11f07-113">コメント</span><span class="sxs-lookup"><span data-stu-id="11f07-113">Remarks</span></span>

<span data-ttu-id="11f07-114">`Imports` ステートメントを使用しようすると、XML リテラルや XML 軸プロパティで使用できるグローバル XML 名前空間の定義や、`GetXmlNamespace` 演算子に渡されるパラメーターとしての定義ができます。</span><span class="sxs-lookup"><span data-stu-id="11f07-114">You can use the `Imports` statement to define global XML namespaces that you can use with XML literals and XML axis properties, or as parameters passed to the `GetXmlNamespace` operator.</span></span> <span data-ttu-id="11f07-115">(`Imports` ステートメントを使用して、コードで型名を使用するときに使用できるエイリアスをインポートする方法については、「 [Imports ステートメント (.Net 名前空間と型)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)」を参照してください。`Imports` ステートメントを使用して XML 名前空間を宣言する構文は、XML で使用される構文と同じです。</span><span class="sxs-lookup"><span data-stu-id="11f07-115">(For information about using the `Imports` statement to import an alias that can be used where type names are used in your code, see [Imports Statement (.NET Namespace and Type)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).) The syntax for declaring an XML namespace by using the `Imports` statement is identical to the syntax used in XML.</span></span> <span data-ttu-id="11f07-116">したがって、XML ファイルから名前空間宣言をコピーし、それを `Imports` ステートメントで使用することができます。</span><span class="sxs-lookup"><span data-stu-id="11f07-116">Therefore, you can copy a namespace declaration from an XML file and use it in an `Imports` statement.</span></span>

<span data-ttu-id="11f07-117">XML 名前空間プレフィックスは、同じ名前空間にある XML 要素を繰り返し作成する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="11f07-117">XML namespace prefixes are useful when you want to repeatedly create XML elements that are from the same namespace.</span></span> <span data-ttu-id="11f07-118">`Imports` ステートメントで宣言された XML 名前空間プレフィックスは、ファイル内のすべてのコードで使用できるという意味でグローバルです。</span><span class="sxs-lookup"><span data-stu-id="11f07-118">The XML namespace prefix declared with the `Imports` statement is global in the sense that it is available to all code in the file.</span></span> <span data-ttu-id="11f07-119">XML 要素リテラルを作成するとき、および XML 軸プロパティにアクセスするときに使用できます。</span><span class="sxs-lookup"><span data-stu-id="11f07-119">You can use it when you create XML element literals and when you access XML axis properties.</span></span> <span data-ttu-id="11f07-120">詳細については、「[XML 要素リテラル](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)」および「[XML 軸のプロパティ](../../../visual-basic/language-reference/xml-axis/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="11f07-120">For more information, see [XML Element Literal](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) and [XML Axis Properties](../../../visual-basic/language-reference/xml-axis/index.md).</span></span>

<span data-ttu-id="11f07-121">名前空間プレフィックスを使用せずにグローバル XML 名前空間を定義した場合 (`Imports <xmlns="http://SomeNameSpace>"`など)、その名前空間は既定の XML 名前空間と見なされます。</span><span class="sxs-lookup"><span data-stu-id="11f07-121">If you define a global XML namespace without a namespace prefix (for example, `Imports <xmlns="http://SomeNameSpace>"`), that namespace is considered the default XML namespace.</span></span> <span data-ttu-id="11f07-122">既定の XML 名前空間は、名前空間を明示的に指定していない XML 要素リテラルまたは XML 属性軸プロパティに使用されます。</span><span class="sxs-lookup"><span data-stu-id="11f07-122">The default XML namespace is used for any XML element literals or XML attribute axis properties that do not explicitly specify a namespace.</span></span> <span data-ttu-id="11f07-123">既定の名前空間は、指定された名前空間が空の名前空間 (つまり、`xmlns=""`) の場合にも使用されます。</span><span class="sxs-lookup"><span data-stu-id="11f07-123">The default namespace is also used if the specified namespace is the empty namespace (that is, `xmlns=""`).</span></span> <span data-ttu-id="11f07-124">既定の XML 名前空間は、xml リテラルの XML 属性、または名前空間を持たない xml 属性軸プロパティには適用されません。</span><span class="sxs-lookup"><span data-stu-id="11f07-124">The default XML namespace does not apply to XML attributes in XML literals or to XML attribute axis properties that do not have a namespace.</span></span>

<span data-ttu-id="11f07-125">Xml リテラルで定義されている xml 名前空間 (*ローカル xml 名前空間*と呼ばれます) は、`Imports` ステートメントでグローバルとして定義されている xml 名前空間よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="11f07-125">XML namespaces that are defined in an XML literal, which are called *local XML namespaces*, take precedence over XML namespaces that are defined by the `Imports` statement as global.</span></span> <span data-ttu-id="11f07-126">`Imports` ステートメントで定義された XML 名前空間は、Visual Basic プロジェクト用にインポートされた XML 名前空間よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="11f07-126">XML namespaces that are defined by the `Imports` statement take precedence over XML namespaces imported for a Visual Basic project.</span></span> <span data-ttu-id="11f07-127">Xml リテラルで XML 名前空間が定義されている場合、そのローカル名前空間は埋め込み式には適用されません。</span><span class="sxs-lookup"><span data-stu-id="11f07-127">If an XML literal defines an XML namespace, that local namespace does not apply to embedded expressions.</span></span>

<span data-ttu-id="11f07-128">グローバル XML 名前空間は .NET Framework 名前空間と同じスコープおよび定義規則に従います。</span><span class="sxs-lookup"><span data-stu-id="11f07-128">Global XML namespaces follow the same scoping and definition rules as .NET Framework namespaces.</span></span> <span data-ttu-id="11f07-129">その結果、.NET Framework 名前空間をインポートできる場所であればどこでも、`Imports` ステートメントを使用してグローバル XML 名前空間を定義できます。</span><span class="sxs-lookup"><span data-stu-id="11f07-129">As a result, you can include an `Imports` statement to define a global XML namespace anywhere you can import a .NET Framework namespace.</span></span> <span data-ttu-id="11f07-130">これには、コードファイルとプロジェクトレベルでインポートされた名前空間の両方が含まれます。</span><span class="sxs-lookup"><span data-stu-id="11f07-130">This includes both code files and project-level imported namespaces.</span></span> <span data-ttu-id="11f07-131">プロジェクトレベルでインポートされた名前空間の詳細については、「[プロジェクトデザイナー (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="11f07-131">For information about project-level imported namespaces, see [References Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic).</span></span>

<span data-ttu-id="11f07-132">各ソースファイルには、任意の数の `Imports` ステートメントを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="11f07-132">Each source file can contain any number of `Imports` statements.</span></span> <span data-ttu-id="11f07-133">これらは、`Option Strict` ステートメントなどのオプション宣言に従う必要があります。また、`Module` や `Class` ステートメントなどのプログラミング要素の宣言の前に記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="11f07-133">These must follow option declarations, such as the `Option Strict` statement, and they must precede programming element declarations, such as `Module` or `Class` statements.</span></span>

## <a name="example"></a><span data-ttu-id="11f07-134">例</span><span class="sxs-lookup"><span data-stu-id="11f07-134">Example</span></span>

<span data-ttu-id="11f07-135">次の例では、既定の XML 名前空間と、プレフィックス `ns`で識別される XML 名前空間をインポートします。</span><span class="sxs-lookup"><span data-stu-id="11f07-135">The following example imports a default XML namespace and an XML namespace identified with the prefix `ns`.</span></span> <span data-ttu-id="11f07-136">次に、両方の名前空間を使用する XML リテラルを作成します。</span><span class="sxs-lookup"><span data-stu-id="11f07-136">It then creates XML literals that use both namespaces.</span></span>

[!code-vb[VbXMLSamples#45](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/Module1.vb#45)]

<span data-ttu-id="11f07-137">このコードを実行すると、次のテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="11f07-137">This code displays the following text:</span></span>

```xml
<ns:outer xmlns="http://DefaultNamespace"
          xmlns:ns="http://NewNamespace">
  <ns:innerElement></ns:innerElement>
  <siblingElement></siblingElement>
  <innerElement />
</ns:outer>
```

## <a name="example"></a><span data-ttu-id="11f07-138">例</span><span class="sxs-lookup"><span data-stu-id="11f07-138">Example</span></span>

<span data-ttu-id="11f07-139">次の例では、XML 名前空間プレフィックス `ns`をインポートします。</span><span class="sxs-lookup"><span data-stu-id="11f07-139">The following example imports the XML namespace prefix `ns`.</span></span> <span data-ttu-id="11f07-140">次に、名前空間プレフィックスを使用する XML リテラルを作成し、要素の最終的な形式を表示します。</span><span class="sxs-lookup"><span data-stu-id="11f07-140">It then creates an XML literal that uses the namespace prefix and displays the element's final form.</span></span>

[!code-vb[VbXMLSamples#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples10.vb#22)]

<span data-ttu-id="11f07-141">このコードを実行すると、次のテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="11f07-141">This code displays the following text:</span></span>

```xml
<ns:outer xmlns:ns="http://SomeNamespace">
  <ns:middle xmlns:ns="http://NewNamespace">
    <ns:inner1 />
    <inner2 xmlns="http://SomeNamespace" />
  </ns:middle>
</ns:outer>
```

<span data-ttu-id="11f07-142">コンパイラによって、XML 名前空間プレフィックスがグローバルプレフィックスからローカルプレフィックス定義に変換されたことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="11f07-142">Notice that the compiler converted the XML namespace prefix from a global prefix to a local prefix definition.</span></span>

## <a name="example"></a><span data-ttu-id="11f07-143">例</span><span class="sxs-lookup"><span data-stu-id="11f07-143">Example</span></span>

<span data-ttu-id="11f07-144">次の例では、XML 名前空間プレフィックス `ns`をインポートします。</span><span class="sxs-lookup"><span data-stu-id="11f07-144">The following example imports the XML namespace prefix `ns`.</span></span> <span data-ttu-id="11f07-145">その後、この名前空間のプレフィックスを使用して XML リテラルを作成し、修飾名 `ns:name` を持つ最初の子ノードにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="11f07-145">It then uses the prefix of the namespace to create an XML literal and access the first child node with the qualified name `ns:name`.</span></span>

[!code-vb[VbXMLSamples#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples8.vb#19)]

<span data-ttu-id="11f07-146">このコードを実行すると、次のテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="11f07-146">This code displays the following text:</span></span>

`Patrick Hines`

## <a name="see-also"></a><span data-ttu-id="11f07-147">参照</span><span class="sxs-lookup"><span data-stu-id="11f07-147">See also</span></span>

- [<span data-ttu-id="11f07-148">XML 要素リテラル</span><span class="sxs-lookup"><span data-stu-id="11f07-148">XML Element Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [<span data-ttu-id="11f07-149">XML 軸プロパティ</span><span class="sxs-lookup"><span data-stu-id="11f07-149">XML Axis Properties</span></span>](../../../visual-basic/language-reference/xml-axis/index.md)
- [<span data-ttu-id="11f07-150">宣言する XML 要素と属性の名前</span><span class="sxs-lookup"><span data-stu-id="11f07-150">Names of Declared XML Elements and Attributes</span></span>](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
- [<span data-ttu-id="11f07-151">GetXmlNamespace 演算子</span><span class="sxs-lookup"><span data-stu-id="11f07-151">GetXmlNamespace Operator</span></span>](../../../visual-basic/language-reference/operators/getxmlnamespace-operator.md)
