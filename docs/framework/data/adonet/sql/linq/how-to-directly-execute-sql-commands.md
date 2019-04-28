---
title: '方法: SQL コマンドを直接実行する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 04671bb0-40c0-4465-86e5-77986f454661
ms.openlocfilehash: eeac6272f176ac8e780b72b0076d032ad9e8f108
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61903228"
---
# <a name="how-to-directly-execute-sql-commands"></a><span data-ttu-id="75757-102">方法: SQL コマンドを直接実行する</span><span class="sxs-lookup"><span data-stu-id="75757-102">How to: Directly Execute SQL Commands</span></span>
<span data-ttu-id="75757-103"><xref:System.Data.Linq.DataContext> 接続を使用すると仮定して、オブジェクトを返さない SQL コマンドを実行するために <xref:System.Data.Linq.DataContext.ExecuteCommand%2A> を使用できます。</span><span class="sxs-lookup"><span data-stu-id="75757-103">Assuming a <xref:System.Data.Linq.DataContext> connection, you can use <xref:System.Data.Linq.DataContext.ExecuteCommand%2A> to execute SQL commands that do not return objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="75757-104">例</span><span class="sxs-lookup"><span data-stu-id="75757-104">Example</span></span>  
 <span data-ttu-id="75757-105">SQL Server で UnitPrice の値を 1.00 増やす方法の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="75757-105">The following example causes SQL Server to increase UnitPrice by 1.00.</span></span>  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#3)]
 [!code-vb[DLinqCommunicatingWithDatabase#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="75757-106">関連項目</span><span class="sxs-lookup"><span data-stu-id="75757-106">See also</span></span>

- [<span data-ttu-id="75757-107">方法: SQL クエリを直接実行します。</span><span class="sxs-lookup"><span data-stu-id="75757-107">How to: Directly Execute SQL Queries</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-directly-execute-sql-queries.md)
- [<span data-ttu-id="75757-108">データベースとの通信</span><span class="sxs-lookup"><span data-stu-id="75757-108">Communicating with the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/communicating-with-the-database.md)
