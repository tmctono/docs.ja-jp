---
title: 型指定された DataSet のクエリ
ms.date: 08/15/2018
dev_langs:
- csharp
- vb
ms.assetid: ad712fa1-2baf-462a-b163-574cce6d376a
ms.openlocfilehash: d956fd5f07c108146d20623bcf811266380c132c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61651741"
---
# <a name="query-typed-datasets"></a><span data-ttu-id="86bc4-102">型指定されたデータセットのクエリ</span><span class="sxs-lookup"><span data-stu-id="86bc4-102">Query typed DataSets</span></span>

<span data-ttu-id="86bc4-103">場合のスキーマ、 <xref:System.Data.DataSet> 、型指定されたを使用することをお勧めします。 アプリケーションのデザイン時に認識が<xref:System.Data.DataSet>LINQ to DataSet を使用する場合。</span><span class="sxs-lookup"><span data-stu-id="86bc4-103">If the schema of the <xref:System.Data.DataSet> is known at application design time, we recommend that you use a typed <xref:System.Data.DataSet> when using LINQ to DataSet.</span></span> <span data-ttu-id="86bc4-104">型指定された<xref:System.Data.DataSet>から派生したクラスには、<xref:System.Data.DataSet>します。</span><span class="sxs-lookup"><span data-stu-id="86bc4-104">A typed <xref:System.Data.DataSet> is a class that derives from a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="86bc4-105">したがって、型指定されたデータセットは <xref:System.Data.DataSet> のすべてのメソッド、イベント、およびプロパティを継承します。</span><span class="sxs-lookup"><span data-stu-id="86bc4-105">As such, it inherits all the methods, events, and properties of a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="86bc4-106">さらに、型指定された<xref:System.Data.DataSet>厳密に型指定されたメソッド、イベント、およびプロパティを提供します。</span><span class="sxs-lookup"><span data-stu-id="86bc4-106">Additionally, a typed <xref:System.Data.DataSet> provides strongly typed methods, events, and properties.</span></span> <span data-ttu-id="86bc4-107">つまり、コレクションベースのメソッドを使用せずに名前でテーブルおよび列にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="86bc4-107">This means that you can access tables and columns by name, instead of using collection-based methods.</span></span> <span data-ttu-id="86bc4-108">これによりクエリが簡素化され、読みやすくなります。</span><span class="sxs-lookup"><span data-stu-id="86bc4-108">This makes queries simpler and more readable.</span></span> <span data-ttu-id="86bc4-109">詳細については、次を参照してください。[型指定されたデータセット](../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md)します。</span><span class="sxs-lookup"><span data-stu-id="86bc4-109">For more information, see [Typed DataSets](../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md).</span></span>

<span data-ttu-id="86bc4-110">LINQ to DataSet がに対する型指定されたクエリの実行をサポートしても<xref:System.Data.DataSet>します。</span><span class="sxs-lookup"><span data-stu-id="86bc4-110">LINQ to DataSet also supports querying over a typed <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="86bc4-111">型指定された<xref:System.Data.DataSet>、ジェネリックを使用する必要はありません<xref:System.Data.DataRowExtensions.Field%2A>メソッドまたは<xref:System.Data.DataRowExtensions.SetField%2A>列データにアクセスするメソッド。</span><span class="sxs-lookup"><span data-stu-id="86bc4-111">With a typed <xref:System.Data.DataSet>, you do not have to use the generic <xref:System.Data.DataRowExtensions.Field%2A> method or <xref:System.Data.DataRowExtensions.SetField%2A> method to access column data.</span></span> <span data-ttu-id="86bc4-112">型情報が含まれているために、プロパティ名はコンパイル時に使用可能な<xref:System.Data.DataSet>します。</span><span class="sxs-lookup"><span data-stu-id="86bc4-112">Property names are available at compile time because the type information is included in the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="86bc4-113">LINQ to DataSet では、実行時の代わりに、コードがコンパイルされるときに、型の不一致エラーがキャッチされるように、適切な型として列の値へのアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="86bc4-113">LINQ to DataSet provides access to column values as the correct type, so that type mismatch errors are caught when the code is compiled instead of at run time.</span></span>

<span data-ttu-id="86bc4-114">型指定されたクエリを開始する前に<xref:System.Data.DataSet>を使用して、クラスを生成する必要があります、**データセット デザイナー** Visual Studio でします。</span><span class="sxs-lookup"><span data-stu-id="86bc4-114">Before you can begin querying a typed <xref:System.Data.DataSet>, you must generate the class by using the **DataSet Designer** in Visual Studio.</span></span> <span data-ttu-id="86bc4-115">詳細については、次を参照してください。[作成し、データセットを構成](/visualstudio/data-tools/create-and-configure-datasets-in-visual-studio)します。</span><span class="sxs-lookup"><span data-stu-id="86bc4-115">For more information, see [Create and configure DataSets](/visualstudio/data-tools/create-and-configure-datasets-in-visual-studio).</span></span>

## <a name="example"></a><span data-ttu-id="86bc4-116">例</span><span class="sxs-lookup"><span data-stu-id="86bc4-116">Example</span></span>

<span data-ttu-id="86bc4-117">次の例では、型指定された <xref:System.Data.DataSet> に対してクエリを実行しています。</span><span class="sxs-lookup"><span data-stu-id="86bc4-117">The following example shows a query over a typed <xref:System.Data.DataSet>:</span></span>

```csharp
var query = from o in orders
            where o.OnlineOrderFlag == true
            select new { o.SalesOrderID,
                         o.OrderDate,
                         o.SalesOrderNumber };

foreach(var order in query)
{
    Console.WriteLine("{0}\t{1:d}\t{2}",
      order.SalesOrderID,
      order.OrderDate,
      order.SalesOrderNumber);
}
```

```vb
Dim orders = ds.Tables("SalesOrderHeader")

Dim query = _
       From o In orders _
       Where o.OnlineOrderFlag = True _
       Select New {SalesOrderID := o.SalesOrderID, _
                   OrderDate := o.OrderDate, _
                   SalesOrderNumber := o.SalesOrderNumber}

For Each Dim onlineOrder In query
 Console.WriteLine("{0}\t{1:d}\t{2}", _
 onlineOrder.SalesOrderID, _
 onlineOrder.OrderDate, _
 onlineOrder.SalesOrderNumber)
Next
```

## <a name="see-also"></a><span data-ttu-id="86bc4-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="86bc4-118">See also</span></span>

- [<span data-ttu-id="86bc4-119">DataSet のクエリ</span><span class="sxs-lookup"><span data-stu-id="86bc4-119">Querying DataSets</span></span>](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md)
- [<span data-ttu-id="86bc4-120">複数テーブルにまたがるクエリ</span><span class="sxs-lookup"><span data-stu-id="86bc4-120">Cross-Table Queries</span></span>](../../../../docs/framework/data/adonet/cross-table-queries-linq-to-dataset.md)
- [<span data-ttu-id="86bc4-121">単一テーブルのクエリ</span><span class="sxs-lookup"><span data-stu-id="86bc4-121">Single-Table Queries</span></span>](../../../../docs/framework/data/adonet/single-table-queries-linq-to-dataset.md)
