---
title: DataSet へのデータの読み込み
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a53e5dc1-9669-49d4-828d-efa633237066
ms.openlocfilehash: cb5578d790e5d3f54f75f964bb3288d861c9d7c3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61878541"
---
# <a name="loading-data-into-a-dataset"></a><span data-ttu-id="f881c-102">DataSet へのデータの読み込み</span><span class="sxs-lookup"><span data-stu-id="f881c-102">Loading Data Into a DataSet</span></span>
<span data-ttu-id="f881c-103"><xref:System.Data.DataSet> で [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] オブジェクトに対するクエリを実行するには、まずデータセットにデータを読み込んでおく必要があります。</span><span class="sxs-lookup"><span data-stu-id="f881c-103">A <xref:System.Data.DataSet> object must first be populated before you can query over it with [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].</span></span> <span data-ttu-id="f881c-104"><xref:System.Data.DataSet> には、複数の方法でデータを読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="f881c-104">There are several different ways to populate the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="f881c-105">たとえば、使用することができます[!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)]データベース クエリを実行しに結果を読み込み、<xref:System.Data.DataSet>します。</span><span class="sxs-lookup"><span data-stu-id="f881c-105">For example, you can use [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] to query the database and load the results into the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="f881c-106">詳細については、「[LINQ to SQL](../../../../docs/framework/data/adonet/sql/linq/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f881c-106">For more information, see [LINQ to SQL](../../../../docs/framework/data/adonet/sql/linq/index.md).</span></span>  
  
 <span data-ttu-id="f881c-107">データを <xref:System.Data.DataSet> に読み込む一般的な方法としては、他にも <xref:System.Data.Common.DataAdapter> クラスを使用してデータベースからデータを取得する方法もあります。</span><span class="sxs-lookup"><span data-stu-id="f881c-107">Another common way to load data into a <xref:System.Data.DataSet> is to use the <xref:System.Data.Common.DataAdapter> class to retrieve data from the database.</span></span> <span data-ttu-id="f881c-108">この例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="f881c-108">This is illustrated in the following example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f881c-109">例</span><span class="sxs-lookup"><span data-stu-id="f881c-109">Example</span></span>  
 <span data-ttu-id="f881c-110">この例では、<xref:System.Data.Common.DataAdapter> を使用して、2002 年度の売上情報を照会するクエリを AdventureWorks データベースに対して実行し、その結果を <xref:System.Data.DataSet> に読み込んでいます。</span><span class="sxs-lookup"><span data-stu-id="f881c-110">This example uses a <xref:System.Data.Common.DataAdapter> to query the AdventureWorks database for sales information from the year 2002, and loads the results into a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="f881c-111"><xref:System.Data.DataSet> への読み込みが完了した後、[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] を使用して、そのデータセットに対するクエリを作成できます。</span><span class="sxs-lookup"><span data-stu-id="f881c-111">After the <xref:System.Data.DataSet> has been populated, you can write queries against it by using [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].</span></span> <span data-ttu-id="f881c-112">`FillDataSet`でクエリの例でこの例ではメソッドが使用される[LINQ to DataSet の例](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)します。</span><span class="sxs-lookup"><span data-stu-id="f881c-112">The `FillDataSet` method in this example is used in the example queries in [LINQ to DataSet Examples](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md).</span></span> <span data-ttu-id="f881c-113">詳細については、次を参照してください。[データセットのクエリを実行する](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md)します。</span><span class="sxs-lookup"><span data-stu-id="f881c-113">For more information, see [Querying DataSets](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md).</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#FillDataSet](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#filldataset)]
 [!code-vb[DP LINQ to DataSet Examples#FillDataSet](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#filldataset)]  
  
## <a name="see-also"></a><span data-ttu-id="f881c-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="f881c-114">See also</span></span>

- [<span data-ttu-id="f881c-115">LINQ to DataSet の概要</span><span class="sxs-lookup"><span data-stu-id="f881c-115">LINQ to DataSet Overview</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-overview.md)
- [<span data-ttu-id="f881c-116">DataSet のクエリ</span><span class="sxs-lookup"><span data-stu-id="f881c-116">Querying DataSets</span></span>](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md)
- [<span data-ttu-id="f881c-117">LINQ to DataSet の例</span><span class="sxs-lookup"><span data-stu-id="f881c-117">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)
