---
title: Skip While 句
ms.date: 07/20/2015
f1_keywords:
- vb.QuerySkipWhile
helpviewer_keywords:
- Skip While statement [Visual Basic]
- Skip While clause [Visual Basic]
- queries [Visual Basic], Skip While
ms.assetid: 5dee8350-7520-4f1a-b00d-590cacd572d6
ms.openlocfilehash: 47703e445865435f5bf5312c3fe41833ac21aa3f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74333138"
---
# <a name="skip-while-clause-visual-basic"></a><span data-ttu-id="00bf5-102">Skip While 句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="00bf5-102">Skip While Clause (Visual Basic)</span></span>
<span data-ttu-id="00bf5-103">指定された条件が `true` である限り、コレクションの要素をバイパスし、残りの要素を返します。</span><span class="sxs-lookup"><span data-stu-id="00bf5-103">Bypasses elements in a collection as long as a specified condition is `true` and then returns the remaining elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00bf5-104">構文</span><span class="sxs-lookup"><span data-stu-id="00bf5-104">Syntax</span></span>  
  
```vb  
Skip While expression  
```  
  
## <a name="parts"></a><span data-ttu-id="00bf5-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="00bf5-105">Parts</span></span>  
  
|<span data-ttu-id="00bf5-106">用語</span><span class="sxs-lookup"><span data-stu-id="00bf5-106">Term</span></span>|<span data-ttu-id="00bf5-107">定義</span><span class="sxs-lookup"><span data-stu-id="00bf5-107">Definition</span></span>|  
|---|---|  
|`expression`|<span data-ttu-id="00bf5-108">必須です。</span><span class="sxs-lookup"><span data-stu-id="00bf5-108">Required.</span></span> <span data-ttu-id="00bf5-109">次の要素をテストするための条件を表す式。</span><span class="sxs-lookup"><span data-stu-id="00bf5-109">An expression that represents a condition to test elements for.</span></span> <span data-ttu-id="00bf5-110">式は、`Boolean` 値または同等の機能 (`Boolean` として評価される `Integer` など) を返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="00bf5-110">The expression must return a `Boolean` value or a functional equivalent, such as an `Integer` to be evaluated as a `Boolean`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="00bf5-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="00bf5-111">Remarks</span></span>  
 <span data-ttu-id="00bf5-112">`Skip While` 句では、クエリ結果の先頭から、指定された `expression` で `false` が返されるまでの要素がバイパスされます。</span><span class="sxs-lookup"><span data-stu-id="00bf5-112">The `Skip While` clause bypasses elements from the beginning of a query result until the supplied `expression` returns `false`.</span></span> <span data-ttu-id="00bf5-113">`expression` で `false` が返されると、クエリが残りのすべての要素を返します。</span><span class="sxs-lookup"><span data-stu-id="00bf5-113">After `expression` returns `false`, the query returns all the remaining elements.</span></span> <span data-ttu-id="00bf5-114">残りの結果に対して、`expression` は無視されます。</span><span class="sxs-lookup"><span data-stu-id="00bf5-114">The `expression` is ignored for the remaining results.</span></span>  
  
 <span data-ttu-id="00bf5-115">`Skip While` 句は、`Where` 句を使用して、特定の条件を満たしていないすべての要素をクエリから除外できるという点で、`Where` 句と異なります。</span><span class="sxs-lookup"><span data-stu-id="00bf5-115">The `Skip While` clause differs from the `Where` clause in that the `Where` clause can be used to exclude all elements from a query that do not meet a particular condition.</span></span> <span data-ttu-id="00bf5-116">`Skip While` 句では、初めて条件が満たされなくなったときまでの要素が除外されます。</span><span class="sxs-lookup"><span data-stu-id="00bf5-116">The `Skip While` clause excludes elements only until the first time that the condition is not satisfied.</span></span> <span data-ttu-id="00bf5-117">`Skip While` 句は、順序付けされたクエリ結果を操作する場合に最も役立ちます。</span><span class="sxs-lookup"><span data-stu-id="00bf5-117">The `Skip While` clause is most useful when you are working with an ordered query result.</span></span>  
  
 <span data-ttu-id="00bf5-118">`Skip` 句を使用して、クエリ結果の先頭から特定の数の結果をバイパスできます。</span><span class="sxs-lookup"><span data-stu-id="00bf5-118">You can bypass a specific number of results from the beginning of a query result by using the `Skip` clause.</span></span>  
  
## <a name="example"></a><span data-ttu-id="00bf5-119">例</span><span class="sxs-lookup"><span data-stu-id="00bf5-119">Example</span></span>  
 <span data-ttu-id="00bf5-120">次のコード例では、`Skip While` 句を使用して、米国の最初の顧客が見つかるまで結果をバイパスします。</span><span class="sxs-lookup"><span data-stu-id="00bf5-120">The following code example uses the `Skip While` clause to bypass results until the first customer from the United States is found.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="00bf5-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="00bf5-121">See also</span></span>

- [<span data-ttu-id="00bf5-122">Visual Basic における LINQ の概要</span><span class="sxs-lookup"><span data-stu-id="00bf5-122">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="00bf5-123">クエリ</span><span class="sxs-lookup"><span data-stu-id="00bf5-123">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="00bf5-124">Select 句</span><span class="sxs-lookup"><span data-stu-id="00bf5-124">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="00bf5-125">From 句</span><span class="sxs-lookup"><span data-stu-id="00bf5-125">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="00bf5-126">Skip 句</span><span class="sxs-lookup"><span data-stu-id="00bf5-126">Skip Clause</span></span>](../../../visual-basic/language-reference/queries/skip-clause.md)
- [<span data-ttu-id="00bf5-127">Take While 句</span><span class="sxs-lookup"><span data-stu-id="00bf5-127">Take While Clause</span></span>](../../../visual-basic/language-reference/queries/take-while-clause.md)
- [<span data-ttu-id="00bf5-128">WHERE 句</span><span class="sxs-lookup"><span data-stu-id="00bf5-128">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
