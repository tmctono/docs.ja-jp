---
title: '方法: テーブル値のユーザー定義関数を使用する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5a4ae2b4-3290-4aa1-bc95-fc70c51b54cf
ms.openlocfilehash: c4b5290e4f1aa69c7f55951d526ccb303a5a95ec
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2019
ms.locfileid: "72003183"
---
# <a name="how-to-use-table-valued-user-defined-functions"></a><span data-ttu-id="7acc2-102">方法: テーブル値のユーザー定義関数を使用する</span><span class="sxs-lookup"><span data-stu-id="7acc2-102">How to: Use Table-Valued User-Defined Functions</span></span>
<span data-ttu-id="7acc2-103">テーブル値関数は、単一の行セットを返します (複数の結果形状を返すことができるストアド プロシージャとは異なります)。</span><span class="sxs-lookup"><span data-stu-id="7acc2-103">A table-valued function returns a single rowset (unlike stored procedures, which can return multiple result shapes).</span></span> <span data-ttu-id="7acc2-104">テーブル値関数の戻り値の型は `Table` であるため、テーブルを使用できる SQL の任意の場所でテーブル値関数を使用できます。</span><span class="sxs-lookup"><span data-stu-id="7acc2-104">Because the return type of a table-valued function is `Table`, you can use a table-valued function anywhere in SQL that you can use a table.</span></span> <span data-ttu-id="7acc2-105">テーブル値関数をテーブルのように扱うこともできます。</span><span class="sxs-lookup"><span data-stu-id="7acc2-105">You can also treat the table-valued function just as you would a table.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7acc2-106">例</span><span class="sxs-lookup"><span data-stu-id="7acc2-106">Example</span></span>  
 <span data-ttu-id="7acc2-107">次の SQL 関数は、`TABLE` を返すことを明示的に示しています。</span><span class="sxs-lookup"><span data-stu-id="7acc2-107">The following SQL function explicitly states that it returns a `TABLE`.</span></span> <span data-ttu-id="7acc2-108">そのため、返される行セットの構造が暗黙的に定義されます。</span><span class="sxs-lookup"><span data-stu-id="7acc2-108">Therefore, the returned rowset structure is implicitly defined.</span></span>  
  
```sql
CREATE FUNCTION ProductsCostingMoreThan(@cost money)  
RETURNS TABLE  
AS  
RETURN  
    SELECT ProductID, UnitPrice  
    FROM Products  
    WHERE UnitPrice > @cost  
```  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="7acc2-109">は、関数を次のように割り当てます。</span><span class="sxs-lookup"><span data-stu-id="7acc2-109">maps the function as follows:</span></span>  
  
 [!code-csharp[DLinqUDFS#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqUDFS/cs/northwind-tfunc.cs#1)]
 [!code-vb[DLinqUDFS#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqUDFS/vb/northwind-tfunc.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="7acc2-110">例</span><span class="sxs-lookup"><span data-stu-id="7acc2-110">Example</span></span>  
 <span data-ttu-id="7acc2-111">次の SQL コードは、関数が返すテーブルに結合できることを示しており、それ以外の場合は、他のテーブルと同じように扱います。</span><span class="sxs-lookup"><span data-stu-id="7acc2-111">The following SQL code shows that you can join to the table that the function returns and otherwise treat it as you would any other table:</span></span>  
  
```sql
SELECT p2.ProductName, p1.UnitPrice  
FROM dbo.ProductsCostingMoreThan(80.50)  
AS p1 INNER JOIN Products AS p2 ON p1.ProductID = p2.ProductID  
```  
  
 <span data-ttu-id="7acc2-112">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] では、クエリは次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="7acc2-112">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the query would be rendered as follows:</span></span>  
  
 [!code-csharp[DLinqUDFS#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqUDFS/cs/Program.cs#2)]
 [!code-vb[DLinqUDFS#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqUDFS/vb/Module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="7acc2-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="7acc2-113">See also</span></span>

- [<span data-ttu-id="7acc2-114">ユーザー定義関数</span><span class="sxs-lookup"><span data-stu-id="7acc2-114">User-Defined Functions</span></span>](user-defined-functions.md)
