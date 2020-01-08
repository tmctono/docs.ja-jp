---
title: LINQ to XML の概要
ms.date: 07/20/2015
ms.assetid: 502661e0-bc5d-438d-94c2-7efb63bb6fbd
ms.openlocfilehash: a30340e06a3f8eac9fe2b7718b14ba20363d682f
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/03/2020
ms.locfileid: "75636472"
---
# <a name="linq-to-xml-overview-visual-basic"></a><span data-ttu-id="57fc6-102">LINQ to XML の概要 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="57fc6-102">LINQ to XML Overview (Visual Basic)</span></span>
<span data-ttu-id="57fc6-103">XML は、多くのコンテキストでデータを書式設定する方法として広く採用されてきました。</span><span class="sxs-lookup"><span data-stu-id="57fc6-103">XML has been widely adopted as a way to format data in many contexts.</span></span> <span data-ttu-id="57fc6-104">たとえば、Web、構成ファイル、Microsoft Office Word ファイル、データベースで XML が使用されています。</span><span class="sxs-lookup"><span data-stu-id="57fc6-104">For example, you can find XML on the Web, in configuration files, in Microsoft Office Word files, and in databases.</span></span>  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="57fc6-105">は、XML によるプログラミングのために再設計された最新の方法です。</span><span class="sxs-lookup"><span data-stu-id="57fc6-105">is an up-to-date, redesigned approach to programming with XML.</span></span> <span data-ttu-id="57fc6-106">これは、ドキュメントオブジェクトモデル (DOM) のインメモリドキュメント変更機能を提供し、LINQ クエリ式をサポートします。</span><span class="sxs-lookup"><span data-stu-id="57fc6-106">It provides the in-memory document-modification capabilities of the Document Object Model (DOM) and supports LINQ query expressions.</span></span> <span data-ttu-id="57fc6-107">このクエリ式は、XPath と構文は異なりますが、機能が似ています。</span><span class="sxs-lookup"><span data-stu-id="57fc6-107">Although these query expressions are syntactically different from XPath, they provide similar functionality.</span></span>  
  
## <a name="linq-to-xml-developers"></a><span data-ttu-id="57fc6-108">LINQ to XML の開発者</span><span class="sxs-lookup"><span data-stu-id="57fc6-108">LINQ to XML Developers</span></span>  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="57fc6-109">は、さまざまな開発者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="57fc6-109">targets a variety of developers.</span></span> <span data-ttu-id="57fc6-110">何らかの処理を行うだけの平均的な開発者にとっては、[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] によって SQL と同じようにクエリを作成できるので、XML の操作がより簡単になります。</span><span class="sxs-lookup"><span data-stu-id="57fc6-110">For an average developer who just wants to get something done, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] makes XML easier by providing a query experience that is similar to SQL.</span></span> <span data-ttu-id="57fc6-111">プログラマは、短時間の学習で簡潔かつ強力なクエリを、選択したプログラミング言語で記述できるようになります。</span><span class="sxs-lookup"><span data-stu-id="57fc6-111">With just a bit of study, programmers can learn to write succinct and powerful queries in their programming language of choice.</span></span>  
  
 <span data-ttu-id="57fc6-112">熟練した開発者は、[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] を使用することで生産性を大きく高めることができます。</span><span class="sxs-lookup"><span data-stu-id="57fc6-112">Professional developers can use [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] to greatly increase their productivity.</span></span> <span data-ttu-id="57fc6-113">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] を使用すると、より少ないコードで、表現性と簡潔性に優れた強力なコードを記述できます。</span><span class="sxs-lookup"><span data-stu-id="57fc6-113">With [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], they can write less code that is more expressive, more compact, and more powerful.</span></span> <span data-ttu-id="57fc6-114">また、同時に複数のデータ ドメインからクエリ式を使用できます。</span><span class="sxs-lookup"><span data-stu-id="57fc6-114">They can use query expressions from multiple data domains at the same time.</span></span>  
  
