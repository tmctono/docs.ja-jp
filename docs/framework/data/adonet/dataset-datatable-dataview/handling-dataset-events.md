---
title: DataSet のイベント処理
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 54edefe0-bc38-419b-b486-3d8a0c356f13
ms.openlocfilehash: 5e1de3effcae5700aa25f5dbb84f2dec3a0b20f1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61879685"
---
# <a name="handling-dataset-events"></a><span data-ttu-id="6df59-102">DataSet のイベント処理</span><span class="sxs-lookup"><span data-stu-id="6df59-102">Handling DataSet Events</span></span>
<span data-ttu-id="6df59-103"><xref:System.Data.DataSet> オブジェクトには、 <xref:System.ComponentModel.MarshalByValueComponent.Disposed>、 <xref:System.Data.DataSet.Initialized>、 <xref:System.Data.DataSet.MergeFailed>という 3 つのイベントがあります。</span><span class="sxs-lookup"><span data-stu-id="6df59-103">The <xref:System.Data.DataSet> object provides three events: <xref:System.ComponentModel.MarshalByValueComponent.Disposed>, <xref:System.Data.DataSet.Initialized>, and <xref:System.Data.DataSet.MergeFailed>.</span></span>  
  
## <a name="the-mergefailed-event"></a><span data-ttu-id="6df59-104">MergeFailed イベント</span><span class="sxs-lookup"><span data-stu-id="6df59-104">The MergeFailed Event</span></span>  
 <span data-ttu-id="6df59-105">`DataSet` オブジェクトのイベントの中で最も使用頻度が高いイベントは、マージしようとしている `MergeFailed`オブジェクトのスキーマが競合する場合に発生する `DataSet` です。</span><span class="sxs-lookup"><span data-stu-id="6df59-105">The most commonly used event of the `DataSet` object is `MergeFailed`, which is raised when the schema of the `DataSet` objects being merged are in conflict.</span></span> <span data-ttu-id="6df59-106">この状況は、ターゲットとソースの <xref:System.Data.DataRow> が同じ主キー値を持ち、なおかつ、 <xref:System.Data.DataSet.EnforceConstraints%2A> プロパティが `true`に設定されている場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="6df59-106">This occurs when a target and source <xref:System.Data.DataRow> have the same primary key value, and the <xref:System.Data.DataSet.EnforceConstraints%2A> property is set to `true`.</span></span> <span data-ttu-id="6df59-107">たとえば、マージ対象のテーブルの主キーの列が 2 つの `DataSet` オブジェクトのテーブル間で同じ場合、例外がスローされ、 `MergeFailed` イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="6df59-107">For example, if the primary key columns of a table being merged are the same between the tables in the two `DataSet` objects, an exception is thrown and the `MergeFailed` event is raised.</span></span> <span data-ttu-id="6df59-108"><xref:System.Data.MergeFailedEventArgs> イベントに渡される `MergeFailed` オブジェクトには、2 つの <xref:System.Data.MergeFailedEventArgs.Conflict%2A> オブジェクト間のスキーマで発生した競合を示す `DataSet` プロパティ、および競合が発生したテーブルの名前を示す <xref:System.Data.MergeFailedEventArgs.Table%2A> プロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="6df59-108">The <xref:System.Data.MergeFailedEventArgs> object passed to the `MergeFailed` event have a <xref:System.Data.MergeFailedEventArgs.Conflict%2A> property that identifies the conflict in schema between the two `DataSet` objects, and a <xref:System.Data.MergeFailedEventArgs.Table%2A> property that identifies the name of the table in conflict.</span></span>  
  
 <span data-ttu-id="6df59-109">次のコードは、`MergeFailed` イベントのイベント ハンドラーを追加する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="6df59-109">The following code fragment demonstrates how to add an event handler for the `MergeFailed` event.</span></span>  
  
```vb  
AddHandler workDS.MergeFailed, New MergeFailedEventHandler( _  
  AddressOf DataSetMergeFailed)  
  
Private Shared Sub DataSetMergeFailed(  _  
  sender As Object,args As MergeFailedEventArgs)  
  Console.WriteLine("Merge failed for table " & args.Table.TableName)  
  Console.WriteLine("Conflict = " & args.Conflict)  
End Sub  
```  
  
```csharp  
workDS.MergeFailed += new MergeFailedEventHandler(DataSetMergeFailed);  
  
private static void DataSetMergeFailed(  
  object sender, MergeFailedEventArgs args)  
{  
  Console.WriteLine("Merge failed for table " + args.Table.TableName);  
  Console.WriteLine("Conflict = " + args.Conflict);  
}  
```  
  
