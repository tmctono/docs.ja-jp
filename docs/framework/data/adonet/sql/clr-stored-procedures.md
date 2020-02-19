---
title: CLR ストアド プロシージャ
ms.date: 03/30/2017
ms.assetid: fd7eea9b-218a-4988-8c9a-8abcc6031c66
ms.openlocfilehash: ca0fd2d33f0ad56c96fb63530e6ba3f7f7890f81
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "77450363"
---
# <a name="clr-stored-procedures"></a><span data-ttu-id="401cc-102">CLR ストアド プロシージャ</span><span class="sxs-lookup"><span data-stu-id="401cc-102">CLR Stored Procedures</span></span>
<span data-ttu-id="401cc-103">ストアド プロシージャはスカラー式では使用できないルーチンです。</span><span class="sxs-lookup"><span data-stu-id="401cc-103">Stored procedures are routines that cannot be used in scalar expressions.</span></span> <span data-ttu-id="401cc-104">ストアド プロシージャは、表形式の結果とメッセージをクライアントに返したり、データ定義言語 (DDL) ステートメントおよびデータ操作言語 (DML) ステートメントを呼び出したり、出力パラメーターを返したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="401cc-104">They can return tabular results and messages to the client, invoke data definition language (DDL) and data manipulation language (DML) statements, and return output parameters.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="401cc-105">Microsoft Visual Basic では、出力パラメーターのサポートが Microsoft Visual C# と異なります。</span><span class="sxs-lookup"><span data-stu-id="401cc-105">Microsoft Visual Basic does not support output parameters in the same way that Microsoft Visual C# does.</span></span> <span data-ttu-id="401cc-106">次に示すように、パラメーターを参照によって渡し、\<Out () > 属性を適用して出力パラメーターを表す必要があります。</span><span class="sxs-lookup"><span data-stu-id="401cc-106">You must specify to pass the parameter by reference and apply the \<Out()> attribute to represent an output parameter, as in the following:</span></span>  
  
```vb
Public Shared Sub ExecuteToClient( <Out()> ByRef number As Integer)  
```
  
<span data-ttu-id="401cc-107">詳細については、使用している SQL Server バージョンの[SQL Server ドキュメント](/sql)のバージョンを参照してください。</span><span class="sxs-lookup"><span data-stu-id="401cc-107">For more detailed information, see the version of [SQL Server documentation](/sql) for the version of SQL Server you're using.</span></span>
  
 <span data-ttu-id="401cc-108">**SQL Server のドキュメント**</span><span class="sxs-lookup"><span data-stu-id="401cc-108">**SQL Server documentation**</span></span>

1. <span data-ttu-id="401cc-109">[CLR ストアド プロシージャ](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/ms131094(v=sql.100))</span><span class="sxs-lookup"><span data-stu-id="401cc-109">[CLR Stored Procedures](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/ms131094(v=sql.100))</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="401cc-110">参照</span><span class="sxs-lookup"><span data-stu-id="401cc-110">See also</span></span>

- <span data-ttu-id="401cc-111">[マネージコードでの SQL Server 2005 オブジェクトの作成](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/6s0s2at1(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="401cc-111">[Creating SQL Server 2005 Objects In Managed Code](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/6s0s2at1(v=vs.90))</span></span>
- [<span data-ttu-id="401cc-112">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="401cc-112">ADO.NET Overview</span></span>](../ado-net-overview.md)
