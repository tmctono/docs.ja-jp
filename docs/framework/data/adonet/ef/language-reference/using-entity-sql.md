---
title: USING (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 20f58b8f-6070-4456-b7e8-5ff3d6269273
ms.openlocfilehash: bdab81ed8acae5e757de0a669922dc79d0303ee4
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203593"
---
# <a name="using-entity-sql"></a><span data-ttu-id="c03a2-102">USING (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="c03a2-102">USING (Entity SQL)</span></span>

<span data-ttu-id="c03a2-103">クエリ式で使用する名前空間を指定します。</span><span class="sxs-lookup"><span data-stu-id="c03a2-103">Specifies namespaces used in a query expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c03a2-104">構文</span><span class="sxs-lookup"><span data-stu-id="c03a2-104">Syntax</span></span>  
  
```sql  
USING [ alias = ] namespace  
```  
  
## <a name="arguments"></a><span data-ttu-id="c03a2-105">引数</span><span class="sxs-lookup"><span data-stu-id="c03a2-105">Arguments</span></span>  

 `alias`  
 <span data-ttu-id="c03a2-106">名前空間を修飾する短い別名。</span><span class="sxs-lookup"><span data-stu-id="c03a2-106">Specifies a shorter alias to qualify a namespace with.</span></span>  
  
 `namespace`  
 <span data-ttu-id="c03a2-107">任意の有効な名前空間。</span><span class="sxs-lookup"><span data-stu-id="c03a2-107">Any valid namespace.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c03a2-108">例</span><span class="sxs-lookup"><span data-stu-id="c03a2-108">Example</span></span>  

 <span data-ttu-id="c03a2-109">次の Entity SQL クエリでは、USING 演算子を使用して、クエリ式に使用する名前空間が指定されています。</span><span class="sxs-lookup"><span data-stu-id="c03a2-109">The following Entity SQL query uses the USING operator to specify namespaces used in a query expression.</span></span> <span data-ttu-id="c03a2-110">このクエリをコンパイルして実行するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c03a2-110">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="c03a2-111">「[方法: PrimitiveType 結果を返すクエリを実行する](../how-to-execute-a-query-that-returns-primitivetype-results.md)」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="c03a2-111">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2. <span data-ttu-id="c03a2-112">次のクエリを引数として `ExecutePrimitiveTypeQuery` メソッドに渡します。</span><span class="sxs-lookup"><span data-stu-id="c03a2-112">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
```csharp
using SqlServer; RAND()  
```  
  
## <a name="see-also"></a><span data-ttu-id="c03a2-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="c03a2-113">See also</span></span>

- [<span data-ttu-id="c03a2-114">名前空間</span><span class="sxs-lookup"><span data-stu-id="c03a2-114">Namespaces</span></span>](namespaces-entity-sql.md)
- [<span data-ttu-id="c03a2-115">Entity SQL リファレンス</span><span class="sxs-lookup"><span data-stu-id="c03a2-115">Entity SQL Reference</span></span>](entity-sql-reference.md)
