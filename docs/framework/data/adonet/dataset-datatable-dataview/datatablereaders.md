---
title: DataTableReader
ms.date: 03/30/2017
ms.assetid: 97546ae2-0e42-4d26-961d-e0b244d81ded
ms.openlocfilehash: 1559cde9cb786ccb2baf920347064b8b28d472c3
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70785350"
---
# <a name="datatablereaders"></a><span data-ttu-id="62a5a-102">DataTableReader</span><span class="sxs-lookup"><span data-stu-id="62a5a-102">DataTableReaders</span></span>
<span data-ttu-id="62a5a-103"><xref:System.Data.DataTableReader> は、<xref:System.Data.DataTable> または <xref:System.Data.DataSet> の内容を、読み取り専用かつ前方参照専用の 1 つ以上の結果セットとして表します。</span><span class="sxs-lookup"><span data-stu-id="62a5a-103">The <xref:System.Data.DataTableReader> presents the contents of a <xref:System.Data.DataTable> or a <xref:System.Data.DataSet> in the form of one or more read-only, forward-only result sets.</span></span>  
  
 <span data-ttu-id="62a5a-104">**Datatable**から**DataTableReader**を作成すると、結果の**DataTableReader**オブジェクトには、作成元の**datatable**と同じデータを持つ1つの結果セットが含まれます。ただし、としてマークされている行は除きます。削除.</span><span class="sxs-lookup"><span data-stu-id="62a5a-104">When you create a **DataTableReader** from a **DataTable**, the resulting **DataTableReader** object contains one result set with the same data as the **DataTable** from which it was created, except for any rows that have been marked as deleted.</span></span> <span data-ttu-id="62a5a-105">列は、元の**DataTable**と同じ順序で表示されます。</span><span class="sxs-lookup"><span data-stu-id="62a5a-105">The columns appear in the same order as in the original **DataTable**.</span></span>  
  
 <span data-ttu-id="62a5a-106">**DataTableReader**は、を呼び出す<xref:System.Data.DataSet.CreateDataReader%2A>ことによって作成された場合、複数の結果セットを含むことができます。</span><span class="sxs-lookup"><span data-stu-id="62a5a-106">A **DataTableReader** may contain multiple result sets if it was created by calling <xref:System.Data.DataSet.CreateDataReader%2A>.</span></span> <span data-ttu-id="62a5a-107">結果は、**データセット**オブジェクトの<xref:System.Data.DataSet.Tables%2A>コレクション内の**datatable**と同じ順序で表示されます。</span><span class="sxs-lookup"><span data-stu-id="62a5a-107">The results are in the same order as the **DataTables** in the **DataSet** object's <xref:System.Data.DataSet.Tables%2A> collection.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="62a5a-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="62a5a-108">In This Section</span></span>  
 [<span data-ttu-id="62a5a-109">DataReader の作成</span><span class="sxs-lookup"><span data-stu-id="62a5a-109">Creating a DataReader</span></span>](creating-a-datareader.md)  
 <span data-ttu-id="62a5a-110">**DataTableReader**オブジェクトを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="62a5a-110">Discusses how to create a **DataTableReader** object.</span></span>  
  
 [<span data-ttu-id="62a5a-111">DataTable の移動</span><span class="sxs-lookup"><span data-stu-id="62a5a-111">Navigating DataTables</span></span>](navigating-datatables.md)  
 <span data-ttu-id="62a5a-112">**Read**メソッドを使用して、 **DataTableReader**の内容を移動する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="62a5a-112">Describes the use of the **Read** method to move through the contents of a **DataTableReader**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62a5a-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="62a5a-113">See also</span></span>

- [<span data-ttu-id="62a5a-114">ADO.NET でのデータの取得および変更</span><span class="sxs-lookup"><span data-stu-id="62a5a-114">Retrieving and Modifying Data in ADO.NET</span></span>](../retrieving-and-modifying-data.md)
- [<span data-ttu-id="62a5a-115">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="62a5a-115">ADO.NET Overview</span></span>](../ado-net-overview.md)
