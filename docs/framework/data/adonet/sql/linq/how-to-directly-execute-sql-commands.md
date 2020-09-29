---
title: '方法: SQL コマンドを直接実行する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 04671bb0-40c0-4465-86e5-77986f454661
ms.openlocfilehash: 6c72e683c37968ce18717b70ef6d647ca287bd20
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91147646"
---
# <a name="how-to-directly-execute-sql-commands"></a><span data-ttu-id="dc3bb-102">方法: SQL コマンドを直接実行する</span><span class="sxs-lookup"><span data-stu-id="dc3bb-102">How to: Directly Execute SQL Commands</span></span>

<span data-ttu-id="dc3bb-103"><xref:System.Data.Linq.DataContext> 接続を使用すると仮定して、オブジェクトを返さない SQL コマンドを実行するために <xref:System.Data.Linq.DataContext.ExecuteCommand%2A> を使用できます。</span><span class="sxs-lookup"><span data-stu-id="dc3bb-103">Assuming a <xref:System.Data.Linq.DataContext> connection, you can use <xref:System.Data.Linq.DataContext.ExecuteCommand%2A> to execute SQL commands that do not return objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dc3bb-104">例</span><span class="sxs-lookup"><span data-stu-id="dc3bb-104">Example</span></span>  

 <span data-ttu-id="dc3bb-105">SQL Server で UnitPrice の値を 1.00 増やす方法の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="dc3bb-105">The following example causes SQL Server to increase UnitPrice by 1.00.</span></span>  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#3)]
 [!code-vb[DLinqCommunicatingWithDatabase#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="dc3bb-106">関連項目</span><span class="sxs-lookup"><span data-stu-id="dc3bb-106">See also</span></span>

- [<span data-ttu-id="dc3bb-107">方法: SQL クエリを直接実行する</span><span class="sxs-lookup"><span data-stu-id="dc3bb-107">How to: Directly Execute SQL Queries</span></span>](how-to-directly-execute-sql-queries.md)
- [<span data-ttu-id="dc3bb-108">データベースとの通信</span><span class="sxs-lookup"><span data-stu-id="dc3bb-108">Communicating with the Database</span></span>](communicating-with-the-database.md)
