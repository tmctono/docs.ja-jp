---
title: DataTableReader
ms.date: 03/30/2017
ms.assetid: 97546ae2-0e42-4d26-961d-e0b244d81ded
ms.openlocfilehash: 1ff7868b59c6fdc4e6c443be1b831accc84f36a6
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2019
ms.locfileid: "70203825"
---
# <a name="datatablereaders"></a><span data-ttu-id="6e4e8-102">DataTableReader</span><span class="sxs-lookup"><span data-stu-id="6e4e8-102">DataTableReaders</span></span>
<span data-ttu-id="6e4e8-103"><xref:System.Data.DataTableReader> は、<xref:System.Data.DataTable> または <xref:System.Data.DataSet> の内容を、読み取り専用かつ前方参照専用の 1 つ以上の結果セットとして表します。</span><span class="sxs-lookup"><span data-stu-id="6e4e8-103">The <xref:System.Data.DataTableReader> presents the contents of a <xref:System.Data.DataTable> or a <xref:System.Data.DataSet> in the form of one or more read-only, forward-only result sets.</span></span>  
  
 <span data-ttu-id="6e4e8-104">**Datatable**から**DataTableReader**を作成すると、結果の**DataTableReader**オブジェクトには、作成元の**datatable**と同じデータを持つ1つの結果セットが含まれます。ただし、としてマークされている行は除きます。削除.</span><span class="sxs-lookup"><span data-stu-id="6e4e8-104">When you create a **DataTableReader** from a **DataTable**, the resulting **DataTableReader** object contains one result set with the same data as the **DataTable** from which it was created, except for any rows that have been marked as deleted.</span></span> <span data-ttu-id="6e4e8-105">列は、元の**DataTable**と同じ順序で表示されます。</span><span class="sxs-lookup"><span data-stu-id="6e4e8-105">The columns appear in the same order as in the original **DataTable**.</span></span>  
  
 <span data-ttu-id="6e4e8-106">**DataTableReader**は、を呼び出す<xref:System.Data.DataSet.CreateDataReader%2A>ことによって作成された場合、複数の結果セットを含むことができます。</span><span class="sxs-lookup"><span data-stu-id="6e4e8-106">A **DataTableReader** may contain multiple result sets if it was created by calling <xref:System.Data.DataSet.CreateDataReader%2A>.</span></span> <span data-ttu-id="6e4e8-107">結果は、**データセット**オブジェクトの<xref:System.Data.DataSet.Tables%2A>コレクション内の**datatable**と同じ順序で表示されます。</span><span class="sxs-lookup"><span data-stu-id="6e4e8-107">The results are in the same order as the **DataTables** in the **DataSet** object's <xref:System.Data.DataSet.Tables%2A> collection.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6e4e8-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="6e4e8-108">In This Section</span></span>  
 [<span data-ttu-id="6e4e8-109">DataReader の作成</span><span class="sxs-lookup"><span data-stu-id="6e4e8-109">Creating a DataReader</span></span>](creating-a-datareader.md)  
 <span data-ttu-id="6e4e8-110">**DataTableReader**オブジェクトを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6e4e8-110">Discusses how to create a **DataTableReader** object.</span></span>  
  
 [<span data-ttu-id="6e4e8-111">DataTable の移動</span><span class="sxs-lookup"><span data-stu-id="6e4e8-111">Navigating DataTables</span></span>](navigating-datatables.md)  
 <span data-ttu-id="6e4e8-112">**Read**メソッドを使用して、 **DataTableReader**の内容を移動する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6e4e8-112">Describes the use of the **Read** method to move through the contents of a **DataTableReader**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e4e8-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="6e4e8-113">See also</span></span>

- [<span data-ttu-id="6e4e8-114">ADO.NET でのデータの取得および変更</span><span class="sxs-lookup"><span data-stu-id="6e4e8-114">Retrieving and Modifying Data in ADO.NET</span></span>](../retrieving-and-modifying-data.md)
- [<span data-ttu-id="6e4e8-115">ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター</span><span class="sxs-lookup"><span data-stu-id="6e4e8-115">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
