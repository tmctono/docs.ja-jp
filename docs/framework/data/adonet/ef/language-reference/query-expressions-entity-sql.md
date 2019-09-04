---
title: クエリ式 (Entity SQL)
ms.date: 03/30/2017
ms.assetid: c36f327b-e230-48d4-bbd5-78dc6478c447
ms.openlocfilehash: 4428286890f41573a02daf31a4593d0c8f9ad34b
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70249272"
---
# <a name="query-expressions-entity-sql"></a><span data-ttu-id="e2418-102">クエリ式 (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="e2418-102">Query Expressions (Entity SQL)</span></span>
<span data-ttu-id="e2418-103">クエリ式とは、さまざまなクエリ演算子を組み合わせて 1 つの構文にしたものです。</span><span class="sxs-lookup"><span data-stu-id="e2418-103">A query expression combines many different query operators into a single syntax.</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="e2418-104">には、[リテラル](literals-entity-sql.md)、[パラメーター](parameters-entity-sql.md)、[変数](variables-entity-sql.md)、演算子、[関数](functions-entity-sql.md)、set 演算子など、さまざまな種類の式が用意されています。</span><span class="sxs-lookup"><span data-stu-id="e2418-104">provides various kinds of expressions, including the following: [literals](literals-entity-sql.md), [parameters](parameters-entity-sql.md), [variables](variables-entity-sql.md), operators, [functions](functions-entity-sql.md), set operators, and so on.</span></span> <span data-ttu-id="e2418-105">詳細については、「 [Entity SQL リファレンス](entity-sql-reference.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2418-105">For more information, see [Entity SQL Reference](entity-sql-reference.md).</span></span>  
  
## <a name="clauses"></a><span data-ttu-id="e2418-106">句</span><span class="sxs-lookup"><span data-stu-id="e2418-106">Clauses</span></span>  
 <span data-ttu-id="e2418-107">クエリ式は、オブジェクトのコレクションに連続した操作を適用する一連の句で構成されます。</span><span class="sxs-lookup"><span data-stu-id="e2418-107">A query expression is composed of a series of clauses that apply successive operations to a collection of objects.</span></span> <span data-ttu-id="e2418-108">これらは、標準の SQL select ステートメントと同じ句に基づいています。[SELECT](select-entity-sql.md)、 [FROM](from-entity-sql.md)、 [WHERE](where-entity-sql.md)、 [GROUP BY](group-by-entity-sql.md)、 [HAVING](having-entity-sql.md)、および[ORDER by](order-by-entity-sql.md)を指定します。</span><span class="sxs-lookup"><span data-stu-id="e2418-108">They are based on the same clauses found in standard a SQL select statement: [SELECT](select-entity-sql.md), [FROM](from-entity-sql.md), [WHERE](where-entity-sql.md), [GROUP BY](group-by-entity-sql.md), [HAVING](having-entity-sql.md), and [ORDER BY](order-by-entity-sql.md).</span></span>  
  
## <a name="scope"></a><span data-ttu-id="e2418-109">スコープ</span><span class="sxs-lookup"><span data-stu-id="e2418-109">Scope</span></span>  
 <span data-ttu-id="e2418-110">FROM 句で定義された名前は、出現順 (左から右の順) に FROM スコープに導入されます。</span><span class="sxs-lookup"><span data-stu-id="e2418-110">Names defined in the FROM clause are introduced into the FROM scope in order of appearance, left to right.</span></span> <span data-ttu-id="e2418-111">JOIN リストでは、式は既にリストで定義されている名前を参照できます。</span><span class="sxs-lookup"><span data-stu-id="e2418-111">In the JOIN list, expressions can refer to names defined earlier in the list.</span></span> <span data-ttu-id="e2418-112">From 句で指定された要素のパブリックプロパティは FROM スコープに追加されません。これらは常に、エイリアスで修飾された名前を使用して参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2418-112">Public properties of elements identified in the FROM clause are not added to the FROM scope: They must be always referenced through the alias-qualified name.</span></span> <span data-ttu-id="e2418-113">通常は、SELECT 式のすべての部分が FROM スコープに含まれると見なされます。</span><span class="sxs-lookup"><span data-stu-id="e2418-113">Normally, all parts of the select expression are considered within the FROM scope.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2418-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="e2418-114">See also</span></span>

- [<span data-ttu-id="e2418-115">Entity SQL リファレンス</span><span class="sxs-lookup"><span data-stu-id="e2418-115">Entity SQL Reference</span></span>](entity-sql-reference.md)
