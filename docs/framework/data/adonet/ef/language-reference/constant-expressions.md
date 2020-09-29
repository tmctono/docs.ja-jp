---
title: 定数式
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9d98a7be-b110-4edb-8eba-bed10f250b6d
ms.openlocfilehash: 163f73a7682d444214caa213751cb35f8f0e8743
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91153041"
---
# <a name="constant-expressions"></a><span data-ttu-id="78479-102">定数式</span><span class="sxs-lookup"><span data-stu-id="78479-102">Constant Expressions</span></span>

<span data-ttu-id="78479-103">定数式は、定数値で構成されています。</span><span class="sxs-lookup"><span data-stu-id="78479-103">A constant expression consists of a constant value.</span></span> <span data-ttu-id="78479-104">定数値は、クライアント側で変換されることなく、コマンド ツリーの定数式に直接変換されます。</span><span class="sxs-lookup"><span data-stu-id="78479-104">Constant values are directly converted to constant command tree expressions, without any translation on the client.</span></span> <span data-ttu-id="78479-105">これには、定数値になる式が含まれます。</span><span class="sxs-lookup"><span data-stu-id="78479-105">This includes expressions that result in a constant value.</span></span> <span data-ttu-id="78479-106">したがって、定数にかかわるすべての式でデータ ソースの動作が、予期したとおりになります。</span><span class="sxs-lookup"><span data-stu-id="78479-106">Therefore, data source behavior should be expected for all expressions involving constants.</span></span> <span data-ttu-id="78479-107">これは CLR の動作とは異なる結果となります。</span><span class="sxs-lookup"><span data-stu-id="78479-107">This can result in behavior that differs from CLR behavior.</span></span>  
  
 <span data-ttu-id="78479-108">次の例では、サーバーで評価される定数式を示します。</span><span class="sxs-lookup"><span data-stu-id="78479-108">The following example shows a constant expression that is evaluated on the server.</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#ConstantExpression](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#constantexpression)]
 [!code-vb[DP L2E Conceptual Examples#ConstantExpression](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#constantexpression)]  
  
 <span data-ttu-id="78479-109">LINQ to Entities では、ユーザー クラスを定数として使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="78479-109">LINQ to Entities does not support using a user class as a constant.</span></span> <span data-ttu-id="78479-110">ただし、ユーザー クラスのプロパティ参照は定数と見なされます。そのため、コマンド ツリーの定数式に変換され、データ ソースで実行されます。</span><span class="sxs-lookup"><span data-stu-id="78479-110">However, a property reference on a user class is considered a constant, and will be converted to a command tree constant expression and executed on the data source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78479-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="78479-111">See also</span></span>

- [<span data-ttu-id="78479-112">LINQ to Entities クエリ内の式</span><span class="sxs-lookup"><span data-stu-id="78479-112">Expressions in LINQ to Entities Queries</span></span>](expressions-in-linq-to-entities-queries.md)
