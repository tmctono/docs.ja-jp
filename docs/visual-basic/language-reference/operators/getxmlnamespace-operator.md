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
ms.openlocfilehash: 660474c1193076755889fd885c1b78bec78f0a2c
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873477"
---
# <a name="getxmlnamespace-operator-visual-basic"></a><span data-ttu-id="62271-102">GetXmlNamespace 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="62271-102">GetXmlNamespace Operator (Visual Basic)</span></span>

<span data-ttu-id="62271-103">指定した XML 名前空間プレフィックスに対応する <xref:System.Xml.Linq.XNamespace> オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="62271-103">Gets the <xref:System.Xml.Linq.XNamespace> object that corresponds to the specified XML namespace prefix.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62271-104">構文</span><span class="sxs-lookup"><span data-stu-id="62271-104">Syntax</span></span>  
  
```vb  
GetXmlNamespace(xmlNamespacePrefix)  
```  
  
## <a name="parts"></a><span data-ttu-id="62271-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="62271-105">Parts</span></span>  

 `xmlNamespacePrefix`  
 <span data-ttu-id="62271-106">任意。</span><span class="sxs-lookup"><span data-stu-id="62271-106">Optional.</span></span> <span data-ttu-id="62271-107">XML 名前空間プレフィックスを識別する文字列です。</span><span class="sxs-lookup"><span data-stu-id="62271-107">The string that identifies the XML namespace prefix.</span></span> <span data-ttu-id="62271-108">指定する場合、文字列は有効な XML 識別子である必要があります。</span><span class="sxs-lookup"><span data-stu-id="62271-108">If supplied, this string must be a valid XML identifier.</span></span> <span data-ttu-id="62271-109">詳細については、「[宣言する XML 要素と属性の名前](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="62271-109">For more information, see [Names of Declared XML Elements and Attributes](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span> <span data-ttu-id="62271-110">プレフィックスが指定されていない場合は、既定の名前空間が返されます。</span><span class="sxs-lookup"><span data-stu-id="62271-110">If no prefix is specified, the default namespace is returned.</span></span> <span data-ttu-id="62271-111">既定の名前空間が指定されていない場合は、空の名前空間が返されます。</span><span class="sxs-lookup"><span data-stu-id="62271-111">If no default namespace is specified, the empty namespace is returned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="62271-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="62271-112">Return Value</span></span>  

 <span data-ttu-id="62271-113">XML 名前空間プレフィックスに対応する <xref:System.Xml.Linq.XNamespace> オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="62271-113">The <xref:System.Xml.Linq.XNamespace> object that corresponds to the XML namespace prefix.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="62271-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="62271-114">Remarks</span></span>  

 <span data-ttu-id="62271-115">`GetXmlNamespace` 演算子は、XML 名前空間プレフィックス `xmlNamespacePrefix` に対応する <xref:System.Xml.Linq.XNamespace> オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="62271-115">The `GetXmlNamespace` operator gets the <xref:System.Xml.Linq.XNamespace> object that corresponds to the XML namespace prefix `xmlNamespacePrefix`.</span></span>  
  
 <span data-ttu-id="62271-116">XML 名前空間プレフィックスは、XML リテラルと XML 軸プロパティで直接使用できます。</span><span class="sxs-lookup"><span data-stu-id="62271-116">You can use XML namespace prefixes directly in XML literals and XML axis properties.</span></span> <span data-ttu-id="62271-117">ただし、コードで名前空間プレフィックスを使用する前に、`GetXmlNamespace` 演算子を使用して、それを <xref:System.Xml.Linq.XNamespace> オブジェクトに変換しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="62271-117">However, you must use the `GetXmlNamespace` operator to convert a namespace prefix to an <xref:System.Xml.Linq.XNamespace> object before you can use it in your code.</span></span> <span data-ttu-id="62271-118"><xref:System.Xml.Linq.XNamespace> オブジェクトに非修飾要素名を追加して、多くの [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] メソッドで必要となる完全修飾 <xref:System.Xml.Linq.XName> オブジェクトを取得できます。</span><span class="sxs-lookup"><span data-stu-id="62271-118">You can append an unqualified element name to an <xref:System.Xml.Linq.XNamespace> object to get a fully qualified <xref:System.Xml.Linq.XName> object, which many [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] methods require.</span></span>  
  
## <a name="example"></a><span data-ttu-id="62271-119">例</span><span class="sxs-lookup"><span data-stu-id="62271-119">Example</span></span>  

 <span data-ttu-id="62271-120">次の例では、名前空間プレフィックスとして `ns` をインポートしています。</span><span class="sxs-lookup"><span data-stu-id="62271-120">The following example imports `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="62271-121">その後、この名前空間のプレフィックスを使用して XML リテラルを作成し、修飾名が `ns:phone` である最初の子ノードにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="62271-121">It then uses the prefix of the namespace to create an XML literal and access the first child node that has the qualified name `ns:phone`.</span></span> <span data-ttu-id="62271-122">次に、その子ノードを `ShowName` サブルーチンに渡します。これにより、`GetXmlNamespace` 演算子を使用して修飾名が作成されます。</span><span class="sxs-lookup"><span data-stu-id="62271-122">It then passes that child node to the `ShowName` subroutine, which constructs a qualified name by using the `GetXmlNamespace` operator.</span></span> <span data-ttu-id="62271-123">次に、`ShowName` サブルーチンが修飾名を <xref:System.Xml.Linq.XNode.Ancestors%2A> メソッドに渡して、親の `ns:contact` ノードを取得します。</span><span class="sxs-lookup"><span data-stu-id="62271-123">The `ShowName` subroutine then passes the qualified name to the <xref:System.Xml.Linq.XNode.Ancestors%2A> method to get the parent `ns:contact` node.</span></span>  
  
 [!code-vb[VbXMLSamples#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/GetXmlNamespace.vb#38)]  
  
 <span data-ttu-id="62271-124">`TestGetXmlNamespace.RunSample()` を呼び出すと、次のテキストを含むメッセージ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="62271-124">When you call `TestGetXmlNamespace.RunSample()`, it displays a message box that contains the following text:</span></span>  
  
 `Name: Patrick Hines`  
  
## <a name="see-also"></a><span data-ttu-id="62271-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="62271-125">See also</span></span>

- [<span data-ttu-id="62271-126">Imports ステートメント (XML 名前空間)</span><span class="sxs-lookup"><span data-stu-id="62271-126">Imports Statement (XML Namespace)</span></span>](../statements/imports-statement-xml-namespace.md)
- [<span data-ttu-id="62271-127">Visual Basic での XML へのアクセス</span><span class="sxs-lookup"><span data-stu-id="62271-127">Accessing XML in Visual Basic</span></span>](../../programming-guide/language-features/xml/accessing-xml.md)
