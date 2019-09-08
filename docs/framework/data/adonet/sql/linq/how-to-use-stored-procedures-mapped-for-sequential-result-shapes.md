---
title: '方法: シーケンシャルな結果形状が割り当てられたストアド プロシージャを使用する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a73530de-5a4e-4d9c-8d66-abb19c225b11
ms.openlocfilehash: bae10e823a274304f21292cf55947a4d4eaccc10
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781458"
---
# <a name="how-to-use-stored-procedures-mapped-for-sequential-result-shapes"></a><span data-ttu-id="a8211-102">方法: シーケンシャルな結果形状が割り当てられたストアド プロシージャを使用する</span><span class="sxs-lookup"><span data-stu-id="a8211-102">How to: Use Stored Procedures Mapped for Sequential Result Shapes</span></span>
<span data-ttu-id="a8211-103">この種類のストアド プロシージャでは、複数の結果形状が生成されますが、どの順序で結果が返されるかがわかります。</span><span class="sxs-lookup"><span data-stu-id="a8211-103">This kind of stored procedure can generate more than one result shape, but you know in what order the results are returned.</span></span> <span data-ttu-id="a8211-104">このシナリオは、返される結果のシーケンスがわからないシナリオと対照的です。</span><span class="sxs-lookup"><span data-stu-id="a8211-104">Contrast this scenario with the scenario where you do not know the sequence of the returns.</span></span> <span data-ttu-id="a8211-105">詳細については、「[方法 :複数の結果形状](how-to-use-stored-procedures-mapped-for-multiple-result-shapes.md)にマップされたストアドプロシージャを使用します。</span><span class="sxs-lookup"><span data-stu-id="a8211-105">For more information, see [How to: Use Stored Procedures Mapped for Multiple Result Shapes](how-to-use-stored-procedures-mapped-for-multiple-result-shapes.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a8211-106">例</span><span class="sxs-lookup"><span data-stu-id="a8211-106">Example</span></span>  
 <span data-ttu-id="a8211-107">次は、複数の結果形状をシーケンシャルに返すストアド プロシージャの T-SQL です。</span><span class="sxs-lookup"><span data-stu-id="a8211-107">Here is the T-SQL of a stored procedure that returns multiple result shapes sequentially:</span></span>  
  
```  
CREATE PROCEDURE MultipleResultTypesSequentially  
AS  
select * from products  
select * from customers  
```  
  
 [!code-csharp[DLinqSprox#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/northwind-sprox.cs#6)]
 [!code-vb[DLinqSprox#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/northwind-sprox.vb#6)]  
  
## <a name="example"></a><span data-ttu-id="a8211-108">例</span><span class="sxs-lookup"><span data-stu-id="a8211-108">Example</span></span>  
 <span data-ttu-id="a8211-109">このストアド プロシージャを実行するには、次のようなコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="a8211-109">You would use code similar to the following to execute this stored procedure.</span></span>  
  
 [!code-csharp[DLinqSprox#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/Program.cs#7)]
 [!code-vb[DLinqSprox#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/Module1.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="a8211-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="a8211-110">See also</span></span>

- [<span data-ttu-id="a8211-111">ストアド プロシージャ</span><span class="sxs-lookup"><span data-stu-id="a8211-111">Stored Procedures</span></span>](stored-procedures.md)
