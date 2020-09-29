---
title: LINQ to ADO.NET (ポータル ページ)
description: LINQ to ADO.NET では、LINQ プログラミング モデルを使用して ADO.NET 内の列挙可能なオブジェクトに対してクエリを実行できます。 3 つの ADO.NET LINQ テクノロジについて学習します。
ms.date: 07/20/2015
ms.assetid: 6bd269b4-3509-4688-b672-836008704182
ms.openlocfilehash: 6d8a6a7a90abe12dacec9a017f80c1ff1abd46f1
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91202553"
---
# <a name="linq-to-adonet-portal-page"></a><span data-ttu-id="799e6-104">LINQ to ADO.NET (ポータル ページ)</span><span class="sxs-lookup"><span data-stu-id="799e6-104">LINQ to ADO.NET (Portal Page)</span></span>

<span data-ttu-id="799e6-105">LINQ to ADO.NET では、統合言語クエリ (LINQ) プログラミング モデルを使用して ADO.NET 内の列挙可能なオブジェクトに対してクエリを実行できます。</span><span class="sxs-lookup"><span data-stu-id="799e6-105">LINQ to ADO.NET enables you to query over any enumerable object in ADO.NET by using the Language-Integrated Query (LINQ) programming model.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="799e6-106">LINQ to ADO.NET のドキュメントは、.NET Framework SDK の ADO.NET のセクションにあります。「[LINQ と ADO.NET](../../../../framework/data/adonet/linq-and-ado-net.md)」。</span><span class="sxs-lookup"><span data-stu-id="799e6-106">The LINQ to ADO.NET documentation is located in the ADO.NET section of the .NET Framework SDK: [LINQ and ADO.NET](../../../../framework/data/adonet/linq-and-ado-net.md).</span></span>  
  
 <span data-ttu-id="799e6-107">ADO.NET 統合言語クエリ (LINQ) には、3 つのテクノロジがあります。LINQ to DataSet、[!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)]、LINQ to Entities です。</span><span class="sxs-lookup"><span data-stu-id="799e6-107">There are three separate ADO.NET Language-Integrated Query (LINQ) technologies: LINQ to DataSet, [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)], and LINQ to Entities.</span></span> <span data-ttu-id="799e6-108">LINQ to DataSet では、<xref:System.Data.DataSet> に対する高度で最適化されたクエリの実行が提供されます。[!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] では、SQL Server データベース スキーマに対して直接クエリを実行できます。LINQ to Entities では、Entity Data Model のクエリを実行できます。</span><span class="sxs-lookup"><span data-stu-id="799e6-108">LINQ to DataSet provides richer, optimized querying over the <xref:System.Data.DataSet>, [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] enables you to directly query SQL Server database schemas, and LINQ to Entities allows you to query an Entity Data Model.</span></span>  
  
