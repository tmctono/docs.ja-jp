---
title: ページング (Entity SQL)
ms.date: 03/30/2017
ms.assetid: ba4f334d-03e5-4a7b-9d42-628f4639b9a2
ms.openlocfilehash: 7148d693041968acb543a3d659caf05820f2aff8
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90553637"
---
# <a name="paging-entity-sql"></a><span data-ttu-id="d87cb-102">ページング (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="d87cb-102">Paging (Entity SQL)</span></span>
<span data-ttu-id="d87cb-103">物理的なページングは、[ORDER BY](order-by-entity-sql.md) 句の [SKIP](skip-entity-sql.md) サブ句および [LIMIT](limit-entity-sql.md) サブ句を使用して実行できます。</span><span class="sxs-lookup"><span data-stu-id="d87cb-103">Physical paging can be performed by using the [SKIP](skip-entity-sql.md) and [LIMIT](limit-entity-sql.md) sub-clauses in the [ORDER BY](order-by-entity-sql.md) clause.</span></span> <span data-ttu-id="d87cb-104">物理的ページングを決定的に実行するには、SKIP と LIMIT を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d87cb-104">To perform physical paging deterministically, you should use SKIP and LIMIT.</span></span> <span data-ttu-id="d87cb-105">非決定的な方法で結果の行の数を制限するには、[TOP](top-entity-sql.md) を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d87cb-105">If you only want to restrict the number of rows in the result in a non-deterministic way, you should use [TOP](top-entity-sql.md).</span></span> <span data-ttu-id="d87cb-106">TOP および SKIP/LIMIT は、同時には指定できません。</span><span class="sxs-lookup"><span data-stu-id="d87cb-106">TOP and SKIP/LIMIT are mutually exclusive.</span></span>  
  
## <a name="top-overview"></a><span data-ttu-id="d87cb-107">TOP の概要</span><span class="sxs-lookup"><span data-stu-id="d87cb-107">TOP Overview</span></span>  
 <span data-ttu-id="d87cb-108">SELECT 句には、オプションの ALL/DISTINCT 修飾子に続けてオプションの TOP サブ句を指定できます。</span><span class="sxs-lookup"><span data-stu-id="d87cb-108">The SELECT clause can have an optional TOP sub-clause following the optional ALL/DISTINCT modifier.</span></span> <span data-ttu-id="d87cb-109">TOP サブ句は、クエリ結果の先頭から指定した行セットだけを返すよう指定します。</span><span class="sxs-lookup"><span data-stu-id="d87cb-109">The TOP sub-clause specifies that only the first set of rows will be returned from the query result.</span></span> <span data-ttu-id="d87cb-110">詳細については、「[TOP](top-entity-sql.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d87cb-110">For more information, see [TOP](top-entity-sql.md).</span></span>  
  
## <a name="skip-and-limit-overview"></a><span data-ttu-id="d87cb-111">SKIP/LIMIT の概要</span><span class="sxs-lookup"><span data-stu-id="d87cb-111">SKIP And LIMIT Overview</span></span>  
 <span data-ttu-id="d87cb-112">SKIP と LIMIT は ORDER BY 句の一部です。</span><span class="sxs-lookup"><span data-stu-id="d87cb-112">SKIP and LIMIT are part of the ORDER BY clause.</span></span> <span data-ttu-id="d87cb-113">SKIP 式のサブ句が ORDER BY 句に存在する場合、結果は並べ替え順序に従って並べ替えられ、結果セットには SKIP 式の直後の行から始まる行が含まれます。</span><span class="sxs-lookup"><span data-stu-id="d87cb-113">If a SKIP expression sub-clause is present in a ORDER BY clause, the results will be sorted according to the sort specification and the result set will include row(s) starting from the next row immediately after the SKIP expression.</span></span> <span data-ttu-id="d87cb-114">たとえば、SKIP 5 は、先頭の 5 行をスキップし、6 行目以降を返します。</span><span class="sxs-lookup"><span data-stu-id="d87cb-114">For example, SKIP 5 will skip the first five rows and return from the sixth row forward.</span></span> <span data-ttu-id="d87cb-115">LIMIT 式のサブ句が ORDER BY 句に存在する場合、クエリは並べ替え順序に従って並べ替えられ、結果の行数は LIMIT 式によって制限されます。</span><span class="sxs-lookup"><span data-stu-id="d87cb-115">If a LIMIT expression sub-clause is present in an ORDER BY clause, the query will be sorted according to the sort specification and the resulting number of rows will be restricted by the LIMIT expression.</span></span> <span data-ttu-id="d87cb-116">たとえば、LIMIT 5 は、結果セットを 5 つのインスタンスまたは行に制限します。</span><span class="sxs-lookup"><span data-stu-id="d87cb-116">For instance, LIMIT 5 will restrict the result set to five instances or rows.</span></span> <span data-ttu-id="d87cb-117">SKIP と LIMIT を同時に使用することはできません。SKIP のみまたは LIMIT のみを ORDER BY 句と一緒に使用できます。</span><span class="sxs-lookup"><span data-stu-id="d87cb-117">SKIP and LIMIT do not have to be used together; you can use just SKIP or just LIMIT with ORDER BY clause.</span></span> <span data-ttu-id="d87cb-118">詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d87cb-118">For more information, see the following topics:</span></span>  
  
- [<span data-ttu-id="d87cb-119">SKIP</span><span class="sxs-lookup"><span data-stu-id="d87cb-119">SKIP</span></span>](skip-entity-sql.md)  
  
- [<span data-ttu-id="d87cb-120">LIMIT</span><span class="sxs-lookup"><span data-stu-id="d87cb-120">LIMIT</span></span>](limit-entity-sql.md)  
  
- [<span data-ttu-id="d87cb-121">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="d87cb-121">ORDER BY</span></span>](order-by-entity-sql.md)  
  
## <a name="see-also"></a><span data-ttu-id="d87cb-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="d87cb-122">See also</span></span>

- [<span data-ttu-id="d87cb-123">Entity SQL リファレンス</span><span class="sxs-lookup"><span data-stu-id="d87cb-123">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="d87cb-124">Entity SQL の概要</span><span class="sxs-lookup"><span data-stu-id="d87cb-124">Entity SQL Overview</span></span>](entity-sql-overview.md)
- <span data-ttu-id="d87cb-125">[方法: クエリの結果をページングする](/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="d87cb-125">[How to: Page Through Query Results](/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100))</span></span>
