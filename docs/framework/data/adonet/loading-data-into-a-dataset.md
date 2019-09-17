---
title: DataSet へのデータの読み込み
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a53e5dc1-9669-49d4-828d-efa633237066
ms.openlocfilehash: 53f0f5a589a0033c9612f0465dff090ab04e3fc4
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70794960"
---
# <a name="loading-data-into-a-dataset"></a><span data-ttu-id="2f42f-102">DataSet へのデータの読み込み</span><span class="sxs-lookup"><span data-stu-id="2f42f-102">Loading Data Into a DataSet</span></span>
<span data-ttu-id="2f42f-103">LINQ to DataSet <xref:System.Data.DataSet>でクエリを実行する前に、まずオブジェクトに値を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f42f-103">A <xref:System.Data.DataSet> object must first be populated before you can query over it with LINQ to DataSet.</span></span> <span data-ttu-id="2f42f-104"><xref:System.Data.DataSet> には、複数の方法でデータを読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="2f42f-104">There are several different ways to populate the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="2f42f-105">たとえば、を使用[!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)]してデータベースに対してクエリを実行し、その<xref:System.Data.DataSet>結果をに読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="2f42f-105">For example, you can use [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] to query the database and load the results into the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="2f42f-106">詳細については、「[LINQ to SQL](./sql/linq/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2f42f-106">For more information, see [LINQ to SQL](./sql/linq/index.md).</span></span>  
  
 <span data-ttu-id="2f42f-107">データを <xref:System.Data.DataSet> に読み込む一般的な方法としては、他にも <xref:System.Data.Common.DataAdapter> クラスを使用してデータベースからデータを取得する方法もあります。</span><span class="sxs-lookup"><span data-stu-id="2f42f-107">Another common way to load data into a <xref:System.Data.DataSet> is to use the <xref:System.Data.Common.DataAdapter> class to retrieve data from the database.</span></span> <span data-ttu-id="2f42f-108">この例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2f42f-108">This is illustrated in the following example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2f42f-109">例</span><span class="sxs-lookup"><span data-stu-id="2f42f-109">Example</span></span>  
 <span data-ttu-id="2f42f-110">この例では、<xref:System.Data.Common.DataAdapter> を使用して、2002 年度の売上情報を照会するクエリを AdventureWorks データベースに対して実行し、その結果を <xref:System.Data.DataSet> に読み込んでいます。</span><span class="sxs-lookup"><span data-stu-id="2f42f-110">This example uses a <xref:System.Data.Common.DataAdapter> to query the AdventureWorks database for sales information from the year 2002, and loads the results into a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="2f42f-111">に値<xref:System.Data.DataSet>が設定されたら、LINQ to DataSet を使用して、そのデータに対するクエリを作成できます。</span><span class="sxs-lookup"><span data-stu-id="2f42f-111">After the <xref:System.Data.DataSet> has been populated, you can write queries against it by using LINQ to DataSet.</span></span> <span data-ttu-id="2f42f-112">この例の `FillDataSet` メソッドは [LINQtoDataSet 例](linq-to-dataset-examples.md)のクエリ例で使用されています。</span><span class="sxs-lookup"><span data-stu-id="2f42f-112">The `FillDataSet` method in this example is used in the example queries in [LINQ to DataSet Examples](linq-to-dataset-examples.md).</span></span> <span data-ttu-id="2f42f-113">詳細については、「[データセットのクエリ](querying-datasets-linq-to-dataset.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2f42f-113">For more information, see [Querying DataSets](querying-datasets-linq-to-dataset.md).</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#FillDataSet](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#filldataset)]
 [!code-vb[DP LINQ to DataSet Examples#FillDataSet](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#filldataset)]  
  
## <a name="see-also"></a><span data-ttu-id="2f42f-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="2f42f-114">See also</span></span>

- [<span data-ttu-id="2f42f-115">LINQ to DataSet の概要</span><span class="sxs-lookup"><span data-stu-id="2f42f-115">LINQ to DataSet Overview</span></span>](linq-to-dataset-overview.md)
- [<span data-ttu-id="2f42f-116">DataSet のクエリ</span><span class="sxs-lookup"><span data-stu-id="2f42f-116">Querying DataSets</span></span>](querying-datasets-linq-to-dataset.md)
- [<span data-ttu-id="2f42f-117">LINQ to DataSet の例</span><span class="sxs-lookup"><span data-stu-id="2f42f-117">LINQ to DataSet Examples</span></span>](linq-to-dataset-examples.md)
