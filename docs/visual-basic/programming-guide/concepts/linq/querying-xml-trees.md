---
title: XML ツリーのクエリ
ms.date: 07/20/2015
ms.assetid: 2e35c1ab-08c8-4378-9ca8-8ff344756eda
ms.openlocfilehash: 643b19a0cfcd2a81c6f685de65979f83ca32d918
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/03/2020
ms.locfileid: "75636901"
---
# <a name="querying-xml-trees-visual-basic"></a><span data-ttu-id="4b9bf-102">XML ツリーのクエリ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4b9bf-102">Querying XML Trees (Visual Basic)</span></span>
<span data-ttu-id="4b9bf-103">ここでは、[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] クエリの例について説明します。</span><span class="sxs-lookup"><span data-stu-id="4b9bf-103">This section provides examples of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] queries.</span></span>  
  
 <span data-ttu-id="4b9bf-104">LINQ クエリの記述の詳細については、「 [Visual Basic での linq のはじめに](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4b9bf-104">For more information about writing LINQ queries, see [Getting Started with LINQ in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md).</span></span>  
  
 <span data-ttu-id="4b9bf-105">XML ツリーをインスタンス化してからクエリを記述することが、ツリーからデータを抽出する最も効率的な方法です。</span><span class="sxs-lookup"><span data-stu-id="4b9bf-105">After you have instantiated an XML tree, writing queries is the most effective way to extract data from the tree.</span></span> <span data-ttu-id="4b9bf-106">また、関数型構築と組み合わせてクエリを実行すると、元のドキュメントとは異なる形式の新しい XML ドキュメントを生成できます。</span><span class="sxs-lookup"><span data-stu-id="4b9bf-106">Also, querying combined with functional construction enables you to generate a new XML document that has a different shape from the original document.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4b9bf-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="4b9bf-107">In This Section</span></span>  
  
|<span data-ttu-id="4b9bf-108">トピック</span><span class="sxs-lookup"><span data-stu-id="4b9bf-108">Topic</span></span>|<span data-ttu-id="4b9bf-109">説明</span><span class="sxs-lookup"><span data-stu-id="4b9bf-109">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="4b9bf-110">基本的なクエリ (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4b9bf-110">Basic Queries (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)|<span data-ttu-id="4b9bf-111">XML ツリーのクエリの一般的な例について説明します。</span><span class="sxs-lookup"><span data-stu-id="4b9bf-111">Provides common examples of querying XML trees.</span></span>|  
|[<span data-ttu-id="4b9bf-112">プロジェクションと変換 (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4b9bf-112">Projections and Transformations (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/projections-and-transformations-linq-to-xml.md)|<span data-ttu-id="4b9bf-113">XML ツリーからの射影と XML ツリーの変換の一般的な例について説明します。</span><span class="sxs-lookup"><span data-stu-id="4b9bf-113">Provides common examples of projecting from and transforming XML trees.</span></span>|  
|[<span data-ttu-id="4b9bf-114">高度なクエリ手法 (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4b9bf-114">Advanced Query Techniques (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/advanced-query-techniques-linq-to-xml.md)|<span data-ttu-id="4b9bf-115">より高度なシナリオで役立つクエリ手法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4b9bf-115">Provides query techniques that are useful in more advanced scenarios.</span></span>|  
|[<span data-ttu-id="4b9bf-116">XPath ユーザーの LINQ to XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4b9bf-116">LINQ to XML for XPath Users (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)|<span data-ttu-id="4b9bf-117">多くの XPath 式と対応する [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] の式について説明します。</span><span class="sxs-lookup"><span data-stu-id="4b9bf-117">Presents a number of XPath expressions and their [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] equivalents.</span></span>|  
|[<span data-ttu-id="4b9bf-118">XML の純粋関数型変換 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4b9bf-118">Pure Functional Transformations of XML (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/pure-functional-transformations-of-xml.md)|<span data-ttu-id="4b9bf-119">関数型のプログラミング形式でクエリを記述する簡単なチュートリアルについて説明します。</span><span class="sxs-lookup"><span data-stu-id="4b9bf-119">Presents a small tutorial on writing queries in the style of functional programming.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4b9bf-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="4b9bf-120">See also</span></span>

- [<span data-ttu-id="4b9bf-121">プログラミングガイド (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4b9bf-121">Programming Guide (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/programming-guide-linq-to-xml.md)
- [<span data-ttu-id="4b9bf-122">Visual Basic の LINQ の概要</span><span class="sxs-lookup"><span data-stu-id="4b9bf-122">Getting Started with LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)
