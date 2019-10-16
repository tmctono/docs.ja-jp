---
title: パラメーター (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 8d618edd-0988-4ff2-8263-ce59448af7a5
ms.openlocfilehash: 8fbca4f10a7c2c3dbaffff978a536b87d31a8df4
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319432"
---
# <a name="parameters-entity-sql"></a><span data-ttu-id="a72a3-102">パラメーター (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="a72a3-102">Parameters (Entity SQL)</span></span>
<span data-ttu-id="a72a3-103">パラメーターは、[!INCLUDE[esql](../../../../../../includes/esql-md.md)] の外部で定義される変数です。通常は、ホスト言語で使用されるバインド API を通じて定義されます。</span><span class="sxs-lookup"><span data-stu-id="a72a3-103">Parameters are variables that are defined outside [!INCLUDE[esql](../../../../../../includes/esql-md.md)], usually through a binding API that is used by a host language.</span></span> <span data-ttu-id="a72a3-104">それぞれのパラメーターには、名前と型があります。</span><span class="sxs-lookup"><span data-stu-id="a72a3-104">Each parameter has a name and a type.</span></span> <span data-ttu-id="a72a3-105">パラメーター名は、クエリ式で、アットマーク (@) をプレフィックスとして定義されています。</span><span class="sxs-lookup"><span data-stu-id="a72a3-105">Parameter names are defined in query expressions with the at (@) symbol as a prefix.</span></span> <span data-ttu-id="a72a3-106">これにより、クエリ内で定義されている他の名前 (プロパティ名など) と明確に区別されます。</span><span class="sxs-lookup"><span data-stu-id="a72a3-106">This disambiguates them from the names of properties or other names that are defined in the query.</span></span>  
  
 <span data-ttu-id="a72a3-107">パラメーターをバインドするための API は、ホスト言語によって提供されます。</span><span class="sxs-lookup"><span data-stu-id="a72a3-107">The host-language binding API provides APIs for binding parameters.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a72a3-108">例</span><span class="sxs-lookup"><span data-stu-id="a72a3-108">Example</span></span>  
  
```sql  
SELECT c   
      FROM LOB.Customers AS c   
      WHERE c.Name = @name  
```  
  
## <a name="see-also"></a><span data-ttu-id="a72a3-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="a72a3-109">See also</span></span>

- [<span data-ttu-id="a72a3-110">Entity SQL リファレンス</span><span class="sxs-lookup"><span data-stu-id="a72a3-110">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="a72a3-111">Entity SQL の概要</span><span class="sxs-lookup"><span data-stu-id="a72a3-111">Entity SQL Overview</span></span>](entity-sql-overview.md)