## <a name="what-is-linq-to-xml"></a><span data-ttu-id="57fc6-115">LINQ to XML とは</span><span class="sxs-lookup"><span data-stu-id="57fc6-115">What Is LINQ to XML?</span></span>  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="57fc6-116">は、.NET Framework プログラミング言語から XML を操作できるようにする、LINQ に対応したメモリ内 XML プログラミング インターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="57fc6-116">is a LINQ-enabled, in-memory XML programming interface that enables you to work with XML from within the .NET Framework programming languages.</span></span>  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="57fc6-117">は、XML ドキュメントをメモリに読み込むという点で、ドキュメント オブジェクト モデル (DOM) に似ています。</span><span class="sxs-lookup"><span data-stu-id="57fc6-117">is like the Document Object Model (DOM) in that it brings the XML document into memory.</span></span> <span data-ttu-id="57fc6-118">ドキュメントに対するクエリや変更を行うことができ、変更したドキュメントをファイルに保存したり、シリアル化してインターネット経由で送信したりできます。</span><span class="sxs-lookup"><span data-stu-id="57fc6-118">You can query and modify the document, and after you modify it you can save it to a file or serialize it and send it over the Internet.</span></span> <span data-ttu-id="57fc6-119">ただし、[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] は DOM とは異なります。これは、より軽量で使いやすく、Visual Basic の言語機能を利用する新しいオブジェクトモデルを提供します。</span><span class="sxs-lookup"><span data-stu-id="57fc6-119">However, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] differs from DOM: It provides a new object model that is lighter weight and easier to work with, and that takes advantage of language features in Visual Basic.</span></span>  
  
 <span data-ttu-id="57fc6-120">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] の最も重要な利点は、統合言語クエリ (LINQ) との統合です。</span><span class="sxs-lookup"><span data-stu-id="57fc6-120">The most important advantage of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] is its integration with Language-Integrated Query (LINQ).</span></span> <span data-ttu-id="57fc6-121">この統合により、メモリ内の XML ドキュメントに対するクエリを記述して、要素および属性のコレクションを取得できます。</span><span class="sxs-lookup"><span data-stu-id="57fc6-121">This integration enables you to write queries on the in-memory XML document to retrieve collections of elements and attributes.</span></span> <span data-ttu-id="57fc6-122">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] のクエリ機能は、構文は異なりますが、XPath および XQuery と機能面で互換性があります。</span><span class="sxs-lookup"><span data-stu-id="57fc6-122">The query capability of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] is comparable in functionality (although not in syntax) to XPath and XQuery.</span></span> <span data-ttu-id="57fc6-123">Visual Basic での LINQ の統合により、より厳密な型指定、コンパイル時チェック、および強化されたデバッガーサポートが提供されます。</span><span class="sxs-lookup"><span data-stu-id="57fc6-123">The integration of LINQ in Visual Basic provides stronger typing, compile-time checking, and improved debugger support.</span></span>  
  
 <span data-ttu-id="57fc6-124">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] のもう 1 つの利点は、クエリの結果を <xref:System.Xml.Linq.XElement> および <xref:System.Xml.Linq.XAttribute> オブジェクト コンストラクターに対するパラメーターとして使用できるので、XML ツリーを作成するための強力な方法が利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="57fc6-124">Another advantage of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] is the ability to use query results as parameters to <xref:System.Xml.Linq.XElement> and <xref:System.Xml.Linq.XAttribute> object constructors enables a powerful approach to creating XML trees.</span></span> <span data-ttu-id="57fc6-125">*関数型構築*と呼ばれるこの方法では、開発者が XML ツリーの構造を簡単に変換できます。</span><span class="sxs-lookup"><span data-stu-id="57fc6-125">This approach, called *functional construction*, enables developers to easily transform XML trees from one shape to another.</span></span>  
  
 <span data-ttu-id="57fc6-126">たとえば、「[サンプル XML ファイル: 一般的な購買発注書 (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md)」で説明されているように、典型的な XML の購買発注書を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="57fc6-126">For example, you might have a typical XML purchase order as described in [Sample XML File: Typical Purchase Order (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md).</span></span> <span data-ttu-id="57fc6-127">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] を使用することで、次のクエリを実行して購買発注書のすべての品目要素の部品番号属性を取得できます。</span><span class="sxs-lookup"><span data-stu-id="57fc6-127">By using [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], you could run the following query to obtain the part number attribute value for every item element in the purchase order:</span></span>  
  
```vb  
Dim partNos = _  
    From item In purchaseOrder...<Item> _  
    Select item.@PartNumber  
```  
  
 <span data-ttu-id="57fc6-128">もう 1 つの例として、金額が $100 を超える品目を部品番号順に並べた一覧が必要であるとします。</span><span class="sxs-lookup"><span data-stu-id="57fc6-128">As another example, you might want a list, sorted by part number, of the items with a value greater than $100.</span></span> <span data-ttu-id="57fc6-129">この情報を取得するには、次のクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="57fc6-129">To obtain this information, you could run the following query:</span></span>  
  
```vb  
Dim partNos = _  
From item In purchaseOrder...<Item> _  
Where (item.<Quantity>.Value * _  
       item.<USPrice>.Value) > 100 _  
Order By item.<PartNumber>.Value _  
Select item  
```  
  
 <span data-ttu-id="57fc6-130">これらの LINQ 機能に加えて、[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] では XML プログラミングインターフェイスが強化されています。</span><span class="sxs-lookup"><span data-stu-id="57fc6-130">In addition to these LINQ capabilities, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] provides an improved XML programming interface.</span></span> <span data-ttu-id="57fc6-131">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] を使用すると、次のことを実行できます。</span><span class="sxs-lookup"><span data-stu-id="57fc6-131">Using [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], you can:</span></span>  
  
