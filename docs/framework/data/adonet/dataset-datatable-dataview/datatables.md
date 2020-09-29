---
title: DataTables
description: ADO.NET DataTable について説明します。これは、それが存在する .NET ベースのアプリケーションに対してローカルな、インメモリ リレーショナル データの 1 つのテーブルを表します。
ms.date: 03/30/2017
ms.assetid: 52ff0e32-3e5a-41de-9a3b-7b04ea52b83e
ms.openlocfilehash: d501096b4abe94653acdc5249c120abff94534d1
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91202306"
---
# <a name="datatables"></a><span data-ttu-id="19068-103">DataTables</span><span class="sxs-lookup"><span data-stu-id="19068-103">DataTables</span></span>

<span data-ttu-id="19068-104"><xref:System.Data.DataSet> は、テーブル、リレーションシップ、および制約のコレクションで構成されます。</span><span class="sxs-lookup"><span data-stu-id="19068-104">A <xref:System.Data.DataSet> is made up of a collection of tables, relationships, and constraints.</span></span> <span data-ttu-id="19068-105">ADO.NET では、<xref:System.Data.DataTable> は **DataSet** 内のテーブルを表すために使用されます。</span><span class="sxs-lookup"><span data-stu-id="19068-105">In ADO.NET, <xref:System.Data.DataTable> objects are used to represent the tables in a **DataSet**.</span></span> <span data-ttu-id="19068-106">**DataTable** は、1 つのメモリ内のリレーショナル データ テーブルを表します。このテーブルのデータは、そのデータが存在する .NET ベース アプリケーションのローカル データですが、**DataAdapter** を使用して Microsoft SQL Server などのデータ ソースから読み込むこともできます。詳細については、「[DataAdapter からの DataSet の読み込み](../populating-a-dataset-from-a-dataadapter.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="19068-106">A **DataTable** represents one table of in-memory relational data; the data is local to the .NET-based application in which it resides, but can be populated from a data source such as Microsoft SQL Server using a **DataAdapter** For more information, see [Populating a DataSet from a DataAdapter](../populating-a-dataset-from-a-dataadapter.md).</span></span>  
  
 <span data-ttu-id="19068-107">**DataTable** クラスは、.NET Framework クラス ライブラリ内の **System.Data** 名前空間のメンバーです。</span><span class="sxs-lookup"><span data-stu-id="19068-107">The **DataTable** class is a member of the **System.Data** namespace within the .NET Framework class library.</span></span> <span data-ttu-id="19068-108">**DataTable** は、単独でも **DataSet** のメンバーとしても作成および使用できます。また、**DataTable** オブジェクトは、<xref:System.Data.DataView> などの他の .NET Framework オブジェクトからも使用できます。</span><span class="sxs-lookup"><span data-stu-id="19068-108">You can create and use a **DataTable** independently or as a member of a **DataSet**, and **DataTable** objects can also be used in conjunction with other .NET Framework objects, including the <xref:System.Data.DataView>.</span></span> <span data-ttu-id="19068-109">**DataSet** 内のテーブルのコレクションには、**DataSet** オブジェクトの **Tables** プロパティを使用してアクセスします。</span><span class="sxs-lookup"><span data-stu-id="19068-109">You access the collection of tables in a **DataSet** through the **Tables** property of the **DataSet** object.</span></span>  
  
 <span data-ttu-id="19068-110">テーブルのスキーマ (構造) は、列と制約で表されます。</span><span class="sxs-lookup"><span data-stu-id="19068-110">The schema, or structure of a table is represented by columns and constraints.</span></span> <span data-ttu-id="19068-111">**DataTable** のスキーマは、<xref:System.Data.DataColumn> オブジェクト共に <xref:System.Data.ForeignKeyConstraint> および <xref:System.Data.UniqueConstraint> オブジェクトを使用して定義します。</span><span class="sxs-lookup"><span data-stu-id="19068-111">You define the schema of a **DataTable** using <xref:System.Data.DataColumn> objects as well as <xref:System.Data.ForeignKeyConstraint> and <xref:System.Data.UniqueConstraint> objects.</span></span> <span data-ttu-id="19068-112">テーブルの列は、データ ソースの列に割り当てたり、式で算出された値を格納したり、格納されている値を自動的にインクリメントしたり、主キー値を格納したりできます。</span><span class="sxs-lookup"><span data-stu-id="19068-112">The columns in a table can map to columns in a data source, contain calculated values from expressions, automatically increment their values, or contain primary key values.</span></span>  
  
 <span data-ttu-id="19068-113">**DataTable** には、スキーマだけでなく、データを格納して順序付けるための行も必要です。</span><span class="sxs-lookup"><span data-stu-id="19068-113">In addition to a schema, a **DataTable** must also have rows to contain and order data.</span></span> <span data-ttu-id="19068-114"><xref:System.Data.DataRow> クラスは、テーブルに格納される実際のデータを表します。</span><span class="sxs-lookup"><span data-stu-id="19068-114">The <xref:System.Data.DataRow> class represents the actual data contained in a table.</span></span> <span data-ttu-id="19068-115">**DataRow** およびそのプロパティとメソッドを使用して、テーブル内のデータを取得、評価、および操作できます。</span><span class="sxs-lookup"><span data-stu-id="19068-115">You use the **DataRow** and its properties and methods to retrieve, evaluate, and manipulate the data in a table.</span></span> <span data-ttu-id="19068-116">行内のデータがアクセスされて変更されると、**DataRow** オブジェクトには、現在の状態と元の状態が維持されます。</span><span class="sxs-lookup"><span data-stu-id="19068-116">As you access and change the data within a row, the **DataRow** object maintains both its current and original state.</span></span>  
  
 <span data-ttu-id="19068-117">テーブル間で 1 つ以上の列を関連付け、テーブル間の親子のリレーションシップを作成できます。</span><span class="sxs-lookup"><span data-stu-id="19068-117">You can create parent-child relationships between tables using one or more related columns in the tables.</span></span> <span data-ttu-id="19068-118">**DataTable** オブジェクト間のリレーションシップを作成するには、<xref:System.Data.DataRelation> を使用します。</span><span class="sxs-lookup"><span data-stu-id="19068-118">You create a relationship between **DataTable** objects using a <xref:System.Data.DataRelation>.</span></span> <span data-ttu-id="19068-119">**DataRelation** オブジェクトを使用すると、特定の行に関連付けられた子の行または親の行を返すことができます。</span><span class="sxs-lookup"><span data-stu-id="19068-119">**DataRelation** objects can then be used to return the related child or parent rows of a particular row.</span></span> <span data-ttu-id="19068-120">詳しくは、「[DataRelation の追加](adding-datarelations.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="19068-120">For more information, see [Adding DataRelations](adding-datarelations.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="19068-121">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="19068-121">In This Section</span></span>  

 [<span data-ttu-id="19068-122">DataTable の作成</span><span class="sxs-lookup"><span data-stu-id="19068-122">Creating a DataTable</span></span>](creating-a-datatable.md)  
 <span data-ttu-id="19068-123">**DataTable** を作成し、それを **DataSet** に追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="19068-123">Explains how to create a **DataTable** and add it to a **DataSet**.</span></span>  
  
 [<span data-ttu-id="19068-124">DataTable スキーマの定義</span><span class="sxs-lookup"><span data-stu-id="19068-124">DataTable Schema Definition</span></span>](datatable-schema-definition.md)  
 <span data-ttu-id="19068-125">**DataColumn** オブジェクトと制約の作成および使用について説明します。</span><span class="sxs-lookup"><span data-stu-id="19068-125">Provides information about creating and using **DataColumn** objects and constraints.</span></span>  
  
 [<span data-ttu-id="19068-126">DataTable 内のデータの操作</span><span class="sxs-lookup"><span data-stu-id="19068-126">Manipulating Data in a DataTable</span></span>](manipulating-data-in-a-datatable.md)  
 <span data-ttu-id="19068-127">テーブル内のデータを追加、変更、および削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="19068-127">Explains how to add, modify, and delete data in a table.</span></span> <span data-ttu-id="19068-128">**DataTable** イベントを使用してテーブル内のデータが変更されたかどうかを確認する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="19068-128">Explains how to use **DataTable** events to examine changes to data in the table.</span></span>  
  
 [<span data-ttu-id="19068-129">DataTable イベントの処理</span><span class="sxs-lookup"><span data-stu-id="19068-129">Handling DataTable Events</span></span>](handling-datatable-events.md)  
 <span data-ttu-id="19068-130">列値が変更された場合や行が追加または削除された場合のイベントなど、**DataTable** で使用できるイベントについて説明します。</span><span class="sxs-lookup"><span data-stu-id="19068-130">Provides information about the events available for use with a **DataTable**, including events when column values are modified and rows are added or deleted.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="19068-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="19068-131">Related Sections</span></span>  

 [<span data-ttu-id="19068-132">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="19068-132">ADO.NET</span></span>](../index.md)  
 <span data-ttu-id="19068-133">ADO.NET のアーキテクチャとコンポーネントについて説明し、ADO.NET を使用して既存のデータ ソースにアクセスしたり、アプリケーション データを管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="19068-133">Describes the ADO.NET architecture and components, and how to use them to access existing data sources and manage application data.</span></span>  
  
 [<span data-ttu-id="19068-134">DataSet、DataTable、および DataView</span><span class="sxs-lookup"><span data-stu-id="19068-134">DataSets, DataTables, and DataViews</span></span>](index.md)  
 <span data-ttu-id="19068-135">テーブル間のリレーションシップを作成する方法も含め、ADO.NET の **DataSet** について説明します。</span><span class="sxs-lookup"><span data-stu-id="19068-135">Provides information about the ADO.NET **DataSet** including how to create relationships between tables.</span></span>  
  
 <xref:System.Data.Constraint>  
 <span data-ttu-id="19068-136">**Constraint** オブジェクトの参照情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="19068-136">Provides reference information about the **Constraint** object.</span></span>  
  
 <xref:System.Data.DataColumn>  
 <span data-ttu-id="19068-137">**DataColumn** オブジェクトの参照情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="19068-137">Provides reference information about the **DataColumn** object.</span></span>  
  
 <xref:System.Data.DataSet>  
 <span data-ttu-id="19068-138">**DataSet** オブジェクトの参照情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="19068-138">Provides reference information about the **DataSet** object.</span></span>  
  
 <xref:System.Data.DataTable>  
 <span data-ttu-id="19068-139">**DataTable** オブジェクトの参照情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="19068-139">Provides reference information about the **DataTable** object.</span></span>  
  
 [<span data-ttu-id="19068-140">クラス ライブラリの概要</span><span class="sxs-lookup"><span data-stu-id="19068-140">Class Library Overview</span></span>](../../../../standard/class-library-overview.md)  
 <span data-ttu-id="19068-141">**System** 名前空間やその下位レベルの名前空間 **System.Data** が含まれる .NET Framework クラス ライブラリの概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="19068-141">Provides an overview of the .NET Framework class library, including the **System** namespace as well as its second-level namespace, **System.Data**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19068-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="19068-142">See also</span></span>

- [<span data-ttu-id="19068-143">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="19068-143">ADO.NET Overview</span></span>](../ado-net-overview.md)
