---
title: サポートされていない式 (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5e79da7e-e78a-413c-8fb0-f3f9cd84f579
dev_langs:
- sql
ms.openlocfilehash: af0e00f470584883b6a65b63f2650c1c359b404c
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2019
ms.locfileid: "66489859"
---
# <a name="unsupported-expressions"></a><span data-ttu-id="7d499-102">サポートされていない式</span><span class="sxs-lookup"><span data-stu-id="7d499-102">Unsupported expressions</span></span>

<span data-ttu-id="7d499-103">このトピックで説明でサポートされていない TRANSACT-SQL 式[!INCLUDE[esql](../../../../../../includes/esql-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="7d499-103">This topic describes Transact-SQL expressions that are not supported in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span> <span data-ttu-id="7d499-104">詳細については、次を参照してください。 [Entity SQL の相違 TRANSACT-SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/how-entity-sql-differs-from-transact-sql.md)します。</span><span class="sxs-lookup"><span data-stu-id="7d499-104">For more information, see [How Entity SQL Differs from Transact-SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/how-entity-sql-differs-from-transact-sql.md).</span></span>

## <a name="quantified-predicates"></a><span data-ttu-id="7d499-105">定量化された述語</span><span class="sxs-lookup"><span data-stu-id="7d499-105">Quantified predicates</span></span>

<span data-ttu-id="7d499-106">TRANSACT-SQL は、次の形式の構成要素を使用できます。</span><span class="sxs-lookup"><span data-stu-id="7d499-106">Transact-SQL allows constructs of the following form:</span></span>

```sql
sal > all (select salary from employees)
sal > any (select salary from employees)
```

<span data-ttu-id="7d499-107">ただし、[!INCLUDE[esql](../../../../../../includes/esql-md.md)] では、このようなコンストラクターがサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="7d499-107">[!INCLUDE[esql](../../../../../../includes/esql-md.md)], however, does not support such constructs.</span></span> <span data-ttu-id="7d499-108">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] では、これに相当する式を次のように記述できます。</span><span class="sxs-lookup"><span data-stu-id="7d499-108">Equivalent expressions can be written in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] as follows:</span></span>

```sql
not exists(select 0 from employees as e where sal <= e.salary)
exists(select 0 from employees as e where sal > e.salary)
```

## <a name="-operator"></a><span data-ttu-id="7d499-109">\* 演算子</span><span class="sxs-lookup"><span data-stu-id="7d499-109">\* operator</span></span>

<span data-ttu-id="7d499-110">TRANSACT-SQL の使用をサポートする、\* をすべての列を予測するかを示すために、SELECT 句での演算子。これは [!INCLUDE[esql](../../../../../../includes/esql-md.md)] でサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="7d499-110">Transact-SQL supports the use of the \* operator in the SELECT clause to indicate that all columns should be projected out. This is not supported in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span>

## <a name="see-also"></a><span data-ttu-id="7d499-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="7d499-111">See also</span></span>

- [<span data-ttu-id="7d499-112">Entity SQL の概要</span><span class="sxs-lookup"><span data-stu-id="7d499-112">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
- [<span data-ttu-id="7d499-113">Entity SQL と Transact-SQL の相違点</span><span class="sxs-lookup"><span data-stu-id="7d499-113">How Entity SQL Differs from Transact-SQL</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/how-entity-sql-differs-from-transact-sql.md)
