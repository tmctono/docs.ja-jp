---
title: CLR ストアド プロシージャ
ms.date: 03/30/2017
ms.assetid: fd7eea9b-218a-4988-8c9a-8abcc6031c66
ms.openlocfilehash: 736020695ae40a8884057ddee8aac8abe6e8c1fd
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90554196"
---
# <a name="clr-stored-procedures"></a><span data-ttu-id="c4b40-102">CLR ストアド プロシージャ</span><span class="sxs-lookup"><span data-stu-id="c4b40-102">CLR Stored Procedures</span></span>
<span data-ttu-id="c4b40-103">ストアド プロシージャは、スカラー式では使用できないルーチンです。</span><span class="sxs-lookup"><span data-stu-id="c4b40-103">Stored procedures are routines that cannot be used in scalar expressions.</span></span> <span data-ttu-id="c4b40-104">ストアド プロシージャは、表形式の結果とメッセージをクライアントに返したり、データ定義言語 (DDL) ステートメントおよびデータ操作言語 (DML) ステートメントを呼び出したり、出力パラメーターを返したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="c4b40-104">They can return tabular results and messages to the client, invoke data definition language (DDL) and data manipulation language (DML) statements, and return output parameters.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c4b40-105">Microsoft Visual Basic では、出力パラメーターのサポートが Microsoft Visual C# と異なります。</span><span class="sxs-lookup"><span data-stu-id="c4b40-105">Microsoft Visual Basic does not support output parameters in the same way that Microsoft Visual C# does.</span></span> <span data-ttu-id="c4b40-106">パラメーターを参照によって渡す方式を指定し、次に示すように、\<Out()> 属性を適用して出力パラメーターを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4b40-106">You must specify to pass the parameter by reference and apply the \<Out()> attribute to represent an output parameter, as in the following:</span></span>  
  
```vb
Public Shared Sub ExecuteToClient( <Out()> ByRef number As Integer)  
```
  
<span data-ttu-id="c4b40-107">詳細については、使用している SQL Server のバージョンに対応する [SQL Server ドキュメント](/sql)のバージョンを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4b40-107">For more detailed information, see the version of [SQL Server documentation](/sql) for the version of SQL Server you're using.</span></span>
  
 <span data-ttu-id="c4b40-108">**SQL Server のドキュメント**</span><span class="sxs-lookup"><span data-stu-id="c4b40-108">**SQL Server documentation**</span></span>

1. <span data-ttu-id="c4b40-109">[CLR ストアド プロシージャ](/previous-versions/sql/sql-server-2008/ms131094(v=sql.100))</span><span class="sxs-lookup"><span data-stu-id="c4b40-109">[CLR Stored Procedures](/previous-versions/sql/sql-server-2008/ms131094(v=sql.100))</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4b40-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="c4b40-110">See also</span></span>

- <span data-ttu-id="c4b40-111">[マネージ コードでの SQL Server 2005 オブジェクトの作成](/previous-versions/visualstudio/visual-studio-2008/6s0s2at1(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="c4b40-111">[Creating SQL Server 2005 Objects In Managed Code](/previous-versions/visualstudio/visual-studio-2008/6s0s2at1(v=vs.90))</span></span>
- [<span data-ttu-id="c4b40-112">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="c4b40-112">ADO.NET Overview</span></span>](../ado-net-overview.md)
