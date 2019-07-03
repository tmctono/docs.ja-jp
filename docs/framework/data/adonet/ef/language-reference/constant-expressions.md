---
title: 定数式
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9d98a7be-b110-4edb-8eba-bed10f250b6d
ms.openlocfilehash: cc3a214a2faa06c79ee0794b0158381bff0c4b0b
ms.sourcegitcommit: b5c59eaaf8bf48ef3ec259f228cb328d6d4c0ceb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2019
ms.locfileid: "67539885"
---
# <a name="constant-expressions"></a><span data-ttu-id="f4b8e-102">定数式</span><span class="sxs-lookup"><span data-stu-id="f4b8e-102">Constant Expressions</span></span>
<span data-ttu-id="f4b8e-103">定数式は、定数値で構成されています。</span><span class="sxs-lookup"><span data-stu-id="f4b8e-103">A constant expression consists of a constant value.</span></span> <span data-ttu-id="f4b8e-104">定数値は、クライアント側で変換されることなく、コマンド ツリーの定数式に直接変換されます。</span><span class="sxs-lookup"><span data-stu-id="f4b8e-104">Constant values are directly converted to constant command tree expressions, without any translation on the client.</span></span> <span data-ttu-id="f4b8e-105">これには、定数値になる式が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f4b8e-105">This includes expressions that result in a constant value.</span></span> <span data-ttu-id="f4b8e-106">したがって、定数にかかわるすべての式でデータ ソースの動作が、予期したとおりになります。</span><span class="sxs-lookup"><span data-stu-id="f4b8e-106">Therefore, data source behavior should be expected for all expressions involving constants.</span></span> <span data-ttu-id="f4b8e-107">これは CLR の動作とは異なる結果となります。</span><span class="sxs-lookup"><span data-stu-id="f4b8e-107">This can result in behavior that differs from CLR behavior.</span></span>  
  
 <span data-ttu-id="f4b8e-108">次の例では、サーバーで評価される定数式を示します。</span><span class="sxs-lookup"><span data-stu-id="f4b8e-108">The following example shows a constant expression that is evaluated on the server.</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#ConstantExpression](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#constantexpression)]
 [!code-vb[DP L2E Conceptual Examples#ConstantExpression](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#constantexpression)]  
  
 <span data-ttu-id="f4b8e-109">LINQ to Entities では、ユーザー クラスを定数として使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="f4b8e-109">LINQ to Entities does not support using a user class as a constant.</span></span> <span data-ttu-id="f4b8e-110">ただし、ユーザー クラスのプロパティ参照は定数と見なされます。そのため、コマンド ツリーの定数式に変換され、データ ソースで実行されます。</span><span class="sxs-lookup"><span data-stu-id="f4b8e-110">However, a property reference on a user class is considered a constant, and will be converted to a command tree constant expression and executed on the data source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4b8e-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="f4b8e-111">See also</span></span>

- [<span data-ttu-id="f4b8e-112">LINQ to Entities クエリ内の式</span><span class="sxs-lookup"><span data-stu-id="f4b8e-112">Expressions in LINQ to Entities Queries</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/expressions-in-linq-to-entities-queries.md)
