---
title: USING (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 20f58b8f-6070-4456-b7e8-5ff3d6269273
ms.openlocfilehash: e14b7857a65898683939647c872c48d0b3fe458a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62034097"
---
# <a name="using-entity-sql"></a><span data-ttu-id="31979-102">USING (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="31979-102">USING (Entity SQL)</span></span>
<span data-ttu-id="31979-103">クエリ式で使用する名前空間を指定します。</span><span class="sxs-lookup"><span data-stu-id="31979-103">Specifies namespaces used in a query expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31979-104">構文</span><span class="sxs-lookup"><span data-stu-id="31979-104">Syntax</span></span>  
  
```  
USING [ alias = ] namespace  
```  
  
## <a name="arguments"></a><span data-ttu-id="31979-105">引数</span><span class="sxs-lookup"><span data-stu-id="31979-105">Arguments</span></span>  
 `alias`  
 <span data-ttu-id="31979-106">名前空間を修飾する短い別名。</span><span class="sxs-lookup"><span data-stu-id="31979-106">Specifies a shorter alias to qualify a namespace with.</span></span>  
  
 `namespace`  
 <span data-ttu-id="31979-107">任意の有効な名前空間。</span><span class="sxs-lookup"><span data-stu-id="31979-107">Any valid namespace.</span></span>  
  
## <a name="example"></a><span data-ttu-id="31979-108">例</span><span class="sxs-lookup"><span data-stu-id="31979-108">Example</span></span>  
 <span data-ttu-id="31979-109">次の Entity SQL クエリでは、USING 演算子を使用して、クエリ式に使用する名前空間が指定されています。</span><span class="sxs-lookup"><span data-stu-id="31979-109">The following Entity SQL query uses the USING operator to specify namespaces used in a query expression.</span></span> <span data-ttu-id="31979-110">このクエリをコンパイルして実行するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="31979-110">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="31979-111">」の手順に従って[方法。PrimitiveType 結果を返すクエリを実行](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md)します。</span><span class="sxs-lookup"><span data-stu-id="31979-111">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2. <span data-ttu-id="31979-112">次のクエリを引数として `ExecutePrimitiveTypeQuery` メソッドに渡します。</span><span class="sxs-lookup"><span data-stu-id="31979-112">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
```  
using SqlServer; RAND()  
```  
  
## <a name="see-also"></a><span data-ttu-id="31979-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="31979-113">See also</span></span>

- [<span data-ttu-id="31979-114">名前空間</span><span class="sxs-lookup"><span data-stu-id="31979-114">Namespaces</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/namespaces-entity-sql.md)
- [<span data-ttu-id="31979-115">Entity SQL リファレンス</span><span class="sxs-lookup"><span data-stu-id="31979-115">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
