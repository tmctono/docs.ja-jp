---
title: DataSet、DataTable、および DataView
ms.date: 03/30/2017
ms.assetid: 6d4c4b69-8919-4224-8a65-6cca1c61b48f
ms.openlocfilehash: 9c57f75dd94f3fbda74c13a5d5773825051fe416
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62034295"
---
# <a name="datasets-datatables-and-dataviews"></a><span data-ttu-id="47fe9-102">DataSet、DataTable、および DataView</span><span class="sxs-lookup"><span data-stu-id="47fe9-102">DataSets, DataTables, and DataViews</span></span>
<span data-ttu-id="47fe9-103">ADO.NET <xref:System.Data.DataSet> はメモリ常駐型のデータ表現であり、含まれているデータ ソースとは関係なく、一貫性のあるリレーショナル プログラミング モデルを提供します。</span><span class="sxs-lookup"><span data-stu-id="47fe9-103">The ADO.NET <xref:System.Data.DataSet> is a memory-resident representation of data that provides a consistent relational programming model regardless of the source of the data it contains.</span></span> <span data-ttu-id="47fe9-104"><xref:System.Data.DataSet> とは、テーブル間のリレーションシップだけでなく、包括するテーブル、整列するテーブル、およびデータを制約するテーブルを含むデータのセットを表します。</span><span class="sxs-lookup"><span data-stu-id="47fe9-104">A <xref:System.Data.DataSet> represents a complete set of data including the tables that contain, order, and constrain the data, as well as the relationships between the tables.</span></span>  
  
 <span data-ttu-id="47fe9-105"><xref:System.Data.DataSet> にはさまざまな使用方法があり、単独または組み合わせで使用できます。</span><span class="sxs-lookup"><span data-stu-id="47fe9-105">There are several ways of working with a <xref:System.Data.DataSet>, which can be applied independently or in combination.</span></span> <span data-ttu-id="47fe9-106">次の操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="47fe9-106">You can:</span></span>  
  
- <span data-ttu-id="47fe9-107">プログラムを使用して <xref:System.Data.DataTable> 内に <xref:System.Data.DataRelation>、<xref:System.Data.Constraint>、および <xref:System.Data.DataSet> を作成し、テーブルにデータを設定できます。</span><span class="sxs-lookup"><span data-stu-id="47fe9-107">Programmatically create a <xref:System.Data.DataTable>, <xref:System.Data.DataRelation>, and <xref:System.Data.Constraint> within a <xref:System.Data.DataSet> and populate the tables with data.</span></span>  
  
- <span data-ttu-id="47fe9-108"><xref:System.Data.DataSet> を使用して、既存のリレーショナル データ ソースから取得したデータのテーブルで `DataAdapter` を作成できます。</span><span class="sxs-lookup"><span data-stu-id="47fe9-108">Populate the <xref:System.Data.DataSet> with tables of data from an existing relational data source using a `DataAdapter`.</span></span>  
  
