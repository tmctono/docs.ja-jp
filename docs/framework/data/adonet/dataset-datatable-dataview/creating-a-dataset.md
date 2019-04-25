---
title: DataSet の作成
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 57629d8f-393e-4677-8b83-29ffde27f5fc
ms.openlocfilehash: d2d17056e6dcd29ef9b5c5e8c3024a32fce32bd5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61879880"
---
# <a name="creating-a-dataset"></a><span data-ttu-id="191c6-102">DataSet の作成</span><span class="sxs-lookup"><span data-stu-id="191c6-102">Creating a DataSet</span></span>
<span data-ttu-id="191c6-103"><xref:System.Data.DataSet> のインスタンスを作成するには、<xref:System.Data.DataSet> のコンストラクターを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="191c6-103">You create an instance of a <xref:System.Data.DataSet> by calling the <xref:System.Data.DataSet> constructor.</span></span> <span data-ttu-id="191c6-104">必要に応じて、引数 name を指定します。</span><span class="sxs-lookup"><span data-stu-id="191c6-104">Optionally specify a name argument.</span></span> <span data-ttu-id="191c6-105">名前を指定しない場合、<xref:System.Data.DataSet> の名前は "NewDataSet" に設定されます。</span><span class="sxs-lookup"><span data-stu-id="191c6-105">If you do not specify a name for the <xref:System.Data.DataSet>, the name is set to "NewDataSet".</span></span>  
  
 <span data-ttu-id="191c6-106">また、既存の <xref:System.Data.DataSet> に基づいて新しい <xref:System.Data.DataSet> を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="191c6-106">You can also create a new <xref:System.Data.DataSet> based on an existing <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="191c6-107">既存の <xref:System.Data.DataSet> の正確なコピーを新しい <xref:System.Data.DataSet> として作成できるのは、リレーショナル構造またはスキーマはコピーするけれども既存の <xref:System.Data.DataSet> からのデータは含まない <xref:System.Data.DataSet> のクローン、または <xref:System.Data.DataSet> メソッドを使用して既存の <xref:System.Data.DataSet> から変更された行だけを含む <xref:System.Data.DataSet.GetChanges%2A> のサブセットのいずれかです。</span><span class="sxs-lookup"><span data-stu-id="191c6-107">The new <xref:System.Data.DataSet> can be an exact copy of the existing <xref:System.Data.DataSet>; a clone of the <xref:System.Data.DataSet> that copies the relational structure or schema but that does not contain any of the data from the existing <xref:System.Data.DataSet>; or a subset of the <xref:System.Data.DataSet>, containing only the modified rows from the existing <xref:System.Data.DataSet> using the <xref:System.Data.DataSet.GetChanges%2A> method.</span></span> <span data-ttu-id="191c6-108">詳細については、次を参照してください。 [DataSet の内容をコピー](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/copying-dataset-contents.md)します。</span><span class="sxs-lookup"><span data-stu-id="191c6-108">For more information, see [Copying DataSet Contents](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/copying-dataset-contents.md).</span></span>  
  
 <span data-ttu-id="191c6-109"><xref:System.Data.DataSet> のインスタンスの作成方法を示すコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="191c6-109">The following code example demonstrates how to construct an instance of a <xref:System.Data.DataSet>.</span></span>  
  
```vb  
Dim customerOrders As DataSet = New DataSet("CustomerOrders")  
```  
  
```csharp  
DataSet customerOrders = new DataSet("CustomerOrders");  
```  
  
## <a name="see-also"></a><span data-ttu-id="191c6-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="191c6-110">See also</span></span>

- [<span data-ttu-id="191c6-111">DataAdapter からの DataSet の読み込み</span><span class="sxs-lookup"><span data-stu-id="191c6-111">Populating a DataSet from a DataAdapter</span></span>](../../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md)
- [<span data-ttu-id="191c6-112">DataSet、DataTable、および DataView</span><span class="sxs-lookup"><span data-stu-id="191c6-112">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [<span data-ttu-id="191c6-113">ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター</span><span class="sxs-lookup"><span data-stu-id="191c6-113">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
