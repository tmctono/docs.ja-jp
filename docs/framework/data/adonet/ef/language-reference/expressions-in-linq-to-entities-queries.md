---
title: LINQ to Entities クエリ内の式
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d70b502f-6a15-4120-b4fe-500b173ad9cc
ms.openlocfilehash: 383339241194c56d0c3178f538f2ac08b2f1b437
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69950389"
---
# <a name="expressions-in-linq-to-entities-queries"></a><span data-ttu-id="4903c-102">LINQ to Entities クエリ内の式</span><span class="sxs-lookup"><span data-stu-id="4903c-102">Expressions in LINQ to Entities Queries</span></span>
<span data-ttu-id="4903c-103">式は、単一の値、オブジェクト、メソッド、または名前空間として評価されるコード フラグメントです。</span><span class="sxs-lookup"><span data-stu-id="4903c-103">An expression is a fragment of code that can be evaluated to a single value, object, method, or namespace.</span></span> <span data-ttu-id="4903c-104">式には、リテラル値、メソッド呼び出し、演算子とそのオペランド、または単純な名前を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="4903c-104">Expressions can contain a literal value, a method call, an operator and its operands, or a simple name.</span></span> <span data-ttu-id="4903c-105">単純な名前には、変数、型メンバー、メソッド パラメーター、名前空間、または型の名前を指定できます。</span><span class="sxs-lookup"><span data-stu-id="4903c-105">Simple names can be the name of a variable, type member, method parameter, namespace or type.</span></span> <span data-ttu-id="4903c-106">式では、他の式をパラメーターとして使用する演算子、またはパラメーターが他のメソッド呼び出しであるメソッド呼び出しを使用できます。</span><span class="sxs-lookup"><span data-stu-id="4903c-106">Expressions can use operators that in turn use other expressions as parameters, or method calls whose parameters are in turn other method calls.</span></span> <span data-ttu-id="4903c-107">したがって、単純な式だけでなく、非常に複雑な式も作成できます。</span><span class="sxs-lookup"><span data-stu-id="4903c-107">Therefore, expressions can range from simple to very complex.</span></span>  
  
 <span data-ttu-id="4903c-108">LINQ to Entities のクエリでは、ラムダ式を含む、 <xref:System.Linq.Expressions>名前空間内の型で許可されているものを式に含めることができます。</span><span class="sxs-lookup"><span data-stu-id="4903c-108">In LINQ to Entities queries, expressions can contain anything allowed by the types within the <xref:System.Linq.Expressions> namespace, including lambda expressions.</span></span> <span data-ttu-id="4903c-109">LINQ to Entities クエリで使用できる式は、 [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)]にクエリを実行するために使用できる式のスーパーセットです。</span><span class="sxs-lookup"><span data-stu-id="4903c-109">The expressions that can be used in LINQ to Entities queries are a superset of the expressions that can be used to query the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)].</span></span>  <span data-ttu-id="4903c-110">に対する[!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)]クエリの一部である式は、および基になる`ObjectQuery<T>`データソースでサポートされている操作に制限されます。</span><span class="sxs-lookup"><span data-stu-id="4903c-110">Expressions that are part of queries against the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] are limited to operations supported by `ObjectQuery<T>` and the underlying data source.</span></span>  
  
 <span data-ttu-id="4903c-111">次の例では、`Where` 句で使用される比較の式を示します。</span><span class="sxs-lookup"><span data-stu-id="4903c-111">In the following example, the comparison in the `Where` clause is an expression:</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#WhereExpression](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#whereexpression)]
 [!code-vb[DP L2E Conceptual Examples#WhereExpression](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#whereexpression)]  
  
> [!NOTE]
> <span data-ttu-id="4903c-112">などの特定の言語構成C# `unchecked`要素は、LINQ to Entities では意味がありません。</span><span class="sxs-lookup"><span data-stu-id="4903c-112">Specific language constructs, such as C# `unchecked`, have no meaning in LINQ to Entities.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4903c-113">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="4903c-113">In This Section</span></span>  
 [<span data-ttu-id="4903c-114">定数式</span><span class="sxs-lookup"><span data-stu-id="4903c-114">Constant Expressions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/constant-expressions.md)  
  
 [<span data-ttu-id="4903c-115">比較式</span><span class="sxs-lookup"><span data-stu-id="4903c-115">Comparison Expressions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/comparison-expressions.md)  
  
 [<span data-ttu-id="4903c-116">NULL 比較</span><span class="sxs-lookup"><span data-stu-id="4903c-116">Null Comparisons</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/null-comparisons.md)  
  
 [<span data-ttu-id="4903c-117">初期化式</span><span class="sxs-lookup"><span data-stu-id="4903c-117">Initialization Expressions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/initialization-expressions.md)  
  
 [<span data-ttu-id="4903c-118">リレーションシップ、ナビゲーションプロパティ、外部キー</span><span class="sxs-lookup"><span data-stu-id="4903c-118">Relationships, navigation properties and foreign keys</span></span>](/ef/ef6/fundamentals/relationships)  
  
## <a name="see-also"></a><span data-ttu-id="4903c-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="4903c-119">See also</span></span>

- [<span data-ttu-id="4903c-120">ADO.NET Entity Framework</span><span class="sxs-lookup"><span data-stu-id="4903c-120">ADO.NET Entity Framework</span></span>](../../../../../../docs/framework/data/adonet/ef/index.md)