## <a name="the-initialized-event"></a><span data-ttu-id="6df59-110">Initialized イベント</span><span class="sxs-lookup"><span data-stu-id="6df59-110">The Initialized Event</span></span>  
 <span data-ttu-id="6df59-111"><xref:System.Data.DataSet.Initialized> イベントは、 `DataSet` のコンストラクターによって `DataSet`の新しいインスタンスが初期化された後に発生します。</span><span class="sxs-lookup"><span data-stu-id="6df59-111">The <xref:System.Data.DataSet.Initialized> event occurs after the `DataSet` constructor initializes a new instance of the `DataSet`.</span></span>  
  
 <span data-ttu-id="6df59-112"><xref:System.Data.DataSet.IsInitialized%2A> プロパティは、 `true` の初期化が完了した場合に `DataSet` を返します。それ以外の場合は `false`を返します。</span><span class="sxs-lookup"><span data-stu-id="6df59-112">The <xref:System.Data.DataSet.IsInitialized%2A> property returns `true` if the `DataSet` has completed initialization; otherwise it returns `false`.</span></span> <span data-ttu-id="6df59-113">この値は、 <xref:System.Data.DataSet.BeginInit%2A> の初期化を開始する `DataSet`メソッドによって <xref:System.Data.DataSet.IsInitialized%2A> が `false`に設定されます。</span><span class="sxs-lookup"><span data-stu-id="6df59-113">The <xref:System.Data.DataSet.BeginInit%2A> method, which begins the initialization of a `DataSet`, sets <xref:System.Data.DataSet.IsInitialized%2A> to `false`.</span></span> <span data-ttu-id="6df59-114">また、 <xref:System.Data.DataSet.EndInit%2A> の初期化を終了する `DataSet`メソッドによって `true`に設定されます。</span><span class="sxs-lookup"><span data-stu-id="6df59-114">The <xref:System.Data.DataSet.EndInit%2A> method, which ends the initialization of the `DataSet`, sets it to `true`.</span></span> <span data-ttu-id="6df59-115">これらのメソッドは、Visual Studio のデザイン環境が初期化に使用される、`DataSet`別のコンポーネントで使用されています。</span><span class="sxs-lookup"><span data-stu-id="6df59-115">These methods are used by the Visual Studio design environment to initialize a `DataSet` that is being used by another component.</span></span> <span data-ttu-id="6df59-116">通常、コード内で直接使用することはありません。</span><span class="sxs-lookup"><span data-stu-id="6df59-116">You will not commonly use them in your code.</span></span>  
  
## <a name="the-disposed-event"></a><span data-ttu-id="6df59-117">Disposed イベント</span><span class="sxs-lookup"><span data-stu-id="6df59-117">The Disposed Event</span></span>  
 <span data-ttu-id="6df59-118">`DataSet` は、 <xref:System.ComponentModel.MarshalByValueComponent> メソッドおよび <xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A> イベントの両方を公開する <xref:System.ComponentModel.MarshalByValueComponent.Disposed> クラスから派生しています。</span><span class="sxs-lookup"><span data-stu-id="6df59-118">`DataSet` is derived from the <xref:System.ComponentModel.MarshalByValueComponent> class, which exposes both the <xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A> method and the <xref:System.ComponentModel.MarshalByValueComponent.Disposed> event.</span></span> <span data-ttu-id="6df59-119"><xref:System.ComponentModel.MarshalByValueComponent.Disposed>コンポーネントのイベントが破棄イベントをリッスンするように、イベント ハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="6df59-119">The <xref:System.ComponentModel.MarshalByValueComponent.Disposed> event adds an event handler to listen to the disposed event on the component.</span></span> <span data-ttu-id="6df59-120">使用することができます、<xref:System.ComponentModel.MarshalByValueComponent.Disposed>のイベントを`DataSet`を実行する場合は、ときにコード、<xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A>メソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="6df59-120">You can use the <xref:System.ComponentModel.MarshalByValueComponent.Disposed> event of a `DataSet` if you want to execute code when the <xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A> method is called.</span></span> <span data-ttu-id="6df59-121"><xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A> 使用されるリソースを解放、<xref:System.ComponentModel.MarshalByValueComponent>します。</span><span class="sxs-lookup"><span data-stu-id="6df59-121"><xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A> releases the resources used by the <xref:System.ComponentModel.MarshalByValueComponent>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6df59-122">`DataSet`と`DataTable`オブジェクトから継承<xref:System.ComponentModel.MarshalByValueComponent>をサポートし、<xref:System.Runtime.Serialization.ISerializable>リモート処理用のインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="6df59-122">The `DataSet` and `DataTable` objects inherit from <xref:System.ComponentModel.MarshalByValueComponent> and support the <xref:System.Runtime.Serialization.ISerializable> interface for remoting.</span></span> <span data-ttu-id="6df59-123">これらは、リモート処理ができる唯一の ADO.NET オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="6df59-123">These are the only ADO.NET objects that can be remoted.</span></span> <span data-ttu-id="6df59-124">詳細については、次を参照してください。 [.NET リモート処理](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/72x4h507(v=vs.100))します。</span><span class="sxs-lookup"><span data-stu-id="6df59-124">For more information, see [.NET Remoting](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/72x4h507(v=vs.100)).</span></span>  
  
 <span data-ttu-id="6df59-125">使用する場合に使用可能なその他のイベントについては、`DataSet`を参照してください[DataTable イベントの処理](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-datatable-events.md)と[DataAdapter イベントの処理](../../../../../docs/framework/data/adonet/handling-dataadapter-events.md)します。</span><span class="sxs-lookup"><span data-stu-id="6df59-125">For information about other events available when working with a `DataSet`, see [Handling DataTable Events](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-datatable-events.md) and [Handling DataAdapter Events](../../../../../docs/framework/data/adonet/handling-dataadapter-events.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6df59-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="6df59-126">See also</span></span>

- [<span data-ttu-id="6df59-127">DataSet、DataTable、および DataView</span><span class="sxs-lookup"><span data-stu-id="6df59-127">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- <span data-ttu-id="6df59-128">[データの検証](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/t3b36awf(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="6df59-128">[Validating Data](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/t3b36awf(v=vs.120))</span></span>
- [<span data-ttu-id="6df59-129">ADO.NET でのデータの取得および変更</span><span class="sxs-lookup"><span data-stu-id="6df59-129">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)
- [<span data-ttu-id="6df59-130">ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター</span><span class="sxs-lookup"><span data-stu-id="6df59-130">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
