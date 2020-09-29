---
title: LINQ の概要
ms.date: 07/20/2015
ms.assetid: c6339c12-9b2d-433e-961c-0d2b7f0091c2
ms.openlocfilehash: e99da74eb69511b92ddccfb42f8002adc7be83d1
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "91098282"
---
# <a name="introduction-to-linq-visual-basic"></a><span data-ttu-id="5ec2e-102">LINQ の概要 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5ec2e-102">Introduction to LINQ (Visual Basic)</span></span>

<span data-ttu-id="5ec2e-103">統合言語クエリ (LINQ) は、.NET Framework Version 3.5 で導入された、オブジェクトとデータの溝を埋める画期的な手法です。</span><span class="sxs-lookup"><span data-stu-id="5ec2e-103">Language-Integrated Query (LINQ) is an innovation introduced in the .NET Framework version 3.5 that bridges the gap between the world of objects and the world of data.</span></span>  
  
 <span data-ttu-id="5ec2e-104">これまでは、データに対するクエリは、コンパイル時の型チェックや IntelliSense のサポートがない単純な文字列として表現されてきました。</span><span class="sxs-lookup"><span data-stu-id="5ec2e-104">Traditionally, queries against data are expressed as simple strings without type checking at compile time or IntelliSense support.</span></span> <span data-ttu-id="5ec2e-105">さらに、SQL データベース、XML ドキュメント、さまざまな Web サービスなど、各種データ ソースの異なるクエリ言語を学習する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5ec2e-105">Furthermore, you have to learn a different query language for each type of data source: SQL databases, XML documents, various Web services, and so on.</span></span> <span data-ttu-id="5ec2e-106">LINQ により、"*クエリ*" は Visual Basic の高度な言語構成要素になります。</span><span class="sxs-lookup"><span data-stu-id="5ec2e-106">LINQ makes a *query* a first-class language construct in Visual Basic.</span></span> <span data-ttu-id="5ec2e-107">厳密に型指定されているオブジェクトのコレクションに対して、言語キーワードと使い慣れた演算子を用いてクエリを記述します。</span><span class="sxs-lookup"><span data-stu-id="5ec2e-107">You write queries against strongly typed collections of objects by using language keywords and familiar operators.</span></span>  
  
 <span data-ttu-id="5ec2e-108">Visual Basic を使って LINQ クエリを記述できます。対象は、<xref:System.Collections.IEnumerable> またはジェネリック <xref:System.Collections.Generic.IEnumerable%601> インターフェイスをサポートする SQL Server データベース、XML ドキュメント、ADO.NET データセット、その他のオブジェクトのコレクションです。</span><span class="sxs-lookup"><span data-stu-id="5ec2e-108">You can write LINQ queries in Visual Basic for SQL Server databases, XML documents, ADO.NET Datasets, and any collection of objects that supports <xref:System.Collections.IEnumerable> or the generic <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span> <span data-ttu-id="5ec2e-109">サード パーティからも、多くの Web サービスとその他のデータベース実装に対する LINQ のサポートが提供されます。</span><span class="sxs-lookup"><span data-stu-id="5ec2e-109">LINQ support is also provided by third parties for many Web services and other database implementations.</span></span>  
  
 <span data-ttu-id="5ec2e-110">新しいプロジェクトで LINQ クエリを使用できるほか、既存のプロジェクトで LINQ 以外のクエリを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="5ec2e-110">You can use LINQ queries in new projects, or alongside non-LINQ queries in existing projects.</span></span> <span data-ttu-id="5ec2e-111">唯一の要件は、プロジェクトが .NET Framework 3.5 以降をターゲットとしていることです。</span><span class="sxs-lookup"><span data-stu-id="5ec2e-111">The only requirement is that the project target .NET Framework 3.5 or later.</span></span>  
  
 <span data-ttu-id="5ec2e-112">次の Visual Studio の図は、SQL Server データベースに対して部分的に完了した LINQ クエリを示しています。このクエリは C# および Visual Basic の両方で記述されており、完全な型チェックと IntelliSense に対応しています。</span><span class="sxs-lookup"><span data-stu-id="5ec2e-112">The following illustration from Visual Studio shows a partially-completed LINQ query against a SQL Server database in both C# and Visual Basic with full type checking and IntelliSense support.</span></span>  
  
 ![Intellisense を使用する LINQ クエリを示す図。](./media/introduction-to-linq/linq-query-intellisense.png)  
  
## <a name="next-steps"></a><span data-ttu-id="5ec2e-114">次の手順</span><span class="sxs-lookup"><span data-stu-id="5ec2e-114">Next Steps</span></span>  

 <span data-ttu-id="5ec2e-115">LINQ の詳細については、最初に「[Visual Basic の LINQ の概要](getting-started-with-linq.md)」の概要に関するセクションで基本的な概念を理解し、次に関心のある LINQ テクノロジのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5ec2e-115">To learn more details about LINQ, start by becoming familiar with some basic concepts in the Getting Started section [Getting Started with LINQ in Visual Basic](getting-started-with-linq.md), and then read the documentation for the LINQ technology in which you are interested:</span></span>  
  
- <span data-ttu-id="5ec2e-116">SQL Server データベース:[LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)</span><span class="sxs-lookup"><span data-stu-id="5ec2e-116">SQL Server databases: [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)</span></span>  
  
- <span data-ttu-id="5ec2e-117">XML ドキュメント:[LINQ to XML (Visual Basic)](../../../../standard/linq/linq-xml-overview.md)</span><span class="sxs-lookup"><span data-stu-id="5ec2e-117">XML documents: [LINQ to XML (Visual Basic)](../../../../standard/linq/linq-xml-overview.md)</span></span>  
  
- <span data-ttu-id="5ec2e-118">ADO.NET データセット:[LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md)</span><span class="sxs-lookup"><span data-stu-id="5ec2e-118">ADO.NET Datasets: [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md)</span></span>  
  
- <span data-ttu-id="5ec2e-119">.NET のコレクション、ファイル、文字列など:[LINQ to Objects (Visual Basic)](linq-to-objects.md)</span><span class="sxs-lookup"><span data-stu-id="5ec2e-119">.NET collections, files, strings and so on: [LINQ to Objects (Visual Basic)](linq-to-objects.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ec2e-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="5ec2e-120">See also</span></span>

- [<span data-ttu-id="5ec2e-121">統合言語クエリ (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5ec2e-121">Language-Integrated Query (LINQ) (Visual Basic)</span></span>](index.md)
