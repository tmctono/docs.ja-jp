---
title: 演算子の優先順位 (Entity SQL)
ms.date: 03/30/2017
ms.assetid: e92e4ca5-2889-4266-9625-47f0eb01a948
ms.openlocfilehash: 2d8c78f410708fd1aa843ee8f14f7243a9f686c0
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70249781"
---
# <a name="operator-precedence-entity-sql"></a><span data-ttu-id="7820a-102">演算子の優先順位 (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="7820a-102">Operator Precedence (Entity SQL)</span></span>
<span data-ttu-id="7820a-103">クエリに[!INCLUDE[esql](../../../../../../includes/esql-md.md)]複数の演算子がある場合、演算子の優先順位によって、操作が実行される順序が決まります。</span><span class="sxs-lookup"><span data-stu-id="7820a-103">When an [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query has multiple operators, operator precedence determines the sequence in which the operations are performed.</span></span> <span data-ttu-id="7820a-104">実行される順序により、クエリ結果の値は大きく変わります。</span><span class="sxs-lookup"><span data-stu-id="7820a-104">The order of execution can significantly affect the query result.</span></span>  
  
 <span data-ttu-id="7820a-105">演算子には、次の表に示す優先順位レベルが定義されています。</span><span class="sxs-lookup"><span data-stu-id="7820a-105">Operators have the precedence levels shown in the following table.</span></span> <span data-ttu-id="7820a-106">優先順位が高い演算子は、優先順位が低い演算子よりも前に評価されます。</span><span class="sxs-lookup"><span data-stu-id="7820a-106">An operator with a higher level is evaluated before an operator with a lower level.</span></span>  
  
|<span data-ttu-id="7820a-107">レベル</span><span class="sxs-lookup"><span data-stu-id="7820a-107">Level</span></span>|<span data-ttu-id="7820a-108">演算の種類</span><span class="sxs-lookup"><span data-stu-id="7820a-108">Operation type</span></span>|<span data-ttu-id="7820a-109">演算子</span><span class="sxs-lookup"><span data-stu-id="7820a-109">Operator</span></span>|  
|-----------|--------------------|--------------|  
|<span data-ttu-id="7820a-110">1</span><span class="sxs-lookup"><span data-stu-id="7820a-110">1</span></span>|<span data-ttu-id="7820a-111">1 次式</span><span class="sxs-lookup"><span data-stu-id="7820a-111">Primary</span></span>|`. , [] ()`|  
|<span data-ttu-id="7820a-112">2</span><span class="sxs-lookup"><span data-stu-id="7820a-112">2</span></span>|<span data-ttu-id="7820a-113">単項</span><span class="sxs-lookup"><span data-stu-id="7820a-113">Unary</span></span>|`! not`|  
|<span data-ttu-id="7820a-114">3</span><span class="sxs-lookup"><span data-stu-id="7820a-114">3</span></span>|<span data-ttu-id="7820a-115">乗法</span><span class="sxs-lookup"><span data-stu-id="7820a-115">Multiplicative</span></span>|`* / %`|  
|<span data-ttu-id="7820a-116">4</span><span class="sxs-lookup"><span data-stu-id="7820a-116">4</span></span>|<span data-ttu-id="7820a-117">加法</span><span class="sxs-lookup"><span data-stu-id="7820a-117">Additive</span></span>|`+ -`|  
|<span data-ttu-id="7820a-118">5</span><span class="sxs-lookup"><span data-stu-id="7820a-118">5</span></span>|<span data-ttu-id="7820a-119">順序</span><span class="sxs-lookup"><span data-stu-id="7820a-119">Ordering</span></span>|`< > <= >=`|  
|<span data-ttu-id="7820a-120">6</span><span class="sxs-lookup"><span data-stu-id="7820a-120">6</span></span>|<span data-ttu-id="7820a-121">等価比較</span><span class="sxs-lookup"><span data-stu-id="7820a-121">Equality</span></span>|`= != <>`|  
|<span data-ttu-id="7820a-122">7</span><span class="sxs-lookup"><span data-stu-id="7820a-122">7</span></span>|<span data-ttu-id="7820a-123">条件 AND</span><span class="sxs-lookup"><span data-stu-id="7820a-123">Conditional AND</span></span>|`and &&`|  
|<span data-ttu-id="7820a-124">8</span><span class="sxs-lookup"><span data-stu-id="7820a-124">8</span></span>|<span data-ttu-id="7820a-125">条件 OR</span><span class="sxs-lookup"><span data-stu-id="7820a-125">Conditional OR</span></span>|`or &#124;&#124;`|  
  
 <span data-ttu-id="7820a-126">式の中の 2 つの演算子が同じ優先順位レベルである場合は、クエリの中での位置に従って演算子は左から右へと評価されます。</span><span class="sxs-lookup"><span data-stu-id="7820a-126">When two operators in an expression have the same operator precedence level, they are evaluated left to right, based on their position in the query.</span></span> <span data-ttu-id="7820a-127">たとえば、`x+y-z` は `(x+y)-z` と評価されます。</span><span class="sxs-lookup"><span data-stu-id="7820a-127">For example, `x+y-z` is evaluated as `(x+y)-z`.</span></span>  
  
 <span data-ttu-id="7820a-128">クエリの中で演算子の定義済みの優先順位をオーバーライドするには、かっこを使用します。</span><span class="sxs-lookup"><span data-stu-id="7820a-128">You can use parentheses to override the defined precedence of the operators in a query.</span></span> <span data-ttu-id="7820a-129">この場合、かっこ内のすべての演算が評価され、1 つの結果が作成されてから、かっこ外の演算子でこの結果が使用されます。</span><span class="sxs-lookup"><span data-stu-id="7820a-129">Everything within parentheses is evaluated first to yield a single result before that result can be used by any operator outside the parentheses.</span></span> <span data-ttu-id="7820a-130">たとえば、は`x+y*z` `x` `x` `z` `y` `(x+y)*z`とを加算した後、を追加しますが、結果はによって乗算されます。 `y` `z`</span><span class="sxs-lookup"><span data-stu-id="7820a-130">For example, `x+y*z` multiplies `y` by `z` and then adds `x`, but `(x+y)*z` adds `x` to `y` and then multiplies the result by `z`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7820a-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="7820a-131">See also</span></span>

- [<span data-ttu-id="7820a-132">Entity SQL の概要</span><span class="sxs-lookup"><span data-stu-id="7820a-132">Entity SQL Overview</span></span>](entity-sql-overview.md)