- <span data-ttu-id="57fc6-132">ファイルまたはストリームからの XML の読み込み</span><span class="sxs-lookup"><span data-stu-id="57fc6-132">Load XML from files or streams.</span></span>  
  
- <span data-ttu-id="57fc6-133">ファイルまたはストリームへの XML のシリアル化</span><span class="sxs-lookup"><span data-stu-id="57fc6-133">Serialize XML to files or streams.</span></span>  
  
- <span data-ttu-id="57fc6-134">関数型構築を使用した XML の新規作成</span><span class="sxs-lookup"><span data-stu-id="57fc6-134">Create XML from scratch by using functional construction.</span></span>  
  
- <span data-ttu-id="57fc6-135">XPath に類似した軸を使用した XML に対するクエリの実行</span><span class="sxs-lookup"><span data-stu-id="57fc6-135">Query XML using XPath-like axes.</span></span>  
  
- <span data-ttu-id="57fc6-136"><xref:System.Xml.Linq.XContainer.Add%2A>、<xref:System.Xml.Linq.XNode.Remove%2A>、<xref:System.Xml.Linq.XNode.ReplaceWith%2A>、<xref:System.Xml.Linq.XElement.SetValue%2A> などのメソッドを使用した、メモリ内の XML ツリーの操作</span><span class="sxs-lookup"><span data-stu-id="57fc6-136">Manipulate the in-memory XML tree by using methods such as <xref:System.Xml.Linq.XContainer.Add%2A>, <xref:System.Xml.Linq.XNode.Remove%2A>, <xref:System.Xml.Linq.XNode.ReplaceWith%2A>, and <xref:System.Xml.Linq.XElement.SetValue%2A>.</span></span>  
  
- <span data-ttu-id="57fc6-137">XSD を使用した XML ツリーの検証</span><span class="sxs-lookup"><span data-stu-id="57fc6-137">Validate XML trees using XSD.</span></span>  
  
- <span data-ttu-id="57fc6-138">上記の機能を組み合わせて使用した XML ツリーの構造の変換</span><span class="sxs-lookup"><span data-stu-id="57fc6-138">Use a combination of these features to transform XML trees from one shape into another.</span></span>  
  
## <a name="creating-xml-trees"></a><span data-ttu-id="57fc6-139">XML ツリーの作成</span><span class="sxs-lookup"><span data-stu-id="57fc6-139">Creating XML Trees</span></span>  
 <span data-ttu-id="57fc6-140">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] でのプログラミングで最も重要な利点の 1 つは、XML ツリーを簡単に作成できるという点です。</span><span class="sxs-lookup"><span data-stu-id="57fc6-140">IOne of the most significant advantages of programming with [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] is that it is easy to create XML trees.</span></span> <span data-ttu-id="57fc6-141">たとえば、小さな XML ツリーを作成するには、次のようにコードを記述します。</span><span class="sxs-lookup"><span data-stu-id="57fc6-141">For example, to create a small XML tree, you can write  code as follows:</span></span>  
  
```vb  
Dim contacts = _  
<Contacts>  
    <Contact>  
        <Name>Patrick Hines</Name>  
        <Phone Type="Home">206-555-0144</Phone>  
        <Phone Type="Work">425-555-0145</Phone>  
        <Address>  
            <Street1>123 Main St</Street1>  
            <City>Mercer Island</City>  
            <State>WA</State>  
            <Postal>68042</Postal>  
        </Address>  
    </Contact>  
</Contacts>  
```  
  
 <span data-ttu-id="57fc6-142">Visual Basic コンパイラは、XML リテラルを [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] メソッド呼び出しに変換します。</span><span class="sxs-lookup"><span data-stu-id="57fc6-142">The Visual Basic compiler translates XML literals into [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] method calls.</span></span>  
  
 <span data-ttu-id="57fc6-143">詳細については、「 [XML ツリーの作成 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="57fc6-143">For more information, see [Creating XML Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57fc6-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="57fc6-144">See also</span></span>

- <xref:System.Xml.Linq>
- [<span data-ttu-id="57fc6-145">はじめに (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="57fc6-145">Getting Started (LINQ to XML)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/getting-started-linq-to-xml.md)
- [<span data-ttu-id="57fc6-146">Visual Basic における LINQ to XML の概要</span><span class="sxs-lookup"><span data-stu-id="57fc6-146">Overview of LINQ to XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/overview-of-linq-to-xml.md)
- [<span data-ttu-id="57fc6-147">XML</span><span class="sxs-lookup"><span data-stu-id="57fc6-147">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
