---
title: パラメーター (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 8d618edd-0988-4ff2-8263-ce59448af7a5
ms.openlocfilehash: e1bb633f7f7c7908a5f424991f20a5cd89aee5aa
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150015"
---
# <a name="parameters-entity-sql"></a><span data-ttu-id="34644-102">パラメーター (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="34644-102">Parameters (Entity SQL)</span></span>
<span data-ttu-id="34644-103">パラメーターは、[!INCLUDE[esql](../../../../../../includes/esql-md.md)] の外部で定義される変数です。通常は、ホスト言語で使用されるバインド API を通じて定義されます。</span><span class="sxs-lookup"><span data-stu-id="34644-103">Parameters are variables that are defined outside [!INCLUDE[esql](../../../../../../includes/esql-md.md)], usually through a binding API that is used by a host language.</span></span> <span data-ttu-id="34644-104">それぞれのパラメーターには、名前と型があります。</span><span class="sxs-lookup"><span data-stu-id="34644-104">Each parameter has a name and a type.</span></span> <span data-ttu-id="34644-105">パラメーター名は、クエリ式の中で、先頭に @ 記号を付けることによって定義します。</span><span class="sxs-lookup"><span data-stu-id="34644-105">Parameter names are defined in query expressions with the at (@) symbol as a prefix.</span></span> <span data-ttu-id="34644-106">これにより、クエリ内で定義されている他の名前 (プロパティ名など) と明確に区別されます。</span><span class="sxs-lookup"><span data-stu-id="34644-106">This disambiguates them from the names of properties or other names that are defined in the query.</span></span>  
  
 <span data-ttu-id="34644-107">パラメーターをバインドするための API は、ホスト言語によって提供されます。</span><span class="sxs-lookup"><span data-stu-id="34644-107">The host-language binding API provides APIs for binding parameters.</span></span>  
  
## <a name="example"></a><span data-ttu-id="34644-108">例</span><span class="sxs-lookup"><span data-stu-id="34644-108">Example</span></span>  
  
```sql  
SELECT c
      FROM LOB.Customers AS c
      WHERE c.Name = @name  
```  
  
## <a name="see-also"></a><span data-ttu-id="34644-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="34644-109">See also</span></span>

- [<span data-ttu-id="34644-110">Entity SQL リファレンス</span><span class="sxs-lookup"><span data-stu-id="34644-110">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="34644-111">Entity SQL の概要</span><span class="sxs-lookup"><span data-stu-id="34644-111">Entity SQL Overview</span></span>](entity-sql-overview.md)
