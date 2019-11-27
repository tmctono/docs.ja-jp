---
title: XML の操作
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ to XML [Visual Basic], manipulating XML
- Visual Basic code, XML
- XML [Visual Basic], manipulating
ms.assetid: da32cffb-198d-41b1-9af3-260fe32e3b7d
ms.openlocfilehash: 2565f43c1014bf0fa9fab1618fedfd1bd6bdb7ca
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74330439"
---
# <a name="manipulating-xml-in-visual-basic"></a><span data-ttu-id="0665d-102">Visual Basic での XML の操作</span><span class="sxs-lookup"><span data-stu-id="0665d-102">Manipulating XML in Visual Basic</span></span>
<span data-ttu-id="0665d-103">*Xml リテラル*を使用して、文字列、ファイル、ストリームなどの外部ソースから xml を読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="0665d-103">You can use *XML literals* to load XML from an external source such as a string, file, or stream.</span></span> <span data-ttu-id="0665d-104">次に、[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] を使用して XML を操作し、[!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] を使用して XML にクエリを実行できます。</span><span class="sxs-lookup"><span data-stu-id="0665d-104">You can then use [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] to manipulate the XML and use [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] to query the XML.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0665d-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="0665d-105">In This Section</span></span>  
 [<span data-ttu-id="0665d-106">方法 : ファイル、文字列、またはストリームからの XML の読み込み</span><span class="sxs-lookup"><span data-stu-id="0665d-106">How to: Load XML from a File, String, or Stream</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md)  
 <span data-ttu-id="0665d-107">テキストファイル、文字列、またはストリームから <xref:System.Xml.Linq.XDocument> または <xref:System.Xml.Linq.XElement> オブジェクトに XML を読み込む方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0665d-107">Demonstrates how to load XML into an <xref:System.Xml.Linq.XDocument> or <xref:System.Xml.Linq.XElement> object from a text file, string, or stream.</span></span>  
  
 [<span data-ttu-id="0665d-108">方法 : LINQ を使用した XML の変換</span><span class="sxs-lookup"><span data-stu-id="0665d-108">How to: Transform XML by Using LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-transform-xml-by-using-linq.md)  
 <span data-ttu-id="0665d-109"><xref:System.Xml.Linq.XDocument> オブジェクトの内容を新しい XML ドキュメントに変換する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="0665d-109">Demonstrates how to transform the contents of an <xref:System.Xml.Linq.XDocument> object into a new XML document.</span></span>  
  
 [<span data-ttu-id="0665d-110">方法 : XML リテラルの変更</span><span class="sxs-lookup"><span data-stu-id="0665d-110">How to: Modify XML Literals</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-modify-xml-literals.md)  
 <span data-ttu-id="0665d-111">XML リテラル内の要素、属性、および値を変更する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="0665d-111">Demonstrates how to modify the elements, attributes, and values in an XML literal.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="0665d-112">関連セクション</span><span class="sxs-lookup"><span data-stu-id="0665d-112">Related Sections</span></span>  
 [<span data-ttu-id="0665d-113">XML 軸プロパティ</span><span class="sxs-lookup"><span data-stu-id="0665d-113">XML Axis Properties</span></span>](../../../../visual-basic/language-reference/xml-axis/index.md)  
 <span data-ttu-id="0665d-114">さまざまな XML アクセスプロパティについて説明するセクションへのリンクを示します。</span><span class="sxs-lookup"><span data-stu-id="0665d-114">Provides links to sections that describe the various XML access properties.</span></span>  
  
 [<span data-ttu-id="0665d-115">Visual Basic における LINQ to XML の概要</span><span class="sxs-lookup"><span data-stu-id="0665d-115">Overview of LINQ to XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/overview-of-linq-to-xml.md)  
 <span data-ttu-id="0665d-116">Visual Basic での [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] の使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0665d-116">Provides an introduction to using [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in Visual Basic.</span></span>  
  
 [<span data-ttu-id="0665d-117">Visual Basic での XML の作成</span><span class="sxs-lookup"><span data-stu-id="0665d-117">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 <span data-ttu-id="0665d-118">Visual Basic での XML リテラルの使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0665d-118">Provides an introduction to using XML literals in Visual Basic.</span></span>  
  
 [<span data-ttu-id="0665d-119">Visual Basic での XML へのアクセス</span><span class="sxs-lookup"><span data-stu-id="0665d-119">Accessing XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)  
 <span data-ttu-id="0665d-120">Visual Basic 内の XML 要素またはドキュメントの一部にアクセスする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="0665d-120">Demonstrates how to access parts of an XML element or document in Visual Basic.</span></span>  
  
 [<span data-ttu-id="0665d-121">XML</span><span class="sxs-lookup"><span data-stu-id="0665d-121">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 <span data-ttu-id="0665d-122">Visual Basic での [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] の使用方法について説明するセクションへのリンクを示します。</span><span class="sxs-lookup"><span data-stu-id="0665d-122">Provides links to sections that describe how to use [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in Visual Basic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0665d-123">参照</span><span class="sxs-lookup"><span data-stu-id="0665d-123">See also</span></span>

- [<span data-ttu-id="0665d-124">XML</span><span class="sxs-lookup"><span data-stu-id="0665d-124">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
- [<span data-ttu-id="0665d-125">LINQ</span><span class="sxs-lookup"><span data-stu-id="0665d-125">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="0665d-126">Visual Basic における LINQ の概要</span><span class="sxs-lookup"><span data-stu-id="0665d-126">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
