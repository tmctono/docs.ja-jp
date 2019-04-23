---
title: DataTableReader
ms.date: 03/30/2017
ms.assetid: 97546ae2-0e42-4d26-961d-e0b244d81ded
ms.openlocfilehash: a790335a25327563e3dab6093449345b99afd048
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59214002"
---
# <a name="datatablereaders"></a><span data-ttu-id="ba6a3-102">DataTableReader</span><span class="sxs-lookup"><span data-stu-id="ba6a3-102">DataTableReaders</span></span>
<span data-ttu-id="ba6a3-103"><xref:System.Data.DataTableReader> は、<xref:System.Data.DataTable> または <xref:System.Data.DataSet> の内容を、読み取り専用かつ前方参照専用の 1 つ以上の結果セットとして表します。</span><span class="sxs-lookup"><span data-stu-id="ba6a3-103">The <xref:System.Data.DataTableReader> presents the contents of a <xref:System.Data.DataTable> or a <xref:System.Data.DataSet> in the form of one or more read-only, forward-only result sets.</span></span>  
  
 <span data-ttu-id="ba6a3-104">作成するときに、 **DataTableReader**から、 **DataTable**、結果の**DataTableReader**オブジェクトには、1 つの結果と同じデータ セットが含まれています、 **DataTable**から作成した、削除済みとしてマークされているすべての行を除く。</span><span class="sxs-lookup"><span data-stu-id="ba6a3-104">When you create a **DataTableReader** from a **DataTable**, the resulting **DataTableReader** object contains one result set with the same data as the **DataTable** from which it was created, except for any rows that have been marked as deleted.</span></span> <span data-ttu-id="ba6a3-105">列の元と同じ順序で表示**DataTable**します。</span><span class="sxs-lookup"><span data-stu-id="ba6a3-105">The columns appear in the same order as in the original **DataTable**.</span></span>  
  
 <span data-ttu-id="ba6a3-106">A **DataTableReader**呼び出すことによって作成された場合、複数の結果セットを含めることができます<xref:System.Data.DataSet.CreateDataReader%2A>します。</span><span class="sxs-lookup"><span data-stu-id="ba6a3-106">A **DataTableReader** may contain multiple result sets if it was created by calling <xref:System.Data.DataSet.CreateDataReader%2A>.</span></span> <span data-ttu-id="ba6a3-107">結果と同じ順序では、 **Datatable**で、**データセット**オブジェクトの<xref:System.Data.DataSet.Tables%2A>コレクション。</span><span class="sxs-lookup"><span data-stu-id="ba6a3-107">The results are in the same order as the **DataTables** in the **DataSet** object's <xref:System.Data.DataSet.Tables%2A> collection.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ba6a3-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="ba6a3-108">In This Section</span></span>  
 [<span data-ttu-id="ba6a3-109">DataReader の作成</span><span class="sxs-lookup"><span data-stu-id="ba6a3-109">Creating a DataReader</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-a-datareader.md)  
 <span data-ttu-id="ba6a3-110">作成する方法について説明します、 **DataTableReader**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="ba6a3-110">Discusses how to create a **DataTableReader** object.</span></span>  
  
 [<span data-ttu-id="ba6a3-111">DataTable の移動</span><span class="sxs-lookup"><span data-stu-id="ba6a3-111">Navigating DataTables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/navigating-datatables.md)  
 <span data-ttu-id="ba6a3-112">使用について説明します、**読み取り**の内容を移動する方法、 **DataTableReader**します。</span><span class="sxs-lookup"><span data-stu-id="ba6a3-112">Describes the use of the **Read** method to move through the contents of a **DataTableReader**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba6a3-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="ba6a3-113">See also</span></span>

- [<span data-ttu-id="ba6a3-114">ADO.NET でのデータの取得および変更</span><span class="sxs-lookup"><span data-stu-id="ba6a3-114">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)
- [<span data-ttu-id="ba6a3-115">ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター</span><span class="sxs-lookup"><span data-stu-id="ba6a3-115">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
