---
title: 型指定された DataSet のクエリ
ms.date: 08/15/2018
dev_langs:
- csharp
- vb
ms.assetid: ad712fa1-2baf-462a-b163-574cce6d376a
ms.openlocfilehash: 55714c4dae73cd17a849cc35681797dfa4266e3b
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70782968"
---
# <a name="query-typed-datasets"></a><span data-ttu-id="9f776-102">型指定されたデータセットのクエリ</span><span class="sxs-lookup"><span data-stu-id="9f776-102">Query typed DataSets</span></span>

<span data-ttu-id="9f776-103">アプリケーションのデザイン時に<xref:System.Data.DataSet>のスキーマがわかっている場合は、LINQ to DataSet を使用するとき<xref:System.Data.DataSet>に、型指定されたを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9f776-103">If the schema of the <xref:System.Data.DataSet> is known at application design time, we recommend that you use a typed <xref:System.Data.DataSet> when using LINQ to DataSet.</span></span> <span data-ttu-id="9f776-104">型指定<xref:System.Data.DataSet>されたは、 <xref:System.Data.DataSet>から派生するクラスです。</span><span class="sxs-lookup"><span data-stu-id="9f776-104">A typed <xref:System.Data.DataSet> is a class that derives from a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="9f776-105">したがって、型指定されたデータセットは <xref:System.Data.DataSet> のすべてのメソッド、イベント、およびプロパティを継承します。</span><span class="sxs-lookup"><span data-stu-id="9f776-105">As such, it inherits all the methods, events, and properties of a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="9f776-106">さらに、型<xref:System.Data.DataSet>指定されたは、厳密に型指定されたメソッド、イベント、およびプロパティを提供します。</span><span class="sxs-lookup"><span data-stu-id="9f776-106">Additionally, a typed <xref:System.Data.DataSet> provides strongly typed methods, events, and properties.</span></span> <span data-ttu-id="9f776-107">つまり、コレクションベースのメソッドを使用せずに名前でテーブルおよび列にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="9f776-107">This means that you can access tables and columns by name, instead of using collection-based methods.</span></span> <span data-ttu-id="9f776-108">これによりクエリが簡素化され、読みやすくなります。</span><span class="sxs-lookup"><span data-stu-id="9f776-108">This makes queries simpler and more readable.</span></span> <span data-ttu-id="9f776-109">詳細については、「型指定された[データセット](./dataset-datatable-dataview/typed-datasets.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9f776-109">For more information, see [Typed DataSets](./dataset-datatable-dataview/typed-datasets.md).</span></span>

<span data-ttu-id="9f776-110">LINQ to DataSet は、型指定<xref:System.Data.DataSet>されたに対するクエリもサポートしています。</span><span class="sxs-lookup"><span data-stu-id="9f776-110">LINQ to DataSet also supports querying over a typed <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="9f776-111">型指定<xref:System.Data.DataSet>されたを使用する場合、列データにアクセス<xref:System.Data.DataRowExtensions.SetField%2A>するためにジェネリック<xref:System.Data.DataRowExtensions.Field%2A>メソッドまたはメソッドを使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="9f776-111">With a typed <xref:System.Data.DataSet>, you do not have to use the generic <xref:System.Data.DataRowExtensions.Field%2A> method or <xref:System.Data.DataRowExtensions.SetField%2A> method to access column data.</span></span> <span data-ttu-id="9f776-112">型情報はに<xref:System.Data.DataSet>含まれるため、コンパイル時にプロパティ名を使用できます。</span><span class="sxs-lookup"><span data-stu-id="9f776-112">Property names are available at compile time because the type information is included in the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="9f776-113">LINQ to DataSet は、列の値へのアクセスを正しい型として提供するため、実行時ではなく、コードをコンパイルするときに型の不一致エラーがキャッチされます。</span><span class="sxs-lookup"><span data-stu-id="9f776-113">LINQ to DataSet provides access to column values as the correct type, so that type mismatch errors are caught when the code is compiled instead of at run time.</span></span>

<span data-ttu-id="9f776-114">型指定<xref:System.Data.DataSet>されたのクエリを開始するには、Visual Studio の**データセットデザイナー**を使用してクラスを生成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f776-114">Before you can begin querying a typed <xref:System.Data.DataSet>, you must generate the class by using the **DataSet Designer** in Visual Studio.</span></span> <span data-ttu-id="9f776-115">詳細については、「[データセットの作成と構成](/visualstudio/data-tools/create-and-configure-datasets-in-visual-studio)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9f776-115">For more information, see [Create and configure DataSets](/visualstudio/data-tools/create-and-configure-datasets-in-visual-studio).</span></span>

## <a name="example"></a><span data-ttu-id="9f776-116">例</span><span class="sxs-lookup"><span data-stu-id="9f776-116">Example</span></span>

<span data-ttu-id="9f776-117">次の例では、型指定された <xref:System.Data.DataSet> に対してクエリを実行しています。</span><span class="sxs-lookup"><span data-stu-id="9f776-117">The following example shows a query over a typed <xref:System.Data.DataSet>:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="9f776-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="9f776-118">See also</span></span>

- [<span data-ttu-id="9f776-119">DataSet のクエリ</span><span class="sxs-lookup"><span data-stu-id="9f776-119">Querying DataSets</span></span>](querying-datasets-linq-to-dataset.md)
- [<span data-ttu-id="9f776-120">複数テーブルにまたがるクエリ</span><span class="sxs-lookup"><span data-stu-id="9f776-120">Cross-Table Queries</span></span>](cross-table-queries-linq-to-dataset.md)
- [<span data-ttu-id="9f776-121">単一テーブルのクエリ</span><span class="sxs-lookup"><span data-stu-id="9f776-121">Single-Table Queries</span></span>](single-table-queries-linq-to-dataset.md)