- <span data-ttu-id="47fe9-109">XML を使用して、<xref:System.Data.DataSet> の内容を読み込んだり、永続化したりできます。</span><span class="sxs-lookup"><span data-stu-id="47fe9-109">Load and persist the <xref:System.Data.DataSet> contents using XML.</span></span> <span data-ttu-id="47fe9-110">詳しくは、「[DataSet での XML の使用](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="47fe9-110">For more information, see [Using XML in a DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md).</span></span>  
  
 <span data-ttu-id="47fe9-111">厳密に型指定された <xref:System.Data.DataSet> も XML Web サービスを使用して転送できます。</span><span class="sxs-lookup"><span data-stu-id="47fe9-111">A strongly typed <xref:System.Data.DataSet> can also be transported using an XML Web service.</span></span> <span data-ttu-id="47fe9-112"><xref:System.Data.DataSet> は、XML Web サービスを使用してデータの転送が理想的に行えるように設計されています。</span><span class="sxs-lookup"><span data-stu-id="47fe9-112">The design of the <xref:System.Data.DataSet> makes it ideal for transporting data using XML Web services.</span></span> <span data-ttu-id="47fe9-113">XML Web サービスの概要については、「[XML Web サービスの概要](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w9fdtx28(v=vs.100))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="47fe9-113">For an overview of XML Web services, see [XML Web Services Overview](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w9fdtx28(v=vs.100)).</span></span> <span data-ttu-id="47fe9-114">XML Web サービスから <xref:System.Data.DataSet> を使用する例については、「[XML Web サービスからの DataSet の使用](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/consuming-a-dataset-from-an-xml-web-service.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="47fe9-114">For an example of consuming a <xref:System.Data.DataSet> from an XML Web service, see [Consuming a DataSet from an XML Web Service](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/consuming-a-dataset-from-an-xml-web-service.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="47fe9-115">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="47fe9-115">In This Section</span></span>  
 [<span data-ttu-id="47fe9-116">DataSet の作成</span><span class="sxs-lookup"><span data-stu-id="47fe9-116">Creating a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-a-dataset.md)  
 <span data-ttu-id="47fe9-117"><xref:System.Data.DataSet> のインスタンス作成に使用する構文について説明します。</span><span class="sxs-lookup"><span data-stu-id="47fe9-117">Describes the syntax for creating an instance of a <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="47fe9-118">DataSet への DataTable の追加</span><span class="sxs-lookup"><span data-stu-id="47fe9-118">Adding a DataTable to a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-a-datatable-to-a-dataset.md)  
 <span data-ttu-id="47fe9-119">テーブルと列の作成方法および <xref:System.Data.DataSet> への追加方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="47fe9-119">Describes how to create and add tables and columns to a <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="47fe9-120">DataRelation の追加</span><span class="sxs-lookup"><span data-stu-id="47fe9-120">Adding DataRelations</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-datarelations.md)  
 <span data-ttu-id="47fe9-121"><xref:System.Data.DataSet> のテーブル間のリレーションを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="47fe9-121">Describes how to create relations between tables in a <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="47fe9-122">DataRelation の移動</span><span class="sxs-lookup"><span data-stu-id="47fe9-122">Navigating DataRelations</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/navigating-datarelations.md)  
 <span data-ttu-id="47fe9-123"><xref:System.Data.DataSet> のテーブル間のリレーションを使用して、親子のリレーションシップに基づく子または親の行を返す方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="47fe9-123">Describes how to use the relations between tables in a <xref:System.Data.DataSet> to return the child or parent rows of a parent-child relationship.</span></span>  
  
 [<span data-ttu-id="47fe9-124">DataSet の内容のマージ</span><span class="sxs-lookup"><span data-stu-id="47fe9-124">Merging DataSet Contents</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/merging-dataset-contents.md)  
 <span data-ttu-id="47fe9-125"><xref:System.Data.DataSet>、<xref:System.Data.DataTable>、<xref:System.Data.DataRow> の各配列の内容を別の <xref:System.Data.DataSet> にマージする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="47fe9-125">Describes how to merge the contents of one <xref:System.Data.DataSet>, <xref:System.Data.DataTable>, or <xref:System.Data.DataRow> array into another <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="47fe9-126">DataSet の内容のコピー</span><span class="sxs-lookup"><span data-stu-id="47fe9-126">Copying DataSet Contents</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/copying-dataset-contents.md)  
 <span data-ttu-id="47fe9-127">指定されたデータだけでなく、スキーマを持つことができる <xref:System.Data.DataSet> のコピーを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="47fe9-127">Describes how to create a copy of a <xref:System.Data.DataSet> that can contain schema as well as specified data.</span></span>  
  
 [<span data-ttu-id="47fe9-128">DataSet のイベント処理</span><span class="sxs-lookup"><span data-stu-id="47fe9-128">Handling DataSet Events</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-dataset-events.md)  
 <span data-ttu-id="47fe9-129"><xref:System.Data.DataSet> のイベントおよびその使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="47fe9-129">Describes the events of a <xref:System.Data.DataSet> and how to use them.</span></span>  
  
 [<span data-ttu-id="47fe9-130">型指定されたデータセット</span><span class="sxs-lookup"><span data-stu-id="47fe9-130">Typed DataSets</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md)  
 <span data-ttu-id="47fe9-131">型指定された <xref:System.Data.DataSet> の概要と、その作成および使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="47fe9-131">Discusses what a typed <xref:System.Data.DataSet> is and how to create and use it.</span></span>  
  
 [<span data-ttu-id="47fe9-132">DataTables</span><span class="sxs-lookup"><span data-stu-id="47fe9-132">DataTables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 <span data-ttu-id="47fe9-133"><xref:System.Data.DataTable> の作成方法、スキーマの定義方法、およびデータの操作方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="47fe9-133">Describes how to create a <xref:System.Data.DataTable>, define the schema, and manipulate data.</span></span>  
  
 [<span data-ttu-id="47fe9-134">DataTableReaders</span><span class="sxs-lookup"><span data-stu-id="47fe9-134">DataTableReaders</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatablereaders.md)  
 <span data-ttu-id="47fe9-135"><xref:System.Data.DataTableReader> の作成方法および使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="47fe9-135">Describes how to create and use a <xref:System.Data.DataTableReader>.</span></span>  
  
 [<span data-ttu-id="47fe9-136">DataViews</span><span class="sxs-lookup"><span data-stu-id="47fe9-136">DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)  
 <span data-ttu-id="47fe9-137">`DataViews` の作成方法および操作方法、および <xref:System.Data.DataView> イベントの操作方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="47fe9-137">Describes how to create and work with `DataViews` and work with <xref:System.Data.DataView> events.</span></span>  
  
 [<span data-ttu-id="47fe9-138">DataSet での XML の使用</span><span class="sxs-lookup"><span data-stu-id="47fe9-138">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 <span data-ttu-id="47fe9-139"><xref:System.Data.DataSet> がデータ ソースとして XML と対話する方法を、<xref:System.Data.DataSet> の内容を XML データとして読み込んで永続化する方法と共に説明します。</span><span class="sxs-lookup"><span data-stu-id="47fe9-139">Describes how the <xref:System.Data.DataSet> interacts with XML as a data source, including loading and persisting the contents of a <xref:System.Data.DataSet> as XML data.</span></span>  
  
 [<span data-ttu-id="47fe9-140">XML Web サービスからの DataSet の使用</span><span class="sxs-lookup"><span data-stu-id="47fe9-140">Consuming a DataSet from an XML Web Service</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/consuming-a-dataset-from-an-xml-web-service.md)  
 <span data-ttu-id="47fe9-141"><xref:System.Data.DataSet> を使用してデータを転送する XML Web サービスを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="47fe9-141">Describes how to create an XML Web service that uses a <xref:System.Data.DataSet> to transport data.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="47fe9-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="47fe9-142">Related Sections</span></span>  
 [<span data-ttu-id="47fe9-143">ADO.NET の新機能</span><span class="sxs-lookup"><span data-stu-id="47fe9-143">What's New in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/whats-new.md)  
 <span data-ttu-id="47fe9-144">ADO.NET の新機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="47fe9-144">Introduces features that are new in ADO.NET.</span></span>  
  
 [<span data-ttu-id="47fe9-145">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="47fe9-145">ADO.NET Overview</span></span>](../../../../../docs/framework/data/adonet/ado-net-overview.md)  
 <span data-ttu-id="47fe9-146">ADO.NET のデザインとコンポーネントを紹介します。</span><span class="sxs-lookup"><span data-stu-id="47fe9-146">Provides an introduction to the design and components of ADO.NET.</span></span>  
  
 [<span data-ttu-id="47fe9-147">DataAdapter からの DataSet の読み込み</span><span class="sxs-lookup"><span data-stu-id="47fe9-147">Populating a DataSet from a DataAdapter</span></span>](../../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md)  
 <span data-ttu-id="47fe9-148">**DataSet** にデータ ソースのデータを読み込む方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="47fe9-148">Describes how to load a **DataSet** with data from a data source.</span></span>  
  
 [<span data-ttu-id="47fe9-149">DataAdapter によるデータ ソースの更新</span><span class="sxs-lookup"><span data-stu-id="47fe9-149">Updating Data Sources with DataAdapters</span></span>](../../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md)  
 <span data-ttu-id="47fe9-150">**DataSet** のデータに加えた変更をデータ ソースに反映する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="47fe9-150">Describes how to resolve changes to the data in a **DataSet** back to the data source.</span></span>  
  
 [<span data-ttu-id="47fe9-151">DataSet への既存の制約の追加</span><span class="sxs-lookup"><span data-stu-id="47fe9-151">Adding Existing Constraints to a DataSet</span></span>](../../../../../docs/framework/data/adonet/adding-existing-constraints-to-a-dataset.md)  
 <span data-ttu-id="47fe9-152">**DataSet** にデータ ソースの主キー情報を設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="47fe9-152">Describes how to populate a **DataSet** with primary key information from a data source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47fe9-153">関連項目</span><span class="sxs-lookup"><span data-stu-id="47fe9-153">See also</span></span>

- [<span data-ttu-id="47fe9-154">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="47fe9-154">ADO.NET</span></span>](../../../../../docs/framework/data/adonet/index.md)
- [<span data-ttu-id="47fe9-155">ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター</span><span class="sxs-lookup"><span data-stu-id="47fe9-155">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
