---
title: サポートされていない式 (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5e79da7e-e78a-413c-8fb0-f3f9cd84f579
dev_langs:
- sql
ms.openlocfilehash: 956fe117eb0c59392c3999046bc70deaed268ac6
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70248781"
---
# <a name="unsupported-expressions"></a><span data-ttu-id="6566c-102">サポートされていない式</span><span class="sxs-lookup"><span data-stu-id="6566c-102">Unsupported expressions</span></span>

<span data-ttu-id="6566c-103">このトピックでは、で[!INCLUDE[esql](../../../../../../includes/esql-md.md)]サポートされていない transact-sql 式について説明します。</span><span class="sxs-lookup"><span data-stu-id="6566c-103">This topic describes Transact-SQL expressions that are not supported in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span> <span data-ttu-id="6566c-104">詳細については、「 [Entity SQL と transact-sql の違い](how-entity-sql-differs-from-transact-sql.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6566c-104">For more information, see [How Entity SQL Differs from Transact-SQL](how-entity-sql-differs-from-transact-sql.md).</span></span>

## <a name="quantified-predicates"></a><span data-ttu-id="6566c-105">定量化述語</span><span class="sxs-lookup"><span data-stu-id="6566c-105">Quantified predicates</span></span>

<span data-ttu-id="6566c-106">Transact-sql では、次の形式の構造が許可されます。</span><span class="sxs-lookup"><span data-stu-id="6566c-106">Transact-SQL allows constructs of the following form:</span></span>

```sql
sal > all (select salary from employees)
sal > any (select salary from employees)
```

<span data-ttu-id="6566c-107">ただし、[!INCLUDE[esql](../../../../../../includes/esql-md.md)] では、このようなコンストラクターがサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="6566c-107">[!INCLUDE[esql](../../../../../../includes/esql-md.md)], however, does not support such constructs.</span></span> <span data-ttu-id="6566c-108">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] では、これに相当する式を次のように記述できます。</span><span class="sxs-lookup"><span data-stu-id="6566c-108">Equivalent expressions can be written in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] as follows:</span></span>

```sql
not exists(select 0 from employees as e where sal <= e.salary)
exists(select 0 from employees as e where sal > e.salary)
```

## <a name="-operator"></a><span data-ttu-id="6566c-109">\* 演算子</span><span class="sxs-lookup"><span data-stu-id="6566c-109">\* operator</span></span>

<span data-ttu-id="6566c-110">Transact-sql では、SELECT 句で \* 演算子を使用して、すべての列を予測する必要があることを示しています。これは [!INCLUDE[esql](../../../../../../includes/esql-md.md)] でサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="6566c-110">Transact-SQL supports the use of the \* operator in the SELECT clause to indicate that all columns should be projected out. This is not supported in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span>

## <a name="see-also"></a><span data-ttu-id="6566c-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="6566c-111">See also</span></span>

- [<span data-ttu-id="6566c-112">Entity SQL の概要</span><span class="sxs-lookup"><span data-stu-id="6566c-112">Entity SQL Overview</span></span>](entity-sql-overview.md)
- [<span data-ttu-id="6566c-113">Entity SQL と Transact-SQL の相違点</span><span class="sxs-lookup"><span data-stu-id="6566c-113">How Entity SQL Differs from Transact-SQL</span></span>](how-entity-sql-differs-from-transact-sql.md)