## <a name="linq-to-dataset"></a><span data-ttu-id="799e6-109">LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="799e6-109">LINQ to DataSet</span></span>  

 <span data-ttu-id="799e6-110"><xref:System.Data.DataSet> は、ADO.NET で最も幅広く使用されているコンポーネントの 1 つであり、ADO.NET の基礎である非接続型プログラミングの重要な要素です。</span><span class="sxs-lookup"><span data-stu-id="799e6-110">The <xref:System.Data.DataSet> is one of the most widely used components in ADO.NET, and is a key element of the disconnected programming model that ADO.NET is built on.</span></span> <span data-ttu-id="799e6-111">こうした突出した特長がある反面、<xref:System.Data.DataSet> のクエリ機能には制限もあります。</span><span class="sxs-lookup"><span data-stu-id="799e6-111">Despite this prominence, however, the <xref:System.Data.DataSet> has limited query capabilities.</span></span>  
  
 <span data-ttu-id="799e6-112">LINQ to DataSet では、他の多くのデータ ソースで使用できるのと同じクエリ機能を使用することで、豊富なクエリ機能を <xref:System.Data.DataSet> に組み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="799e6-112">LINQ to DataSet enables you to build richer query capabilities into <xref:System.Data.DataSet> by using the same query functionality that is available for many other data sources.</span></span>  
  
 <span data-ttu-id="799e6-113">詳細については、「[LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="799e6-113">For more information, see [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md).</span></span>  
  
## <a name="linq-to-sql"></a><span data-ttu-id="799e6-114">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="799e6-114">LINQ to SQL</span></span>  

 [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] <span data-ttu-id="799e6-115">には、リレーショナル データをオブジェクトとして管理するためのランタイム インフラストラクチャが用意されています。</span><span class="sxs-lookup"><span data-stu-id="799e6-115">provides a run-time infrastructure for managing relational data as objects.</span></span> <span data-ttu-id="799e6-116">[!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] では、リレーショナル データベースのデータ モデルが、開発者のプログラミング言語で表されるオブジェクト モデルに対応付けられています。</span><span class="sxs-lookup"><span data-stu-id="799e6-116">In [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)], the data model of a relational database is mapped to an object model expressed in the programming language of the developer.</span></span> <span data-ttu-id="799e6-117">アプリケーションを実行すると、[!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] は、オブジェクト モデルの統合言語クエリを SQL に変換し、それをデータベースに送信して実行します。</span><span class="sxs-lookup"><span data-stu-id="799e6-117">When you execute the application, [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] translates language-integrated queries in the object model into SQL and sends them to the database for execution.</span></span> <span data-ttu-id="799e6-118">データベースから結果が返されると、[!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] で元の操作できるオブジェクトに変換されます。</span><span class="sxs-lookup"><span data-stu-id="799e6-118">When the database returns the results, [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] translates them back into objects that you can manipulate.</span></span>  
  
 [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] <span data-ttu-id="799e6-119">には、データベースのストアド プロシージャ、ユーザー定義関数、オブジェクト モデルの継承のサポートが含まれています。</span><span class="sxs-lookup"><span data-stu-id="799e6-119">includes support for stored procedures and user-defined functions in the database, and for inheritance in the object model.</span></span>  
  
 <span data-ttu-id="799e6-120">詳細については、「[LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="799e6-120">For more information, see [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md).</span></span>  
  
## <a name="linq-to-entities"></a><span data-ttu-id="799e6-121">LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="799e6-121">LINQ to Entities</span></span>  

 <span data-ttu-id="799e6-122">Entity Data Model では、リレーショナル データが .NET 環境にオブジェクトとして公開されます。</span><span class="sxs-lookup"><span data-stu-id="799e6-122">Through the Entity Data Model, relational data is exposed as objects in the .NET environment.</span></span> <span data-ttu-id="799e6-123">これにより、LINQ の利用に最適なオブジェクト レイヤーが実現されます。開発者は、ビジネス ロジックの構築に使用する言語で、データベースを照会するクエリを作成できます。</span><span class="sxs-lookup"><span data-stu-id="799e6-123">This makes the object layer an ideal target for LINQ support, allowing developers to formulate queries against the database from the language used to build the business logic.</span></span> <span data-ttu-id="799e6-124">この機能は、LINQ to Entities と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="799e6-124">This capability is known as LINQ to Entities.</span></span> <span data-ttu-id="799e6-125">LINQ の詳細については、「[LINQ to Entities](../../../../framework/data/adonet/ef/language-reference/linq-to-entities.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="799e6-125">See [LINQ to Entities](../../../../framework/data/adonet/ef/language-reference/linq-to-entities.md) for more information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="799e6-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="799e6-126">See also</span></span>

- [<span data-ttu-id="799e6-127">LINQ と ADO.NET</span><span class="sxs-lookup"><span data-stu-id="799e6-127">LINQ and ADO.NET</span></span>](../../../../framework/data/adonet/linq-and-ado-net.md)
- [<span data-ttu-id="799e6-128">統合言語クエリ (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="799e6-128">Language-Integrated Query (LINQ) (C#)</span></span>](./index.md)
