---
title: XML の操作
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ to XML [Visual Basic], manipulating XML
- Visual Basic code, XML
- XML [Visual Basic], manipulating
ms.assetid: da32cffb-198d-41b1-9af3-260fe32e3b7d
ms.openlocfilehash: bb5aed5099d81f8c8898cd61523b90a43f27db78
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/03/2020
ms.locfileid: "75636160"
---
# <a name="manipulating-xml-in-visual-basic"></a><span data-ttu-id="8bfc8-102">Visual Basic での XML の操作</span><span class="sxs-lookup"><span data-stu-id="8bfc8-102">Manipulating XML in Visual Basic</span></span>
<span data-ttu-id="8bfc8-103">*XML リテラル*を使用すると、文字列、ファイル、ストリームなどの外部ソースから XML を読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="8bfc8-103">You can use *XML literals* to load XML from an external source such as a string, file, or stream.</span></span> <span data-ttu-id="8bfc8-104">さらに、[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] を使用して XML を操作し、統合言語クエリ (LINQ) を使用して XML をクエリできます。</span><span class="sxs-lookup"><span data-stu-id="8bfc8-104">You can then use [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] to manipulate the XML and use Language-Integrated Query (LINQ) to query the XML.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8bfc8-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="8bfc8-105">In This Section</span></span>  
 [<span data-ttu-id="8bfc8-106">方法: ファイル、文字列、またはストリームからの XML の読み込み</span><span class="sxs-lookup"><span data-stu-id="8bfc8-106">How to: Load XML from a File, String, or Stream</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md)  
 <span data-ttu-id="8bfc8-107">テキスト ファイル、文字列、またはストリームから <xref:System.Xml.Linq.XDocument> または <xref:System.Xml.Linq.XElement> オブジェクトに XML を読み込む方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8bfc8-107">Demonstrates how to load XML into an <xref:System.Xml.Linq.XDocument> or <xref:System.Xml.Linq.XElement> object from a text file, string, or stream.</span></span>  
  
 [<span data-ttu-id="8bfc8-108">方法: LINQ を使用した XML の変換</span><span class="sxs-lookup"><span data-stu-id="8bfc8-108">How to: Transform XML by Using LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-transform-xml-by-using-linq.md)  
 <span data-ttu-id="8bfc8-109"><xref:System.Xml.Linq.XDocument> オブジェクトの内容を新しい XML ドキュメントに変換する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="8bfc8-109">Demonstrates how to transform the contents of an <xref:System.Xml.Linq.XDocument> object into a new XML document.</span></span>  
  
 [<span data-ttu-id="8bfc8-110">方法: XML リテラルの変更</span><span class="sxs-lookup"><span data-stu-id="8bfc8-110">How to: Modify XML Literals</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-modify-xml-literals.md)  
 <span data-ttu-id="8bfc8-111">XML リテラル内の要素、属性、および値を変更する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="8bfc8-111">Demonstrates how to modify the elements, attributes, and values in an XML literal.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="8bfc8-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="8bfc8-112">Related Sections</span></span>  
 [<span data-ttu-id="8bfc8-113">XML 軸プロパティ</span><span class="sxs-lookup"><span data-stu-id="8bfc8-113">XML Axis Properties</span></span>](../../../../visual-basic/language-reference/xml-axis/index.md)  
 <span data-ttu-id="8bfc8-114">さまざまな XML アクセス プロパティについて説明するセクションへのリンクを示します。</span><span class="sxs-lookup"><span data-stu-id="8bfc8-114">Provides links to sections that describe the various XML access properties.</span></span>  
  
 [<span data-ttu-id="8bfc8-115">Visual Basic における LINQ to XML の概要</span><span class="sxs-lookup"><span data-stu-id="8bfc8-115">Overview of LINQ to XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/overview-of-linq-to-xml.md)  
 <span data-ttu-id="8bfc8-116">Visual Basic での [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] の使用の概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="8bfc8-116">Provides an introduction to using [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in Visual Basic.</span></span>  
  
 [<span data-ttu-id="8bfc8-117">Visual Basic での XML の作成</span><span class="sxs-lookup"><span data-stu-id="8bfc8-117">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 <span data-ttu-id="8bfc8-118">Visual Basic での XML リテラルの使用の概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="8bfc8-118">Provides an introduction to using XML literals in Visual Basic.</span></span>  
  
 [<span data-ttu-id="8bfc8-119">Visual Basic での XML へのアクセス</span><span class="sxs-lookup"><span data-stu-id="8bfc8-119">Accessing XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)  
 <span data-ttu-id="8bfc8-120">Visual Basic で XML 要素またはドキュメントの一部にアクセスする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="8bfc8-120">Demonstrates how to access parts of an XML element or document in Visual Basic.</span></span>  
  
 [<span data-ttu-id="8bfc8-121">XML</span><span class="sxs-lookup"><span data-stu-id="8bfc8-121">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 <span data-ttu-id="8bfc8-122">Visual Basic での [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] の使用方法を説明するセクションへのリンクを示します。</span><span class="sxs-lookup"><span data-stu-id="8bfc8-122">Provides links to sections that describe how to use [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in Visual Basic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bfc8-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="8bfc8-123">See also</span></span>

- [<span data-ttu-id="8bfc8-124">XML</span><span class="sxs-lookup"><span data-stu-id="8bfc8-124">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
- [<span data-ttu-id="8bfc8-125">LINQ</span><span class="sxs-lookup"><span data-stu-id="8bfc8-125">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="8bfc8-126">Visual Basic における LINQ の概要</span><span class="sxs-lookup"><span data-stu-id="8bfc8-126">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
