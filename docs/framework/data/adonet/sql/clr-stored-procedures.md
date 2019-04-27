---
title: CLR ストアド プロシージャ
ms.date: 03/30/2017
ms.assetid: fd7eea9b-218a-4988-8c9a-8abcc6031c66
ms.openlocfilehash: 9b31d93c1ebc0af9aa8e41b3a4c328af62da7e23
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61878332"
---
# <a name="clr-stored-procedures"></a><span data-ttu-id="389d3-102">CLR ストアド プロシージャ</span><span class="sxs-lookup"><span data-stu-id="389d3-102">CLR Stored Procedures</span></span>
<span data-ttu-id="389d3-103">ストアド プロシージャは、スカラー式では使用できないルーチンです。</span><span class="sxs-lookup"><span data-stu-id="389d3-103">Stored procedures are routines that cannot be used in scalar expressions.</span></span> <span data-ttu-id="389d3-104">ストアド プロシージャは、表形式の結果とメッセージをクライアントに返したり、データ定義言語 (DDL) ステートメントおよびデータ操作言語 (DML) ステートメントを呼び出したり、出力パラメーターを返したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="389d3-104">They can return tabular results and messages to the client, invoke data definition language (DDL) and data manipulation language (DML) statements, and return output parameters.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="389d3-105">Microsoft Visual Basic では、出力パラメーターのサポートが Microsoft Visual C# と異なります。</span><span class="sxs-lookup"><span data-stu-id="389d3-105">Microsoft Visual Basic does not support output parameters in the same way that Microsoft Visual C# does.</span></span> <span data-ttu-id="389d3-106">参照渡しでパラメーターを渡すし、適用を指定する必要があります、 \<Out() > 属性を次のように、出力パラメーターを表します。</span><span class="sxs-lookup"><span data-stu-id="389d3-106">You must specify to pass the parameter by reference and apply the \<Out()> attribute to represent an output parameter, as in the following:</span></span>  
  
```vb
Public Shared Sub ExecuteToClient( <Out()> ByRef number As Integer)  
```
  
<span data-ttu-id="389d3-107">詳細については、のバージョンを参照してください。 [SQL Server のドキュメント](/sql)を使用する SQL Server のバージョン。</span><span class="sxs-lookup"><span data-stu-id="389d3-107">For more detailed information, see the version of [SQL Server documentation](/sql) for the version of SQL Server you're using.</span></span>
  
 <span data-ttu-id="389d3-108">**SQL Server のドキュメント**</span><span class="sxs-lookup"><span data-stu-id="389d3-108">**SQL Server documentation**</span></span>

1. [<span data-ttu-id="389d3-109">CLR ストアド プロシージャ</span><span class="sxs-lookup"><span data-stu-id="389d3-109">CLR Stored Procedures</span></span>](https://go.microsoft.com/fwlink/?LinkId=115400)  
  
## <a name="see-also"></a><span data-ttu-id="389d3-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="389d3-110">See also</span></span>

- <span data-ttu-id="389d3-111">[マネージ コードで SQL Server 2005 のオブジェクトを作成します。](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/6s0s2at1(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="389d3-111">[Creating SQL Server 2005 Objects In Managed Code](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/6s0s2at1(v=vs.90))</span></span>
- [<span data-ttu-id="389d3-112">ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター</span><span class="sxs-lookup"><span data-stu-id="389d3-112">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
