---
title: Oracle 分散トランザクション
ms.date: 03/30/2017
ms.assetid: c340ca81-ef79-402f-b204-c5156b890fe5
ms.openlocfilehash: a21134c3283d3d9d8d7660eecaaf74d60ecf6662
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166522"
---
# <a name="oracle-distributed-transactions"></a>Oracle 分散トランザクション

<xref:System.Data.OracleClient.OracleConnection> オブジェクトはトランザクションがアクティブであると判断した場合、既存の分散トランザクションに自動的に参加します。 自動トランザクション参加は、接続が開かれた場合または接続プールから取得された場合に行われます。 既存のトランザクションへの自動参加を無効にするには、  
  
```csharp  
Enlist=false  
```  
  
 を <xref:System.Data.OracleClient.OracleConnection> の接続文字列パラメーターとして指定します。  
  
## <a name="see-also"></a>関連項目

- [Oracle および ADO.NET](oracle-and-adonet.md)
- [ADO.NET の概要](ado-net-overview.md)
