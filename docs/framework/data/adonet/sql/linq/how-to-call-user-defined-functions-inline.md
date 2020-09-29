---
title: '方法: ユーザー定義関数をインラインで呼び出す'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f80d4327-b6a5-4aa8-a743-e95d09a2a02e
ms.openlocfilehash: 24b23c436fd7d4d5f3fdd0c364c0bdaf6feb8d1b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91161348"
---
# <a name="how-to-call-user-defined-functions-inline"></a>方法: ユーザー定義関数をインラインで呼び出す

ユーザー定義関数はインラインで呼び出すことができますが、遅延実行のクエリに含まれる関数は、そのクエリが実行されるまで実行されません。 詳細については、「[LINQ クエリの概要 (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)」を参照してください。  
  
 同じ関数をクエリの外部で呼び出すと、[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] によって、メソッド呼び出し式から単純なクエリが作成されます。 この SQL 構文を次に示します (`@p0` パラメーターは渡される定数にバインドされます)。  
  
```sql  
SELECT dbo.ReverseCustName(@p0)  
```  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] によって、次の結果が作成されます。  
  
 [!code-csharp[DLinqUDFS#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqUDFS/cs/Program.cs#4)]
 [!code-vb[DLinqUDFS#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqUDFS/vb/Module1.vb#4)]  
  
## <a name="example"></a>例  

 次の [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] のクエリでは、生成されたユーザー定義関数メソッド `ReverseCustName` のインライン呼び出しを確認できます。 クエリは遅延実行されるので、この関数は即座には実行されません。 このクエリ用に作成される SQL は、データベース内のユーザー定義関数の呼び出しに変換されます (クエリの後の SQL コードを参照してください)。  
  
 [!code-csharp[DLinqUDFS#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqUDFS/cs/Program.cs#5)]
 [!code-vb[DLinqUDFS#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqUDFS/vb/Module1.vb#5)]  
  
```sql  
SELECT [t0].[ContactName],  
    dbo.ReverseCustName([t0].[ContactTitle]) AS [Title]  
FROM [Customers] AS [t0]  
```  
  
## <a name="see-also"></a>関連項目

- [ユーザー定義関数](user-defined-functions.md)
