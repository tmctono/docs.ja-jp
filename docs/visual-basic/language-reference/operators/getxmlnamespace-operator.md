---
title: GetXmlNamespace 演算子 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.GetXmlNamespace
- GetXmlNamespace
helpviewer_keywords:
- GetXmlNamespace operator [Visual Basic]
- GetXmlNamespace keyword [Visual Basic]
ms.assetid: d0d28cfd-0755-4896-ae0b-4981aa35517c
ms.openlocfilehash: bfccdcd9b5d35418b206dfa9fefffb5ddab69c66
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/28/2019
ms.locfileid: "71592165"
---
# <a name="getxmlnamespace-operator-visual-basic"></a><span data-ttu-id="21c50-102">GetXmlNamespace 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="21c50-102">GetXmlNamespace Operator (Visual Basic)</span></span>
<span data-ttu-id="21c50-103">指定した XML 名前空間プレフィックスに対応する @no__t 0 オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="21c50-103">Gets the <xref:System.Xml.Linq.XNamespace> object that corresponds to the specified XML namespace prefix.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21c50-104">構文</span><span class="sxs-lookup"><span data-stu-id="21c50-104">Syntax</span></span>  
  
```vb  
GetXmlNamespace(xmlNamespacePrefix)  
```  
  
## <a name="parts"></a><span data-ttu-id="21c50-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="21c50-105">Parts</span></span>  
 `xmlNamespacePrefix`  
 <span data-ttu-id="21c50-106">任意。</span><span class="sxs-lookup"><span data-stu-id="21c50-106">Optional.</span></span> <span data-ttu-id="21c50-107">XML 名前空間プレフィックスを識別する文字列。</span><span class="sxs-lookup"><span data-stu-id="21c50-107">The string that identifies the XML namespace prefix.</span></span> <span data-ttu-id="21c50-108">指定する場合、この文字列は有効な XML 識別子である必要があります。</span><span class="sxs-lookup"><span data-stu-id="21c50-108">If supplied, this string must be a valid XML identifier.</span></span> <span data-ttu-id="21c50-109">詳細については、「宣言され[た XML 要素と属性の名前](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="21c50-109">For more information, see [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span> <span data-ttu-id="21c50-110">プレフィックスが指定されていない場合は、既定の名前空間が返されます。</span><span class="sxs-lookup"><span data-stu-id="21c50-110">If no prefix is specified, the default namespace is returned.</span></span> <span data-ttu-id="21c50-111">既定の名前空間が指定されていない場合は、空の名前空間が返されます。</span><span class="sxs-lookup"><span data-stu-id="21c50-111">If no default namespace is specified, the empty namespace is returned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="21c50-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="21c50-112">Return Value</span></span>  
 <span data-ttu-id="21c50-113">XML 名前空間プレフィックスに対応する @no__t 0 オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="21c50-113">The <xref:System.Xml.Linq.XNamespace> object that corresponds to the XML namespace prefix.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="21c50-114">コメント</span><span class="sxs-lookup"><span data-stu-id="21c50-114">Remarks</span></span>  
 <span data-ttu-id="21c50-115">@No__t-0 演算子は、XML 名前空間プレフィックス `xmlNamespacePrefix` に対応する @no__t 1 オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="21c50-115">The `GetXmlNamespace` operator gets the <xref:System.Xml.Linq.XNamespace> object that corresponds to the XML namespace prefix `xmlNamespacePrefix`.</span></span>  
  
 <span data-ttu-id="21c50-116">Xml 名前空間プレフィックスは、xml リテラルおよび XML 軸プロパティで直接使用できます。</span><span class="sxs-lookup"><span data-stu-id="21c50-116">You can use XML namespace prefixes directly in XML literals and XML axis properties.</span></span> <span data-ttu-id="21c50-117">ただし、コードで使用するには、`GetXmlNamespace` 演算子を使用して、名前空間プレフィックスを <xref:System.Xml.Linq.XNamespace> オブジェクトに変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="21c50-117">However, you must use the `GetXmlNamespace` operator to convert a namespace prefix to an <xref:System.Xml.Linq.XNamespace> object before you can use it in your code.</span></span> <span data-ttu-id="21c50-118">修飾されていない要素名を <xref:System.Xml.Linq.XNamespace> オブジェクトに追加して、完全修飾 <xref:System.Xml.Linq.XName> オブジェクトを取得できます。これには、多くの @no__t 2 つのメソッドが必要です。</span><span class="sxs-lookup"><span data-stu-id="21c50-118">You can append an unqualified element name to an <xref:System.Xml.Linq.XNamespace> object to get a fully qualified <xref:System.Xml.Linq.XName> object, which many [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] methods require.</span></span>  
  
## <a name="example"></a><span data-ttu-id="21c50-119">例</span><span class="sxs-lookup"><span data-stu-id="21c50-119">Example</span></span>  
 <span data-ttu-id="21c50-120">次の例では、`ns` を XML 名前空間プレフィックスとしてインポートします。</span><span class="sxs-lookup"><span data-stu-id="21c50-120">The following example imports `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="21c50-121">次に、名前空間のプレフィックスを使用して XML リテラルを作成し、修飾名が `ns:phone` の最初の子ノードにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="21c50-121">It then uses the prefix of the namespace to create an XML literal and access the first child node that has the qualified name `ns:phone`.</span></span> <span data-ttu-id="21c50-122">次に、その子ノードを @no__t 0 のサブルーチンに渡します。このサブルーチンは、`GetXmlNamespace` 演算子を使用して修飾名を構築します。</span><span class="sxs-lookup"><span data-stu-id="21c50-122">It then passes that child node to the `ShowName` subroutine, which constructs a qualified name by using the `GetXmlNamespace` operator.</span></span> <span data-ttu-id="21c50-123">次に、@no__t 0 のサブルーチンは、修飾名を <xref:System.Xml.Linq.XNode.Ancestors%2A> メソッドに渡して、親 `ns:contact` ノードを取得します。</span><span class="sxs-lookup"><span data-stu-id="21c50-123">The `ShowName` subroutine then passes the qualified name to the <xref:System.Xml.Linq.XNode.Ancestors%2A> method to get the parent `ns:contact` node.</span></span>  
  
 [!code-vb[VbXMLSamples#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/GetXmlNamespace.vb#38)]  
  
 <span data-ttu-id="21c50-124">@No__t-0 を呼び出すと、次のテキストを含むメッセージボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="21c50-124">When you call `TestGetXmlNamespace.RunSample()`, it displays a message box that contains the following text:</span></span>  
  
 `Name: Patrick Hines`  
  
## <a name="see-also"></a><span data-ttu-id="21c50-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="21c50-125">See also</span></span>

- [<span data-ttu-id="21c50-126">Imports ステートメント (XML 名前空間)</span><span class="sxs-lookup"><span data-stu-id="21c50-126">Imports Statement (XML Namespace)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)
- [<span data-ttu-id="21c50-127">Visual Basic での XML へのアクセス</span><span class="sxs-lookup"><span data-stu-id="21c50-127">Accessing XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)
