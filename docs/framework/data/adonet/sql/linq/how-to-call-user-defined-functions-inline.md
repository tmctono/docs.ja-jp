---
title: '方法: ユーザー定義関数をインラインで呼び出す'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f80d4327-b6a5-4aa8-a743-e95d09a2a02e
ms.openlocfilehash: 01ba9ab4359cbd124b2207c87d5dae904641911a
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2019
ms.locfileid: "72002989"
---
# <a name="how-to-call-user-defined-functions-inline"></a><span data-ttu-id="bf05f-102">方法: ユーザー定義関数をインラインで呼び出す</span><span class="sxs-lookup"><span data-stu-id="bf05f-102">How to: Call User-Defined Functions Inline</span></span>
<span data-ttu-id="bf05f-103">ユーザー定義関数はインラインで呼び出すことができますが、遅延実行のクエリに含まれる関数は、そのクエリが実行されるまで実行されません。</span><span class="sxs-lookup"><span data-stu-id="bf05f-103">Although you can call user-defined functions inline, functions that are included in a query whose execution is deferred are not executed until the query is executed.</span></span> <span data-ttu-id="bf05f-104">詳細については、「[LINQ クエリの概要 (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bf05f-104">For more information, see [Introduction to LINQ Queries (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>  
  
 <span data-ttu-id="bf05f-105">同じ関数をクエリの外部で呼び出すと、[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] によって、メソッド呼び出し式から単純なクエリが作成されます。</span><span class="sxs-lookup"><span data-stu-id="bf05f-105">When you call the same function outside a query, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] creates a simple query from the method call expression.</span></span> <span data-ttu-id="bf05f-106">この SQL 構文を次に示します (`@p0` パラメーターは渡される定数にバインドされます)。</span><span class="sxs-lookup"><span data-stu-id="bf05f-106">The following is the SQL syntax (the parameter `@p0` is bound to the constant passed in):</span></span>  
  
```sql  
SELECT dbo.ReverseCustName(@p0)  
```  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="bf05f-107">によって、次の結果が作成されます。</span><span class="sxs-lookup"><span data-stu-id="bf05f-107">creates the following:</span></span>  
  
 [!code-csharp[DLinqUDFS#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqUDFS/cs/Program.cs#4)]
 [!code-vb[DLinqUDFS#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqUDFS/vb/Module1.vb#4)]  
  
## <a name="example"></a><span data-ttu-id="bf05f-108">例</span><span class="sxs-lookup"><span data-stu-id="bf05f-108">Example</span></span>  
 <span data-ttu-id="bf05f-109">次の [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] クエリでは、生成されたユーザー定義関数メソッドのインライン呼び出し `ReverseCustName` を確認できます。</span><span class="sxs-lookup"><span data-stu-id="bf05f-109">In the following [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] query, you can see an inline call to the generated user-defined function method `ReverseCustName`.</span></span> <span data-ttu-id="bf05f-110">クエリは遅延実行されるので、この関数は即座には実行されません。</span><span class="sxs-lookup"><span data-stu-id="bf05f-110">The function is not executed immediately because query execution is deferred.</span></span> <span data-ttu-id="bf05f-111">このクエリ用に作成される SQL は、データベース内のユーザー定義関数の呼び出しに変換されます (クエリの後の SQL コードを参照してください)。</span><span class="sxs-lookup"><span data-stu-id="bf05f-111">The SQL built for this query translates to a call to the user-defined function in the database (see the SQL code following the query).</span></span>  
  
 [!code-csharp[DLinqUDFS#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqUDFS/cs/Program.cs#5)]
 [!code-vb[DLinqUDFS#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqUDFS/vb/Module1.vb#5)]  
  
```sql  
SELECT [t0].[ContactName],  
    dbo.ReverseCustName([t0].[ContactTitle]) AS [Title]  
FROM [Customers] AS [t0]  
```  
  
## <a name="see-also"></a><span data-ttu-id="bf05f-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="bf05f-112">See also</span></span>

- [<span data-ttu-id="bf05f-113">ユーザー定義関数</span><span class="sxs-lookup"><span data-stu-id="bf05f-113">User-Defined Functions</span></span>](user-defined-functions.md)
