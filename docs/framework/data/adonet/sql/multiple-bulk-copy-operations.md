---
title: バルク コピー操作の複数実行
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5ad12f94-7459-4a93-a421-4160d1a90715
ms.openlocfilehash: 838f56311f165c99c71cc734576bbdb53a946b7c
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70792069"
---
# <a name="multiple-bulk-copy-operations"></a><span data-ttu-id="789f2-102">バルク コピー操作の複数実行</span><span class="sxs-lookup"><span data-stu-id="789f2-102">Multiple Bulk Copy Operations</span></span>
<span data-ttu-id="789f2-103"><xref:System.Data.SqlClient.SqlBulkCopy> クラスのインスタンスを 1 つ使用すると、バルク コピー操作を複数回実行できます。</span><span class="sxs-lookup"><span data-stu-id="789f2-103">You can perform multiple bulk copy operations using a single instance of a <xref:System.Data.SqlClient.SqlBulkCopy> class.</span></span> <span data-ttu-id="789f2-104">コピー先のテーブルの名前など、操作パラメーターが変更された場合は、次の例に示すように、 **WriteToServer**メソッドのいずれかの後続の呼び出しの前に、これらのパラメーターを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="789f2-104">If the operation parameters change between copies (for example, the name of the destination table), you must update them prior to any subsequent calls to any of the **WriteToServer** methods, as demonstrated in the following example.</span></span> <span data-ttu-id="789f2-105">明示的に変更されている場合を除き、すべてのプロパティ値は、任意のインスタンスに対する前回のバルク コピー操作の状態のまま残っています。</span><span class="sxs-lookup"><span data-stu-id="789f2-105">Unless explicitly changed, all property values remain the same as they were on the previous bulk copy operation for a given instance.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="789f2-106">通常、バルク コピー操作を複数回実行する場合は、同じ <xref:System.Data.SqlClient.SqlBulkCopy> のインスタンスを使用する方が各操作ごとに別のインスタンスを使用するよりも効率的です。</span><span class="sxs-lookup"><span data-stu-id="789f2-106">Performing multiple bulk copy operations using the same instance of <xref:System.Data.SqlClient.SqlBulkCopy> is usually more efficient than using a separate instance for each operation.</span></span>  
  
 <span data-ttu-id="789f2-107">同じ <xref:System.Data.SqlClient.SqlBulkCopy> オブジェクトを使用してバルク コピー操作を複数回実行する場合は、コピー元またはコピー先の情報が各操作ごとに一致しているかまたは異なっているかどうかは制限されません。</span><span class="sxs-lookup"><span data-stu-id="789f2-107">If you perform several bulk copy operations using the same <xref:System.Data.SqlClient.SqlBulkCopy> object, there are no restrictions on whether source or target information is equal or different in each operation.</span></span> <span data-ttu-id="789f2-108">ただし、サーバーに書き込み処理を行うときは、列の関連情報を毎回正しく設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="789f2-108">However, you must ensure that column association information is properly set each time you write to the server.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="789f2-109">このサンプルは、「[一括コピーの例のセットアップ](bulk-copy-example-setup.md)」で説明されているように作業テーブルを作成しない限り、実行されません。</span><span class="sxs-lookup"><span data-stu-id="789f2-109">This sample will not run unless you have created the work tables as described in [Bulk Copy Example Setup](bulk-copy-example-setup.md).</span></span> <span data-ttu-id="789f2-110">このコードは、 **SqlBulkCopy**のみを使用する構文を示すために用意されています。</span><span class="sxs-lookup"><span data-stu-id="789f2-110">This code is provided to demonstrate the syntax for using **SqlBulkCopy** only.</span></span> <span data-ttu-id="789f2-111">コピー元およびコピー先のテーブルが同一の SQL Server インスタンス内に存在する場合、Transact-SQL `INSERT … SELECT` ステートメントを使用すれば簡単かつ高速にデータをコピーすることができます。</span><span class="sxs-lookup"><span data-stu-id="789f2-111">If the source and destination tables are located in the same SQL Server instance, it is easier and faster to use a Transact-SQL `INSERT … SELECT` statement to copy the data.</span></span>  
  
 [!code-csharp[DataWorks SqlBulkCopy.ColumnMappingOrdersDetails#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlBulkCopy.ColumnMappingOrdersDetails/CS/source.cs#1)]
 [!code-vb[DataWorks SqlBulkCopy.ColumnMappingOrdersDetails#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlBulkCopy.ColumnMappingOrdersDetails/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="789f2-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="789f2-112">See also</span></span>

- [<span data-ttu-id="789f2-113">SQL Server でのバルク コピー操作</span><span class="sxs-lookup"><span data-stu-id="789f2-113">Bulk Copy Operations in SQL Server</span></span>](bulk-copy-operations-in-sql-server.md)
- [<span data-ttu-id="789f2-114">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="789f2-114">ADO.NET Overview</span></span>](../ado-net-overview.md)
