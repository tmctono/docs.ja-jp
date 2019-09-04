---
title: ユーザー定義関数 (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 3f9e6bbd-8e5a-43e1-809f-f8a61338e522
ms.openlocfilehash: 9ddafb18a10ff2313fd27eab453907054a35218a
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70248770"
---
# <a name="user-defined-functions-entity-sql"></a><span data-ttu-id="cde65-102">ユーザー定義関数 (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="cde65-102">User-Defined Functions (Entity SQL)</span></span>
<span data-ttu-id="cde65-103">Entity SQL では、クエリ内でのユーザー定義関数の呼び出しがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="cde65-103">Entity SQL supports calling user-defined functions in a query.</span></span> <span data-ttu-id="cde65-104">これらの関数は、クエリを使用してインライン[で定義できます (「方法:ユーザー定義関数](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd490951(v=vs.100))を呼び出すか、または概念モデルの一部とし[て、次を参照してください。概念モデル](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100))でカスタム関数を定義します。</span><span class="sxs-lookup"><span data-stu-id="cde65-104">You can define these functions inline with the query (see [How to: Call a User-Defined Function](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd490951(v=vs.100))) or as part of the conceptual model (see [How to: Define Custom Functions in the Conceptual Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100))).</span></span> <span data-ttu-id="cde65-105">概念モデルの関数は、概念モデルの[Function](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#function-element-csdl)要素の[定義要素の](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#definingexpression-element-csdl)Entity SQL コマンドとして定義されます。</span><span class="sxs-lookup"><span data-stu-id="cde65-105">Conceptual model functions are defined as an Entity SQL command in the [DefiningExpression](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#definingexpression-element-csdl) element of a [Function](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#function-element-csdl) element in the conceptual model.</span></span>  
  
 <span data-ttu-id="cde65-106">Entity SQL を使用すると、関数をクエリ コマンド自体で定義することができます。</span><span class="sxs-lookup"><span data-stu-id="cde65-106">Entity SQL enables you to define functions in the query command itself.</span></span> <span data-ttu-id="cde65-107">[関数](function-entity-sql.md)演算子は、インライン関数を定義します。</span><span class="sxs-lookup"><span data-stu-id="cde65-107">The [FUNCTION](function-entity-sql.md) operator defines inline functions.</span></span> <span data-ttu-id="cde65-108">複数の関数を 1 つのコマンドで定義することができます。関数の署名が一意であれば、これら複数の関数に同じ名前を付けることができます。</span><span class="sxs-lookup"><span data-stu-id="cde65-108">You can define multiple functions in a single command, and these functions can have the same function name, as long as the function signatures are unique.</span></span> <span data-ttu-id="cde65-109">詳細については、「 [Function Overload Resolution](function-overload-resolution-entity-sql.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cde65-109">For more information, see [Function Overload Resolution](function-overload-resolution-entity-sql.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cde65-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="cde65-110">See also</span></span>

- [<span data-ttu-id="cde65-111">関数</span><span class="sxs-lookup"><span data-stu-id="cde65-111">Functions</span></span>](functions-entity-sql.md)
