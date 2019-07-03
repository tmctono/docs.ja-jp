---
title: LINQ to Entities クエリ内の式
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d70b502f-6a15-4120-b4fe-500b173ad9cc
ms.openlocfilehash: 0b77fc4c2a7c7df6efc9f4d8ce4001c39250ab94
ms.sourcegitcommit: b5c59eaaf8bf48ef3ec259f228cb328d6d4c0ceb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2019
ms.locfileid: "67539898"
---
# <a name="expressions-in-linq-to-entities-queries"></a><span data-ttu-id="75895-102">LINQ to Entities クエリ内の式</span><span class="sxs-lookup"><span data-stu-id="75895-102">Expressions in LINQ to Entities Queries</span></span>
<span data-ttu-id="75895-103">式は、単一の値、オブジェクト、メソッド、または名前空間として評価されるコード フラグメントです。</span><span class="sxs-lookup"><span data-stu-id="75895-103">An expression is a fragment of code that can be evaluated to a single value, object, method, or namespace.</span></span> <span data-ttu-id="75895-104">式には、リテラル値、メソッド呼び出し、演算子とそのオペランド、または単純な名前を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="75895-104">Expressions can contain a literal value, a method call, an operator and its operands, or a simple name.</span></span> <span data-ttu-id="75895-105">単純な名前には、変数、型メンバー、メソッド パラメーター、名前空間、または型の名前を指定できます。</span><span class="sxs-lookup"><span data-stu-id="75895-105">Simple names can be the name of a variable, type member, method parameter, namespace or type.</span></span> <span data-ttu-id="75895-106">式では、他の式をパラメーターとして使用する演算子、またはパラメーターが他のメソッド呼び出しであるメソッド呼び出しを使用できます。</span><span class="sxs-lookup"><span data-stu-id="75895-106">Expressions can use operators that in turn use other expressions as parameters, or method calls whose parameters are in turn other method calls.</span></span> <span data-ttu-id="75895-107">したがって、単純な式だけでなく、非常に複雑な式も作成できます。</span><span class="sxs-lookup"><span data-stu-id="75895-107">Therefore, expressions can range from simple to very complex.</span></span>  
  
 <span data-ttu-id="75895-108">Linq to Entities クエリで式には何も内の型で許可されている、<xref:System.Linq.Expressions>名前空間、ラムダ式を含むです。</span><span class="sxs-lookup"><span data-stu-id="75895-108">In LINQ to Entities queries, expressions can contain anything allowed by the types within the <xref:System.Linq.Expressions> namespace, including lambda expressions.</span></span> <span data-ttu-id="75895-109">Linq to Entities クエリに使用できる式は、使用できる式のスーパー セットのクエリに、[!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="75895-109">The expressions that can be used in LINQ to Entities queries are a superset of the expressions that can be used to query the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)].</span></span>  <span data-ttu-id="75895-110">式に対するクエリの一部である、[!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)]でサポートされる操作に制限されて`ObjectQuery<T>`と基になるデータ ソース。</span><span class="sxs-lookup"><span data-stu-id="75895-110">Expressions that are part of queries against the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] are limited to operations supported by `ObjectQuery<T>` and the underlying data source.</span></span>  
  
 <span data-ttu-id="75895-111">次の例では、`Where` 句で使用される比較の式を示します。</span><span class="sxs-lookup"><span data-stu-id="75895-111">In the following example, the comparison in the `Where` clause is an expression:</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#WhereExpression](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#whereexpression)]
 [!code-vb[DP L2E Conceptual Examples#WhereExpression](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#whereexpression)]  
  
> [!NOTE]
>  <span data-ttu-id="75895-112">特殊な言語構造などC# `unchecked`、LINQ to Entities では意味を持つありません。</span><span class="sxs-lookup"><span data-stu-id="75895-112">Specific language constructs, such as C# `unchecked`, have no meaning in LINQ to Entities.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="75895-113">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="75895-113">In This Section</span></span>  
 [<span data-ttu-id="75895-114">定数式</span><span class="sxs-lookup"><span data-stu-id="75895-114">Constant Expressions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/constant-expressions.md)  
  
 [<span data-ttu-id="75895-115">比較式</span><span class="sxs-lookup"><span data-stu-id="75895-115">Comparison Expressions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/comparison-expressions.md)  
  
 [<span data-ttu-id="75895-116">NULL 比較</span><span class="sxs-lookup"><span data-stu-id="75895-116">Null Comparisons</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/null-comparisons.md)  
  
 [<span data-ttu-id="75895-117">初期化式</span><span class="sxs-lookup"><span data-stu-id="75895-117">Initialization Expressions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/initialization-expressions.md)  
  
 [<span data-ttu-id="75895-118">リレーションシップ、ナビゲーション プロパティ、および外部キー</span><span class="sxs-lookup"><span data-stu-id="75895-118">Relationships, navigation properties and foreign keys</span></span>](/ef/ef6/fundamentals/relationships)  
  
## <a name="see-also"></a><span data-ttu-id="75895-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="75895-119">See also</span></span>

- [<span data-ttu-id="75895-120">ADO.NET Entity Framework</span><span class="sxs-lookup"><span data-stu-id="75895-120">ADO.NET Entity Framework</span></span>](../../../../../../docs/framework/data/adonet/ef/index.md)
