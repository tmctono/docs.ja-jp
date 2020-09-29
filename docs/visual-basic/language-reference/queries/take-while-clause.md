---
title: Take While 句
ms.date: 07/20/2015
f1_keywords:
- vb.QueryTakeWhile
helpviewer_keywords:
- queries [Visual Basic], Take While
- Take While clause [Visual Basic]
- Take While statement [Visual Basic]
ms.assetid: db8f9f2f-fc9f-4a6c-b0b8-1bf048147e11
ms.openlocfilehash: 632e9e2195f21a3aa1d1ffd28e9838905c471156
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "90869660"
---
# <a name="take-while-clause-visual-basic"></a><span data-ttu-id="62041-102">Take While 句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="62041-102">Take While Clause (Visual Basic)</span></span>

<span data-ttu-id="62041-103">指定された条件が `true` である限り、コレクションの要素を含むようにし、残りの要素をバイパスします。</span><span class="sxs-lookup"><span data-stu-id="62041-103">Includes elements in a collection as long as a specified condition is `true` and bypasses the remaining elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62041-104">構文</span><span class="sxs-lookup"><span data-stu-id="62041-104">Syntax</span></span>  
  
```vb  
Take While expression  
```  
  
## <a name="parts"></a><span data-ttu-id="62041-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="62041-105">Parts</span></span>  
  
|<span data-ttu-id="62041-106">用語</span><span class="sxs-lookup"><span data-stu-id="62041-106">Term</span></span>|<span data-ttu-id="62041-107">定義</span><span class="sxs-lookup"><span data-stu-id="62041-107">Definition</span></span>|  
|---|---|  
|`expression`|<span data-ttu-id="62041-108">必須です。</span><span class="sxs-lookup"><span data-stu-id="62041-108">Required.</span></span> <span data-ttu-id="62041-109">次の要素をテストするための条件を表す式。</span><span class="sxs-lookup"><span data-stu-id="62041-109">An expression that represents a condition to test elements for.</span></span> <span data-ttu-id="62041-110">式は、`Boolean` 値または同等の機能 (`Boolean` として評価される `Integer` など) を返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="62041-110">The expression must return a `Boolean` value or a functional equivalent, such as an `Integer` to be evaluated as a `Boolean`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="62041-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="62041-111">Remarks</span></span>  

 <span data-ttu-id="62041-112">`Take While` 句には、クエリ結果の先頭から、指定された `expression` で `false` が返されるまでの要素が含まれます。</span><span class="sxs-lookup"><span data-stu-id="62041-112">The `Take While` clause includes elements from the start of a query result until the supplied `expression` returns `false`.</span></span> <span data-ttu-id="62041-113">`expression` が `false` を返すと、クエリでは残りのすべての要素がバイパスされます。</span><span class="sxs-lookup"><span data-stu-id="62041-113">After the `expression` returns `false`, the query will bypass all remaining elements.</span></span> <span data-ttu-id="62041-114">残りの結果に対して、`expression` は無視されます。</span><span class="sxs-lookup"><span data-stu-id="62041-114">The `expression` is ignored for the remaining results.</span></span>  
  
 <span data-ttu-id="62041-115">`Take While` 句は、`Where` 句を使用して、特定の条件を満たすクエリからのすべての要素を含めることができるという点で、`Where` 句と異なります。</span><span class="sxs-lookup"><span data-stu-id="62041-115">The `Take While` clause differs from the `Where` clause in that the `Where` clause can be used to include all elements from a query that meet a particular condition.</span></span> <span data-ttu-id="62041-116">`Take While` 句には、初めて条件が満たされなくなったときまでの要素が含まれます。</span><span class="sxs-lookup"><span data-stu-id="62041-116">The `Take While` clause includes elements only until the first time that the condition is not satisfied.</span></span> <span data-ttu-id="62041-117">`Take While` 句は、順序付けされたクエリ結果を操作する場合に最も役立ちます。</span><span class="sxs-lookup"><span data-stu-id="62041-117">The `Take While` clause is most useful when you are working with an ordered query result.</span></span>  
  
## <a name="example"></a><span data-ttu-id="62041-118">例</span><span class="sxs-lookup"><span data-stu-id="62041-118">Example</span></span>  

 <span data-ttu-id="62041-119">次のコード例では、`Take While` 句を使用して、注文がない最初の顧客が見つかるまで結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="62041-119">The following code example uses the `Take While` clause to retrieve results until the first customer without any orders is found.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="62041-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="62041-120">See also</span></span>

- [<span data-ttu-id="62041-121">Visual Basic における LINQ の概要</span><span class="sxs-lookup"><span data-stu-id="62041-121">Introduction to LINQ in Visual Basic</span></span>](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="62041-122">クエリ</span><span class="sxs-lookup"><span data-stu-id="62041-122">Queries</span></span>](index.md)
- [<span data-ttu-id="62041-123">Select 句</span><span class="sxs-lookup"><span data-stu-id="62041-123">Select Clause</span></span>](select-clause.md)
- [<span data-ttu-id="62041-124">From 句</span><span class="sxs-lookup"><span data-stu-id="62041-124">From Clause</span></span>](from-clause.md)
- [<span data-ttu-id="62041-125">Take 句</span><span class="sxs-lookup"><span data-stu-id="62041-125">Take Clause</span></span>](take-clause.md)
- [<span data-ttu-id="62041-126">Skip While 句</span><span class="sxs-lookup"><span data-stu-id="62041-126">Skip While Clause</span></span>](skip-while-clause.md)
- [<span data-ttu-id="62041-127">WHERE 句</span><span class="sxs-lookup"><span data-stu-id="62041-127">Where Clause</span></span>](where-clause.md)
