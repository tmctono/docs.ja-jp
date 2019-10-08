---
title: '方法: 複数の結果形状が割り当てられたストアド プロシージャを使用する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c2b84dfe-7fec-489a-92de-45215cec4518
ms.openlocfilehash: 065e866ec5937c4af31c0b1563a7582cb4112eba
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2019
ms.locfileid: "72003274"
---
# <a name="how-to-use-stored-procedures-mapped-for-multiple-result-shapes"></a><span data-ttu-id="72ecb-102">方法: 複数の結果形状が割り当てられたストアド プロシージャを使用する</span><span class="sxs-lookup"><span data-stu-id="72ecb-102">How to: Use Stored Procedures Mapped for Multiple Result Shapes</span></span>
<span data-ttu-id="72ecb-103">複数の結果形状を返すことができるストアド プロシージャの場合、戻り値の型を単一の射影形状として厳密に型指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="72ecb-103">When a stored procedure can return multiple result shapes, the return type cannot be strongly typed to a single projection shape.</span></span> <span data-ttu-id="72ecb-104">@No__t-0 は可能なすべてのプロジェクション型を生成できますが、返される順序を知ることはできません。</span><span class="sxs-lookup"><span data-stu-id="72ecb-104">Although [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] can generate all possible projection types, it cannot know the order in which they will be returned.</span></span>  
  
 <span data-ttu-id="72ecb-105">このシナリオと対照的なのが、複数の結果形状をシーケンシャルに生成するストアド プロシージャです。</span><span class="sxs-lookup"><span data-stu-id="72ecb-105">Contrast this scenario with stored procedures that produce multiple result shapes sequentially.</span></span> <span data-ttu-id="72ecb-106">詳細については、「[方法 :シーケンシャルな結果図形 @ no__t-0 にマップされたストアドプロシージャを使用します。</span><span class="sxs-lookup"><span data-stu-id="72ecb-106">For more information, see [How to: Use Stored Procedures Mapped for Sequential Result Shapes](how-to-use-stored-procedures-mapped-for-sequential-result-shapes.md).</span></span>  
  
 <span data-ttu-id="72ecb-107">複数の結果型を返すストアド プロシージャには、プロシージャが返す可能性のある一連の型を示す <xref:System.Data.Linq.Mapping.ResultTypeAttribute> 属性を適用します。</span><span class="sxs-lookup"><span data-stu-id="72ecb-107">The <xref:System.Data.Linq.Mapping.ResultTypeAttribute> attribute is applied to stored procedures that return multiple result types to specify the set of types the procedure can return.</span></span>  
  
## <a name="example"></a><span data-ttu-id="72ecb-108">例</span><span class="sxs-lookup"><span data-stu-id="72ecb-108">Example</span></span>  
 <span data-ttu-id="72ecb-109">次の SQL コードの例では、結果形状は入力値 (`shape =1` または `shape = 2`) に応じて変わります。</span><span class="sxs-lookup"><span data-stu-id="72ecb-109">In the following SQL code example, the result shape depends on the input (`shape =1` or `shape = 2`).</span></span> <span data-ttu-id="72ecb-110">どちらの射影が先に返されるかはわかりません。</span><span class="sxs-lookup"><span data-stu-id="72ecb-110">You do not know which projection will be returned first.</span></span>  
  
``` sql
CREATE PROCEDURE VariableResultShapes(@shape int)  
AS  
if(@shape = 1)  
    select CustomerID, ContactTitle, CompanyName from customers  
else if(@shape = 2)  
    select OrderID, ShipName from orders  
```  
  
 [!code-csharp[DLinqSprox#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/northwind-sprox.cs#4)]
 [!code-vb[DLinqSprox#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/northwind-sprox.vb#4)]  
  
## <a name="example"></a><span data-ttu-id="72ecb-111">例</span><span class="sxs-lookup"><span data-stu-id="72ecb-111">Example</span></span>  
 <span data-ttu-id="72ecb-112">このストアド プロシージャを実行するには、次のようなコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="72ecb-112">You would use code similar to the following to execute this stored procedure.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="72ecb-113">ストアド プロシージャに対する知識に基づいて、<xref:System.Data.Linq.IMultipleResults.GetResult%2A> パターンを使用し、正しい型の列挙子を取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="72ecb-113">You must use the <xref:System.Data.Linq.IMultipleResults.GetResult%2A> pattern to obtain an enumerator of the correct type, based on your knowledge of the stored procedure.</span></span>  
  
 [!code-csharp[DLinqSprox#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/Program.cs#5)]
 [!code-vb[DLinqSprox#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/Module1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="72ecb-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="72ecb-114">See also</span></span>

- [<span data-ttu-id="72ecb-115">ストアド プロシージャ</span><span class="sxs-lookup"><span data-stu-id="72ecb-115">Stored Procedures</span></span>](stored-procedures.md)
