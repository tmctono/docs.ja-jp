---
title: CLR ストアド プロシージャ
ms.date: 03/30/2017
ms.assetid: fd7eea9b-218a-4988-8c9a-8abcc6031c66
ms.openlocfilehash: aa14c96ed226ac80a9613d3e229f35dbf5085f3b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173615"
---
# <a name="clr-stored-procedures"></a>CLR ストアド プロシージャ

ストアド プロシージャは、スカラー式では使用できないルーチンです。 ストアド プロシージャは、表形式の結果とメッセージをクライアントに返したり、データ定義言語 (DDL) ステートメントおよびデータ操作言語 (DML) ステートメントを呼び出したり、出力パラメーターを返したりすることができます。  
  
> [!NOTE]
> Microsoft Visual Basic では、出力パラメーターのサポートが Microsoft Visual C# と異なります。 パラメーターを参照によって渡す方式を指定し、次に示すように、\<Out()> 属性を適用して出力パラメーターを指定する必要があります。  
  
```vb
Public Shared Sub ExecuteToClient( <Out()> ByRef number As Integer)  
```
  
詳細については、使用している SQL Server のバージョンに対応する [SQL Server ドキュメント](/sql)のバージョンを参照してください。
  
 **SQL Server のドキュメント**

1. [CLR ストアド プロシージャ](/previous-versions/sql/sql-server-2008/ms131094(v=sql.100))  
  
## <a name="see-also"></a>関連項目

- [マネージ コードでの SQL Server 2005 オブジェクトの作成](/previous-versions/visualstudio/visual-studio-2008/6s0s2at1(v=vs.90))
- [ADO.NET の概要](../ado-net-overview.md)
