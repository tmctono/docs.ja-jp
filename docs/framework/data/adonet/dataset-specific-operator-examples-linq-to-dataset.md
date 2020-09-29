---
title: DataSet 固有の演算子の例 (LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8fdd64af-6ad0-46cd-91c8-dbe26620eeb1
ms.openlocfilehash: 4cd99a103fabee3c87036a9933077a3a967f5a13
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173693"
---
# <a name="dataset-specific-operator-examples-linq-to-dataset"></a><span data-ttu-id="94d2c-102">DataSet 固有の演算子の例 (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="94d2c-102">DataSet-Specific Operator Examples (LINQ to DataSet)</span></span>

<span data-ttu-id="94d2c-103">このトピックでは、<xref:System.Data.DataTableExtensions.CopyToDataTable%2A> メソッドおよび <xref:System.Data.DataRowComparer> クラスの使用例を紹介しています。</span><span class="sxs-lookup"><span data-stu-id="94d2c-103">The examples in this topic demonstrate how to use the <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> method and the <xref:System.Data.DataRowComparer> class.</span></span>  
  
 <span data-ttu-id="94d2c-104">これらの例で使用されている `FillDataSet` メソッドは、「[DataSet へのデータの読み込み](loading-data-into-a-dataset.md)」で指定されています。</span><span class="sxs-lookup"><span data-stu-id="94d2c-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="94d2c-105">このトピックの例には、AdventureWorks サンプル データベースの Contact、Address、Product、SalesOrderHeader、SalesOrderDetail の各テーブルが使用されています。</span><span class="sxs-lookup"><span data-stu-id="94d2c-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="94d2c-106">このトピックの例には、次の `using`/`Imports` ステートメントが使用されています。</span><span class="sxs-lookup"><span data-stu-id="94d2c-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="94d2c-107">詳細については、[Visual Studio で LINQ to DataSet プロジェクトを作成する](how-to-create-a-linq-to-dataset-project-in-vs.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="94d2c-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="copytodatatable"></a><span data-ttu-id="94d2c-108">CopyToDataTable</span><span class="sxs-lookup"><span data-stu-id="94d2c-108">CopyToDataTable</span></span>  
  
### <a name="example"></a><span data-ttu-id="94d2c-109">例</span><span class="sxs-lookup"><span data-stu-id="94d2c-109">Example</span></span>  

 <span data-ttu-id="94d2c-110">この例では、<xref:System.Data.DataTable> メソッドを使用して、<xref:System.Data.DataTableExtensions.CopyToDataTable%2A> にクエリ結果を読み込みます。</span><span class="sxs-lookup"><span data-stu-id="94d2c-110">This example loads a <xref:System.Data.DataTable> with query results by using the <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> method.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#LoadDataTableWithQueryResults](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#loaddatatablewithqueryresults)]
 [!code-vb[DP LINQ to DataSet Examples#LoadDataTableWithQueryResults](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#loaddatatablewithqueryresults)]  
  
## <a name="datarowcomparer"></a><span data-ttu-id="94d2c-111">DataRowComparer</span><span class="sxs-lookup"><span data-stu-id="94d2c-111">DataRowComparer</span></span>  
  
### <a name="example"></a><span data-ttu-id="94d2c-112">例</span><span class="sxs-lookup"><span data-stu-id="94d2c-112">Example</span></span>  

 <span data-ttu-id="94d2c-113">この例では 2 つの異なるデータ行を <xref:System.Data.DataRowComparer> を使用して比較します。</span><span class="sxs-lookup"><span data-stu-id="94d2c-113">This example compares two different data rows by using <xref:System.Data.DataRowComparer>.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#CompareDifferentDataRows](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#comparedifferentdatarows)]  
  
## <a name="see-also"></a><span data-ttu-id="94d2c-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="94d2c-114">See also</span></span>

- [<span data-ttu-id="94d2c-115">DataSet へのデータの読み込み</span><span class="sxs-lookup"><span data-stu-id="94d2c-115">Loading Data Into a DataSet</span></span>](loading-data-into-a-dataset.md)
- [<span data-ttu-id="94d2c-116">LINQ to DataSet の例</span><span class="sxs-lookup"><span data-stu-id="94d2c-116">LINQ to DataSet Examples</span></span>](linq-to-dataset-examples.md)
