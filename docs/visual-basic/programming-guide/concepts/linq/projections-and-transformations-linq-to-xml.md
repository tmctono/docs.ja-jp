---
title: 射影と変換 (LINQ to XML)
ms.date: 07/20/2015
ms.assetid: 297de224-b625-44cf-8c00-186b6189aa0e
ms.openlocfilehash: 39a5d972cfedfa2fec69f957f08875f030d51d55
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84396351"
---
# <a name="projections-and-transformations-linq-to-xml-visual-basic"></a><span data-ttu-id="fc097-102">プロジェクションと変換 (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fc097-102">Projections and Transformations (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="fc097-103">ここでは、[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] のプロジェクションと変換の例について説明します。</span><span class="sxs-lookup"><span data-stu-id="fc097-103">This section provides examples of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] projections and transformations.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fc097-104">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="fc097-104">In This Section</span></span>  
  
|<span data-ttu-id="fc097-105">トピック</span><span class="sxs-lookup"><span data-stu-id="fc097-105">Topic</span></span>|<span data-ttu-id="fc097-106">説明</span><span class="sxs-lookup"><span data-stu-id="fc097-106">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="fc097-107">方法: LINQ to XML を使用してディクショナリを操作する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fc097-107">How to: Work with Dictionaries Using LINQ to XML (Visual Basic)</span></span>](how-to-work-with-dictionaries-using-linq-to-xml.md)|<span data-ttu-id="fc097-108">ディクショナリを XML に変換する方法、および XML をディクショナリに変換する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fc097-108">Shows how to transform dictionaries to XML, and how to transform XML into dictionaries.</span></span>|  
|[<span data-ttu-id="fc097-109">方法: XML ツリーの構造を変換する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fc097-109">How to: Transform the Shape of an XML Tree (Visual Basic)</span></span>](how-to-transform-the-shape-of-an-xml-tree.md)|<span data-ttu-id="fc097-110">XML ドキュメントの構造を変換する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fc097-110">Shows how to transform the shape of an XML document.</span></span>|  
|[<span data-ttu-id="fc097-111">方法: プロジェクションの型を制御する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fc097-111">How to: Control the Type of a Projection (Visual Basic)</span></span>](how-to-control-the-type-of-a-projection.md)|<span data-ttu-id="fc097-112">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] クエリの型を制御する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fc097-112">Shows how to control the type of a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] query.</span></span>|  
|[<span data-ttu-id="fc097-113">方法: 新しい型を射影する (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fc097-113">How to: Project a New Type (LINQ to XML) (Visual Basic)</span></span>](how-to-project-a-new-type-linq-to-xml.md)|<span data-ttu-id="fc097-114">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] クエリからユーザー定義型のコレクションを射影する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fc097-114">Shows how to project a collection of a user-defined type from a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] query.</span></span>|  
|[<span data-ttu-id="fc097-115">方法: オブジェクト グラフを射影する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fc097-115">How to: Project an Object Graph (Visual Basic)</span></span>](how-to-project-an-object-graph.md)|<span data-ttu-id="fc097-116">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] クエリから複雑なオブジェクト グラフを射影する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fc097-116">Shows how to project a more complex object graph from a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] query.</span></span>|  
|[<span data-ttu-id="fc097-117">方法: 匿名型を射影する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fc097-117">How to: Project an Anonymous Type (Visual Basic)</span></span>](how-to-project-an-anonymous-type.md)|<span data-ttu-id="fc097-118">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] クエリから匿名オブジェクトのコレクションを射影する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fc097-118">Shows how to project a collection of anonymous objects from a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] query.</span></span>|  
|[<span data-ttu-id="fc097-119">方法: XML からテキスト ファイルを生成する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fc097-119">How to: Generate Text Files from XML (Visual Basic)</span></span>](how-to-generate-text-files-from-xml.md)|<span data-ttu-id="fc097-120">XML ファイルを XML 以外のテキスト ファイルに変換する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fc097-120">Shows how to transform an XML file to a non-XML text file.</span></span>|  
|[<span data-ttu-id="fc097-121">方法: CSV ファイルから XML を生成する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fc097-121">How to: Generate XML from CSV Files (Visual Basic)</span></span>](how-to-generate-xml-from-csv-files.md)|<span data-ttu-id="fc097-122">LINQ を使用して CSV ファイルを解析し、そのファイルから XML を生成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fc097-122">Shows how to use LINQ to parse a CSV file and generate XML from it.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fc097-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="fc097-123">See also</span></span>

- [<span data-ttu-id="fc097-124">XML ツリーのクエリ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fc097-124">Querying XML Trees (Visual Basic)</span></span>](querying-xml-trees.md)
