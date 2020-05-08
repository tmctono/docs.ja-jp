---
title: DataSet へのデータの読み込み
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a53e5dc1-9669-49d4-828d-efa633237066
ms.openlocfilehash: 53f0f5a589a0033c9612f0465dff090ab04e3fc4
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70794960"
---
# <a name="loading-data-into-a-dataset"></a><span data-ttu-id="b91c9-102">DataSet へのデータの読み込み</span><span class="sxs-lookup"><span data-stu-id="b91c9-102">Loading Data Into a DataSet</span></span>
<span data-ttu-id="b91c9-103">LINQ to DataSet で <xref:System.Data.DataSet> オブジェクトに対するクエリを実行するには、まずデータセットにデータを読み込んでおく必要があります。</span><span class="sxs-lookup"><span data-stu-id="b91c9-103">A <xref:System.Data.DataSet> object must first be populated before you can query over it with LINQ to DataSet.</span></span> <span data-ttu-id="b91c9-104"><xref:System.Data.DataSet> には、複数の方法でデータを読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="b91c9-104">There are several different ways to populate the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="b91c9-105">たとえば、[!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] を使用してデータベースのクエリを実行し、その結果を <xref:System.Data.DataSet> に読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="b91c9-105">For example, you can use [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] to query the database and load the results into the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="b91c9-106">詳細については、「[LINQ to SQL](./sql/linq/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b91c9-106">For more information, see [LINQ to SQL](./sql/linq/index.md).</span></span>  
  
 <span data-ttu-id="b91c9-107">データを <xref:System.Data.DataSet> に読み込む一般的な方法としては、他にも <xref:System.Data.Common.DataAdapter> クラスを使用してデータベースからデータを取得する方法もあります。</span><span class="sxs-lookup"><span data-stu-id="b91c9-107">Another common way to load data into a <xref:System.Data.DataSet> is to use the <xref:System.Data.Common.DataAdapter> class to retrieve data from the database.</span></span> <span data-ttu-id="b91c9-108">このことを次の例で説明します。</span><span class="sxs-lookup"><span data-stu-id="b91c9-108">This is illustrated in the following example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b91c9-109">例</span><span class="sxs-lookup"><span data-stu-id="b91c9-109">Example</span></span>  
 <span data-ttu-id="b91c9-110">この例では、<xref:System.Data.Common.DataAdapter> を使用して、2002 年度の売上情報を照会するクエリを AdventureWorks データベースに対して実行し、その結果を <xref:System.Data.DataSet> に読み込んでいます。</span><span class="sxs-lookup"><span data-stu-id="b91c9-110">This example uses a <xref:System.Data.Common.DataAdapter> to query the AdventureWorks database for sales information from the year 2002, and loads the results into a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="b91c9-111"><xref:System.Data.DataSet> を設定した後、LINQ to DataSet を使用して、そのデータセットに対するクエリを作成できます。</span><span class="sxs-lookup"><span data-stu-id="b91c9-111">After the <xref:System.Data.DataSet> has been populated, you can write queries against it by using LINQ to DataSet.</span></span> <span data-ttu-id="b91c9-112">この例の `FillDataSet` メソッドは、「[LINQ to DataSet の例](linq-to-dataset-examples.md)」のクエリ例で使用されています。</span><span class="sxs-lookup"><span data-stu-id="b91c9-112">The `FillDataSet` method in this example is used in the example queries in [LINQ to DataSet Examples](linq-to-dataset-examples.md).</span></span> <span data-ttu-id="b91c9-113">詳しくは、「[DataSet のクエリ](querying-datasets-linq-to-dataset.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b91c9-113">For more information, see [Querying DataSets](querying-datasets-linq-to-dataset.md).</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#FillDataSet](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#filldataset)]
 [!code-vb[DP LINQ to DataSet Examples#FillDataSet](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#filldataset)]  
  
## <a name="see-also"></a><span data-ttu-id="b91c9-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="b91c9-114">See also</span></span>

- [<span data-ttu-id="b91c9-115">LINQ to DataSet の概要</span><span class="sxs-lookup"><span data-stu-id="b91c9-115">LINQ to DataSet Overview</span></span>](linq-to-dataset-overview.md)
- [<span data-ttu-id="b91c9-116">DataSet のクエリ</span><span class="sxs-lookup"><span data-stu-id="b91c9-116">Querying DataSets</span></span>](querying-datasets-linq-to-dataset.md)
- [<span data-ttu-id="b91c9-117">LINQ to DataSet の例</span><span class="sxs-lookup"><span data-stu-id="b91c9-117">LINQ to DataSet Examples</span></span>](linq-to-dataset-examples.md)
