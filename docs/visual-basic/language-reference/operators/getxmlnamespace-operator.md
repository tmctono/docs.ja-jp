---
title: GetXmlNamespace 演算子
ms.date: 07/20/2015
f1_keywords:
- vb.GetXmlNamespace
- GetXmlNamespace
helpviewer_keywords:
- GetXmlNamespace operator [Visual Basic]
- GetXmlNamespace keyword [Visual Basic]
ms.assetid: d0d28cfd-0755-4896-ae0b-4981aa35517c
ms.openlocfilehash: 4d6e738f4e3a47d73e37c395dd74fe19e99d81bd
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353192"
---
# <a name="getxmlnamespace-operator-visual-basic"></a><span data-ttu-id="adf0c-102">GetXmlNamespace 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="adf0c-102">GetXmlNamespace Operator (Visual Basic)</span></span>
<span data-ttu-id="adf0c-103">指定した XML 名前空間プレフィックスに対応する <xref:System.Xml.Linq.XNamespace> オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="adf0c-103">Gets the <xref:System.Xml.Linq.XNamespace> object that corresponds to the specified XML namespace prefix.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="adf0c-104">構文</span><span class="sxs-lookup"><span data-stu-id="adf0c-104">Syntax</span></span>  
  
```vb  
GetXmlNamespace(xmlNamespacePrefix)  
```  
  
## <a name="parts"></a><span data-ttu-id="adf0c-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="adf0c-105">Parts</span></span>  
 `xmlNamespacePrefix`  
 <span data-ttu-id="adf0c-106">省略可能。</span><span class="sxs-lookup"><span data-stu-id="adf0c-106">Optional.</span></span> <span data-ttu-id="adf0c-107">XML 名前空間プレフィックスを識別する文字列です。</span><span class="sxs-lookup"><span data-stu-id="adf0c-107">The string that identifies the XML namespace prefix.</span></span> <span data-ttu-id="adf0c-108">指定する場合、この文字列は有効な XML 識別子である必要があります。</span><span class="sxs-lookup"><span data-stu-id="adf0c-108">If supplied, this string must be a valid XML identifier.</span></span> <span data-ttu-id="adf0c-109">詳細については、「[宣言する XML 要素と属性の名前](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="adf0c-109">For more information, see [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span> <span data-ttu-id="adf0c-110">プレフィックスが指定されていない場合は、既定の名前空間が返されます。</span><span class="sxs-lookup"><span data-stu-id="adf0c-110">If no prefix is specified, the default namespace is returned.</span></span> <span data-ttu-id="adf0c-111">既定の名前空間が指定されていない場合は、空の名前空間が返されます。</span><span class="sxs-lookup"><span data-stu-id="adf0c-111">If no default namespace is specified, the empty namespace is returned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="adf0c-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="adf0c-112">Return Value</span></span>  
 <span data-ttu-id="adf0c-113">XML 名前空間プレフィックスに対応する <xref:System.Xml.Linq.XNamespace> オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="adf0c-113">The <xref:System.Xml.Linq.XNamespace> object that corresponds to the XML namespace prefix.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="adf0c-114">コメント</span><span class="sxs-lookup"><span data-stu-id="adf0c-114">Remarks</span></span>  
 <span data-ttu-id="adf0c-115">`GetXmlNamespace` 演算子は、XML 名前空間プレフィックス `xmlNamespacePrefix`に対応する <xref:System.Xml.Linq.XNamespace> オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="adf0c-115">The `GetXmlNamespace` operator gets the <xref:System.Xml.Linq.XNamespace> object that corresponds to the XML namespace prefix `xmlNamespacePrefix`.</span></span>  
  
 <span data-ttu-id="adf0c-116">Xml 名前空間プレフィックスは、xml リテラルおよび XML 軸プロパティで直接使用できます。</span><span class="sxs-lookup"><span data-stu-id="adf0c-116">You can use XML namespace prefixes directly in XML literals and XML axis properties.</span></span> <span data-ttu-id="adf0c-117">ただし、コードで使用するには、`GetXmlNamespace` 演算子を使用して、名前空間プレフィックスを <xref:System.Xml.Linq.XNamespace> オブジェクトに変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="adf0c-117">However, you must use the `GetXmlNamespace` operator to convert a namespace prefix to an <xref:System.Xml.Linq.XNamespace> object before you can use it in your code.</span></span> <span data-ttu-id="adf0c-118"><xref:System.Xml.Linq.XNamespace> オブジェクトに修飾されていない要素名を追加して、完全修飾 <xref:System.Xml.Linq.XName> オブジェクトを取得できます。これには、多くの [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] メソッドが必要です。</span><span class="sxs-lookup"><span data-stu-id="adf0c-118">You can append an unqualified element name to an <xref:System.Xml.Linq.XNamespace> object to get a fully qualified <xref:System.Xml.Linq.XName> object, which many [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] methods require.</span></span>  
  
## <a name="example"></a><span data-ttu-id="adf0c-119">例</span><span class="sxs-lookup"><span data-stu-id="adf0c-119">Example</span></span>  
 <span data-ttu-id="adf0c-120">次の例では、`ns` を XML 名前空間プレフィックスとしてインポートします。</span><span class="sxs-lookup"><span data-stu-id="adf0c-120">The following example imports `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="adf0c-121">次に、名前空間のプレフィックスを使用して XML リテラルを作成し、修飾名 `ns:phone`を持つ最初の子ノードにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="adf0c-121">It then uses the prefix of the namespace to create an XML literal and access the first child node that has the qualified name `ns:phone`.</span></span> <span data-ttu-id="adf0c-122">次に、その子ノードを `ShowName` サブルーチンに渡します。これにより、`GetXmlNamespace` 演算子を使用して修飾名が構築されます。</span><span class="sxs-lookup"><span data-stu-id="adf0c-122">It then passes that child node to the `ShowName` subroutine, which constructs a qualified name by using the `GetXmlNamespace` operator.</span></span> <span data-ttu-id="adf0c-123">次に、`ShowName` サブルーチンは修飾名を <xref:System.Xml.Linq.XNode.Ancestors%2A> メソッドに渡して、親 `ns:contact` ノードを取得します。</span><span class="sxs-lookup"><span data-stu-id="adf0c-123">The `ShowName` subroutine then passes the qualified name to the <xref:System.Xml.Linq.XNode.Ancestors%2A> method to get the parent `ns:contact` node.</span></span>  
  
 [!code-vb[VbXMLSamples#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/GetXmlNamespace.vb#38)]  
  
 <span data-ttu-id="adf0c-124">`TestGetXmlNamespace.RunSample()`を呼び出すと、次のテキストを含むメッセージボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="adf0c-124">When you call `TestGetXmlNamespace.RunSample()`, it displays a message box that contains the following text:</span></span>  
  
 `Name: Patrick Hines`  
  
## <a name="see-also"></a><span data-ttu-id="adf0c-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="adf0c-125">See also</span></span>

- [<span data-ttu-id="adf0c-126">Imports ステートメント (XML 名前空間)</span><span class="sxs-lookup"><span data-stu-id="adf0c-126">Imports Statement (XML Namespace)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)
- [<span data-ttu-id="adf0c-127">Visual Basic での XML へのアクセス</span><span class="sxs-lookup"><span data-stu-id="adf0c-127">Accessing XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)
