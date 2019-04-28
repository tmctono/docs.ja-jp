---
title: '方法: シーケンシャルな結果形状が割り当てられたストアド プロシージャを使用する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a73530de-5a4e-4d9c-8d66-abb19c225b11
ms.openlocfilehash: e51ebacb3f6be849f7b871f2d12db3ea7476b117
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61877072"
---
# <a name="how-to-use-stored-procedures-mapped-for-sequential-result-shapes"></a><span data-ttu-id="b923c-102">方法: シーケンシャルな結果形状が割り当てられたストアド プロシージャを使用する</span><span class="sxs-lookup"><span data-stu-id="b923c-102">How to: Use Stored Procedures Mapped for Sequential Result Shapes</span></span>
<span data-ttu-id="b923c-103">この種類のストアド プロシージャでは、複数の結果形状が生成されますが、どの順序で結果が返されるかがわかります。</span><span class="sxs-lookup"><span data-stu-id="b923c-103">This kind of stored procedure can generate more than one result shape, but you know in what order the results are returned.</span></span> <span data-ttu-id="b923c-104">このシナリオは、返される結果のシーケンスがわからないシナリオと対照的です。</span><span class="sxs-lookup"><span data-stu-id="b923c-104">Contrast this scenario with the scenario where you do not know the sequence of the returns.</span></span> <span data-ttu-id="b923c-105">詳細については、「[方法 :複数の結果形状が割り当てられたストアド プロシージャを使用して、](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-stored-procedures-mapped-for-multiple-result-shapes.md)します。</span><span class="sxs-lookup"><span data-stu-id="b923c-105">For more information, see [How to: Use Stored Procedures Mapped for Multiple Result Shapes](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-stored-procedures-mapped-for-multiple-result-shapes.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b923c-106">例</span><span class="sxs-lookup"><span data-stu-id="b923c-106">Example</span></span>  
 <span data-ttu-id="b923c-107">次は、複数の結果形状をシーケンシャルに返すストアド プロシージャの T-SQL です。</span><span class="sxs-lookup"><span data-stu-id="b923c-107">Here is the T-SQL of a stored procedure that returns multiple result shapes sequentially:</span></span>  
  
```  
CREATE PROCEDURE MultipleResultTypesSequentially  
AS  
select * from products  
select * from customers  
```  
  
 [!code-csharp[DLinqSprox#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/northwind-sprox.cs#6)]
 [!code-vb[DLinqSprox#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/northwind-sprox.vb#6)]  
  
## <a name="example"></a><span data-ttu-id="b923c-108">例</span><span class="sxs-lookup"><span data-stu-id="b923c-108">Example</span></span>  
 <span data-ttu-id="b923c-109">このストアド プロシージャを実行するには、次のようなコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="b923c-109">You would use code similar to the following to execute this stored procedure.</span></span>  
  
 [!code-csharp[DLinqSprox#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/Program.cs#7)]
 [!code-vb[DLinqSprox#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/Module1.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="b923c-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="b923c-110">See also</span></span>

- [<span data-ttu-id="b923c-111">ストアド プロシージャ</span><span class="sxs-lookup"><span data-stu-id="b923c-111">Stored Procedures</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)
