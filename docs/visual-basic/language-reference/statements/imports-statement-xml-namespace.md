---
title: Imports ステートメント - XML Namespace (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.ImportsXmlns
helpviewer_keywords:
- XML namespace [Visual Basic], importing
- imports [Visual Basic]
- Imports statement [Visual Basic]
- namespaces [Visual Basic], importing
ms.assetid: 1f4d50a6-08c7-4c2e-8206-ccae35fcd1b4
ms.openlocfilehash: 97d08113a37477add9d770b0a680c303fe7e3040
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61638958"
---
# <a name="imports-statement-xml-namespace"></a><span data-ttu-id="22dcd-102">Imports ステートメント (XML 名前空間)</span><span class="sxs-lookup"><span data-stu-id="22dcd-102">Imports Statement (XML Namespace)</span></span>
<span data-ttu-id="22dcd-103">XML リテラルおよび XML 軸のプロパティで使用するための XML 名前空間プレフィックスをインポートします。</span><span class="sxs-lookup"><span data-stu-id="22dcd-103">Imports XML namespace prefixes for use in XML literals and XML axis properties.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22dcd-104">構文</span><span class="sxs-lookup"><span data-stu-id="22dcd-104">Syntax</span></span>  
  
```  
Imports <xmlns:xmlNamespacePrefix = "xmlNamespaceName">  
```  
  
## <a name="parts"></a><span data-ttu-id="22dcd-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="22dcd-105">Parts</span></span>  
 `xmlNamespacePrefix`  
 <span data-ttu-id="22dcd-106">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="22dcd-106">Optional.</span></span> <span data-ttu-id="22dcd-107">XML 要素と属性を参照できます文字列`xmlNamespaceName`します。</span><span class="sxs-lookup"><span data-stu-id="22dcd-107">The string by which XML elements and attributes can refer to `xmlNamespaceName`.</span></span> <span data-ttu-id="22dcd-108">いない場合`xmlNamespacePrefix`は既定の XML 名前空間がインポートされた XML 名前空間を指定します。</span><span class="sxs-lookup"><span data-stu-id="22dcd-108">If no `xmlNamespacePrefix` is supplied, the imported XML namespace is the default XML namespace.</span></span> <span data-ttu-id="22dcd-109">有効な XML 識別子である必要があります。</span><span class="sxs-lookup"><span data-stu-id="22dcd-109">Must be a valid XML identifier.</span></span> <span data-ttu-id="22dcd-110">詳細については、次を参照してください。[宣言されている XML 要素の名前と属性](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)します。</span><span class="sxs-lookup"><span data-stu-id="22dcd-110">For more information, see [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span>  
  
 `xmlNamespaceName`  
 <span data-ttu-id="22dcd-111">必須。</span><span class="sxs-lookup"><span data-stu-id="22dcd-111">Required.</span></span> <span data-ttu-id="22dcd-112">インポートされる XML 名前空間を識別する文字列。</span><span class="sxs-lookup"><span data-stu-id="22dcd-112">The string identifying the XML namespace being imported.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="22dcd-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="22dcd-113">Remarks</span></span>  
 <span data-ttu-id="22dcd-114">使用することができます、 `Imports` XML リテラルおよび XML 軸のプロパティをまたはに渡されるパラメーターとして使用できるグローバルの XML 名前空間を定義するステートメント、`GetXmlNamespace`演算子。</span><span class="sxs-lookup"><span data-stu-id="22dcd-114">You can use the `Imports` statement to define global XML namespaces that you can use with XML literals and XML axis properties, or as parameters passed to the `GetXmlNamespace` operator.</span></span> <span data-ttu-id="22dcd-115">(使用方法について、`Imports`型の名前を使用するコードで使用できるエイリアスをインポートするステートメントを参照してください[Imports ステートメント (.NET Namespace よぶ型)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md))。使用して XML 名前空間を宣言する構文、`Imports`ステートメントは XML で使用される構文と同じです。</span><span class="sxs-lookup"><span data-stu-id="22dcd-115">(For information about using the `Imports` statement to import an alias that can be used where type names are used in your code, see [Imports Statement (.NET Namespace and Type)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).) The syntax for declaring an XML namespace by using the `Imports` statement is identical to the syntax used in XML.</span></span> <span data-ttu-id="22dcd-116">そのため、XML ファイルから名前空間宣言をコピーしで使用する`Imports`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="22dcd-116">Therefore, you can copy a namespace declaration from an XML file and use it in an `Imports` statement.</span></span>  
  
 <span data-ttu-id="22dcd-117">XML 名前空間プレフィックスは、繰り返し、同じ名前空間からの XML 要素を作成する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="22dcd-117">XML namespace prefixes are useful when you want to repeatedly create XML elements that are from the same namespace.</span></span> <span data-ttu-id="22dcd-118">XML 名前空間プレフィックスが宣言された、`Imports`ステートメントがファイルにすべてのコードで使用可能であるという意味でグローバルです。</span><span class="sxs-lookup"><span data-stu-id="22dcd-118">The XML namespace prefix declared with the `Imports` statement is global in the sense that it is available to all code in the file.</span></span> <span data-ttu-id="22dcd-119">XML 要素リテラルおよび XML 軸のプロパティにアクセスするときに作成するときに使用することができます。</span><span class="sxs-lookup"><span data-stu-id="22dcd-119">You can use it when you create XML element literals and when you access XML axis properties.</span></span> <span data-ttu-id="22dcd-120">詳細については、次を参照してください。 [XML 要素リテラル](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)と[XML 軸プロパティ](../../../visual-basic/language-reference/xml-axis/index.md)します。</span><span class="sxs-lookup"><span data-stu-id="22dcd-120">For more information, see [XML Element Literal](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) and [XML Axis Properties](../../../visual-basic/language-reference/xml-axis/index.md).</span></span>  
  
 <span data-ttu-id="22dcd-121">名前空間プレフィックスなしのグローバル XML 名前空間を定義するかどうか (たとえば、 `Imports <xmlns="http://SomeNameSpace>"`)、その名前空間には、既定の XML 名前空間と見なされます。</span><span class="sxs-lookup"><span data-stu-id="22dcd-121">If you define a global XML namespace without a namespace prefix (for example, `Imports <xmlns="http://SomeNameSpace>"`), that namespace is considered the default XML namespace.</span></span> <span data-ttu-id="22dcd-122">既定の XML 名前空間は、任意の XML 要素リテラルまたは名前空間を明示的に指定されていない XML 属性軸プロパティに使用されます。</span><span class="sxs-lookup"><span data-stu-id="22dcd-122">The default XML namespace is used for any XML element literals or XML attribute axis properties that do not explicitly specify a namespace.</span></span> <span data-ttu-id="22dcd-123">指定した名前空間が空の名前空間が場合、既定の名前空間が使用されます (つまり、 `xmlns=""`)。</span><span class="sxs-lookup"><span data-stu-id="22dcd-123">The default namespace is also used if the specified namespace is the empty namespace (that is, `xmlns=""`).</span></span> <span data-ttu-id="22dcd-124">既定の XML 名前空間は、XML リテラルの XML 属性または名前空間がない XML 属性軸プロパティには適用されません。</span><span class="sxs-lookup"><span data-stu-id="22dcd-124">The default XML namespace does not apply to XML attributes in XML literals or to XML attribute axis properties that do not have a namespace.</span></span>  
  
 <span data-ttu-id="22dcd-125">XML 名前空間、XML リテラルで定義されていると呼ばれる*ローカルの XML 名前空間*、XML 名前空間で定義されているよりも優先、`Imports`グローバルとしてステートメント。</span><span class="sxs-lookup"><span data-stu-id="22dcd-125">XML namespaces that are defined in an XML literal, which are called *local XML namespaces*, take precedence over XML namespaces that are defined by the `Imports` statement as global.</span></span> <span data-ttu-id="22dcd-126">XML 名前空間で定義されている、`Imports`ステートメント、Visual Basic プロジェクトのインポートされた XML 名前空間よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="22dcd-126">XML namespaces that are defined by the `Imports` statement take precedence over XML namespaces imported for a Visual Basic project.</span></span> <span data-ttu-id="22dcd-127">XML リテラルには、XML 名前空間が定義されている場合、ローカルの名前空間は埋め込まれた式には適用されません。</span><span class="sxs-lookup"><span data-stu-id="22dcd-127">If an XML literal defines an XML namespace, that local namespace does not apply to embedded expressions.</span></span>  
  
 <span data-ttu-id="22dcd-128">グローバル名前空間は XML では、.NET Framework 名前空間と同じスコープと定義の規則に従います。</span><span class="sxs-lookup"><span data-stu-id="22dcd-128">Global XML namespaces follow the same scoping and definition rules as .NET Framework namespaces.</span></span> <span data-ttu-id="22dcd-129">その結果、含めることができます、`Imports`ステートメント グローバル XML 名前空間を定義する .NET Framework 名前空間をインポートする任意の場所。</span><span class="sxs-lookup"><span data-stu-id="22dcd-129">As a result, you can include an `Imports` statement to define a global XML namespace anywhere you can import a .NET Framework namespace.</span></span> <span data-ttu-id="22dcd-130">これには、コード ファイルとプロジェクト レベル インポートされた名前空間の両方が含まれます。</span><span class="sxs-lookup"><span data-stu-id="22dcd-130">This includes both code files and project-level imported namespaces.</span></span> <span data-ttu-id="22dcd-131">プロジェクト レベル インポートされた名前空間については、次を参照してください。[参照設定 ページ、プロジェクト デザイナー (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic)します。</span><span class="sxs-lookup"><span data-stu-id="22dcd-131">For information about project-level imported namespaces, see [References Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic).</span></span>  
  
 <span data-ttu-id="22dcd-132">各ソース ファイルは、任意の数を含めることができます`Imports`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="22dcd-132">Each source file can contain any number of `Imports` statements.</span></span> <span data-ttu-id="22dcd-133">これらなどのオプションを宣言を従う必要があります、`Option Strict`ステートメント、およびそれらの前にプログラミング要素など`Module`または`Class`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="22dcd-133">These must follow option declarations, such as the `Option Strict` statement, and they must precede programming element declarations, such as `Module` or `Class` statements.</span></span>  
  
## <a name="example"></a><span data-ttu-id="22dcd-134">例</span><span class="sxs-lookup"><span data-stu-id="22dcd-134">Example</span></span>  
 <span data-ttu-id="22dcd-135">次の例では、既定の XML 名前空間とプレフィックスで識別される XML 名前空間のインポート`ns`します。</span><span class="sxs-lookup"><span data-stu-id="22dcd-135">The following example imports a default XML namespace and an XML namespace identified with the prefix `ns`.</span></span> <span data-ttu-id="22dcd-136">両方の名前空間を使用して、XML リテラルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="22dcd-136">It then creates XML literals that use both namespaces.</span></span>  
  
 [!code-vb[VbXMLSamples#45](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/Module1.vb#45)]  
  
 <span data-ttu-id="22dcd-137">このコードを実行すると、次のテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="22dcd-137">This code displays the following text:</span></span>  
  
```xml  
<ns:outer xmlns="http://DefaultNamespace"   
          xmlns:ns="http://NewNamespace">  
  <ns:innerElement></ns:innerElement>  
  <siblingElement></siblingElement>  
  <innerElement />  
</ns:outer>  
```  
  
## <a name="example"></a><span data-ttu-id="22dcd-138">例</span><span class="sxs-lookup"><span data-stu-id="22dcd-138">Example</span></span>  
 <span data-ttu-id="22dcd-139">次の例は、XML 名前空間プレフィックスをインポート`ns`します。</span><span class="sxs-lookup"><span data-stu-id="22dcd-139">The following example imports the XML namespace prefix `ns`.</span></span> <span data-ttu-id="22dcd-140">名前空間プレフィックスを使用し、要素の最終的なフォームを表示する XML リテラルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="22dcd-140">It then creates an XML literal that uses the namespace prefix and displays the element's final form.</span></span>  
  
 [!code-vb[VbXMLSamples#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples10.vb#22)]  
  
 <span data-ttu-id="22dcd-141">このコードを実行すると、次のテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="22dcd-141">This code displays the following text:</span></span>  
  
```xml  
<ns:outer xmlns:ns="http://SomeNamespace">  
  <ns:middle xmlns:ns="http://NewNamespace">  
    <ns:inner1 />  
    <inner2 xmlns="http://SomeNamespace" />  
  </ns:middle>  
</ns:outer>  
```  
  
 <span data-ttu-id="22dcd-142">コンパイラが、ローカル プレフィックス定義へのグローバル プレフィックスから XML 名前空間プレフィックスを変換されたことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="22dcd-142">Notice that the compiler converted the XML namespace prefix from a global prefix to a local prefix definition.</span></span>  
  
## <a name="example"></a><span data-ttu-id="22dcd-143">例</span><span class="sxs-lookup"><span data-stu-id="22dcd-143">Example</span></span>  
 <span data-ttu-id="22dcd-144">次の例は、XML 名前空間プレフィックスをインポート`ns`します。</span><span class="sxs-lookup"><span data-stu-id="22dcd-144">The following example imports the XML namespace prefix `ns`.</span></span> <span data-ttu-id="22dcd-145">その後、この名前空間のプレフィックスを使用して XML リテラルを作成し、修飾名 `ns:name` を持つ最初の子ノードにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="22dcd-145">It then uses the prefix of the namespace to create an XML literal and access the first child node with the qualified name `ns:name`.</span></span>  
  
 [!code-vb[VbXMLSamples#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples8.vb#19)]  
  
 <span data-ttu-id="22dcd-146">このコードを実行すると、次のテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="22dcd-146">This code displays the following text:</span></span>  
  
 `Patrick Hines`  
  
## <a name="see-also"></a><span data-ttu-id="22dcd-147">関連項目</span><span class="sxs-lookup"><span data-stu-id="22dcd-147">See also</span></span>

- [<span data-ttu-id="22dcd-148">XML 要素リテラル</span><span class="sxs-lookup"><span data-stu-id="22dcd-148">XML Element Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [<span data-ttu-id="22dcd-149">XML 軸プロパティ</span><span class="sxs-lookup"><span data-stu-id="22dcd-149">XML Axis Properties</span></span>](../../../visual-basic/language-reference/xml-axis/index.md)
- [<span data-ttu-id="22dcd-150">宣言する XML 要素と属性の名前</span><span class="sxs-lookup"><span data-stu-id="22dcd-150">Names of Declared XML Elements and Attributes</span></span>](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
- [<span data-ttu-id="22dcd-151">GetXmlNamespace 演算子</span><span class="sxs-lookup"><span data-stu-id="22dcd-151">GetXmlNamespace Operator</span></span>](../../../visual-basic/language-reference/operators/getxmlnamespace-operator.md)
