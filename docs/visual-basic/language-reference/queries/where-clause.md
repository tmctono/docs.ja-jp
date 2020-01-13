---
title: Where 句
ms.date: 07/20/2015
f1_keywords:
- vb.QueryWhere
helpviewer_keywords:
- Where statement [Visual Basic]
- queries [Visual Basic], Where
- Where clause [Visual Basic]
ms.assetid: 48b5c2c5-3181-429c-8545-894296798c89
ms.openlocfilehash: 60b7ebe96ce0c4580c36675b2e4aa5f9888732c3
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349625"
---
# <a name="where-clause-visual-basic"></a><span data-ttu-id="247e9-102">Where 句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="247e9-102">Where Clause (Visual Basic)</span></span>
<span data-ttu-id="247e9-103">クエリのフィルター条件を指定します。</span><span class="sxs-lookup"><span data-stu-id="247e9-103">Specifies the filtering condition for a query.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="247e9-104">構文</span><span class="sxs-lookup"><span data-stu-id="247e9-104">Syntax</span></span>  
  
```vb  
Where condition  
```  
  
## <a name="parts"></a><span data-ttu-id="247e9-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="247e9-105">Parts</span></span>  
 `condition`  
 <span data-ttu-id="247e9-106">必須。</span><span class="sxs-lookup"><span data-stu-id="247e9-106">Required.</span></span> <span data-ttu-id="247e9-107">コレクション内の現在の項目の値が出力コレクションに含まれるかどうかを決定する式。</span><span class="sxs-lookup"><span data-stu-id="247e9-107">An expression that determines whether the values for the current item in the collection are included in the output collection.</span></span> <span data-ttu-id="247e9-108">式は、`Boolean` 値または `Boolean` 値に相当する値に評価される必要があります。</span><span class="sxs-lookup"><span data-stu-id="247e9-108">The expression must evaluate to a `Boolean` value or the equivalent of a `Boolean` value.</span></span> <span data-ttu-id="247e9-109">条件が `True`と評価された場合、要素はクエリの結果に含まれます。それ以外の場合、要素はクエリの結果から除外されます。</span><span class="sxs-lookup"><span data-stu-id="247e9-109">If the condition evaluates to `True`, the element is included in the query result; otherwise, the element is excluded from the query result.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="247e9-110">コメント</span><span class="sxs-lookup"><span data-stu-id="247e9-110">Remarks</span></span>  
 <span data-ttu-id="247e9-111">`Where` 句を使用すると、特定の条件を満たす要素のみを選択してクエリデータをフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="247e9-111">The `Where` clause enables you to filter query data by selecting only elements that meet certain criteria.</span></span> <span data-ttu-id="247e9-112">`Where` 句が `True` と評価される値を持つ要素がクエリ結果に含まれます。その他の要素は除外されます。</span><span class="sxs-lookup"><span data-stu-id="247e9-112">Elements whose values cause the `Where` clause to evaluate to `True` are included in the query result; other elements are excluded.</span></span> <span data-ttu-id="247e9-113">`Where` 句で使用される式は、値が0の場合に `False` に評価される整数など、`Boolean` または `Boolean`に相当するものに評価される必要があります。</span><span class="sxs-lookup"><span data-stu-id="247e9-113">The expression that is used in a `Where` clause must evaluate to a `Boolean` or the equivalent of a `Boolean`, such as an Integer that evaluates to `False` when its value is zero.</span></span> <span data-ttu-id="247e9-114">`And`、`Or`、`AndAlso`、`OrElse`、`Is`、`IsNot`などの論理演算子を使用して、`Where` 句で複数の式を組み合わせることができます。</span><span class="sxs-lookup"><span data-stu-id="247e9-114">You can combine multiple expressions in a `Where` clause by using logical operators such as `And`, `Or`, `AndAlso`, `OrElse`, `Is`, and `IsNot`.</span></span>  
  
 <span data-ttu-id="247e9-115">既定では、クエリ式は、アクセスされるまで評価されません。たとえば、データバインドされている場合や、`For` ループ内で反復処理される場合です。</span><span class="sxs-lookup"><span data-stu-id="247e9-115">By default, query expressions are not evaluated until they are accessed—for example, when they are data-bound or iterated through in a `For` loop.</span></span> <span data-ttu-id="247e9-116">その結果、`Where` 句は、クエリがアクセスされるまで評価されません。</span><span class="sxs-lookup"><span data-stu-id="247e9-116">As a result, the `Where` clause is not evaluated until the query is accessed.</span></span> <span data-ttu-id="247e9-117">`Where` 句で使用されているクエリの外部の値がある場合は、クエリの実行時に `Where` 句で適切な値が使用されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="247e9-117">If you have values external to the query that are used in the `Where` clause, ensure that the appropriate value is used in the `Where` clause at the time the query is executed.</span></span> <span data-ttu-id="247e9-118">クエリ実行の詳細については、「[初めてのLINQ クエリの作成](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="247e9-118">For more information about query execution, see [Writing Your First LINQ Query](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).</span></span>  
  
 <span data-ttu-id="247e9-119">`Where` 句内で関数を呼び出して、コレクション内の現在の要素の値に対して計算または操作を実行することができます。</span><span class="sxs-lookup"><span data-stu-id="247e9-119">You can call functions within a `Where` clause to perform a calculation or operation on a value from the current element in the collection.</span></span> <span data-ttu-id="247e9-120">`Where` 句で関数を呼び出すと、クエリがアクセス時ではなく定義された直後に実行される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="247e9-120">Calling a function in a `Where` clause can cause the query to be executed immediately when it is defined instead of when it is accessed.</span></span> <span data-ttu-id="247e9-121">クエリ実行の詳細については、「[初めてのLINQ クエリの作成](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="247e9-121">For more information about query execution, see [Writing Your First LINQ Query](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="247e9-122">例</span><span class="sxs-lookup"><span data-stu-id="247e9-122">Example</span></span>  
 <span data-ttu-id="247e9-123">次のクエリ式では、`From` 句を使用して、`customers` コレクション内の各 `Customer` オブジェクトに対して `cust` 範囲変数を宣言します。</span><span class="sxs-lookup"><span data-stu-id="247e9-123">The following query expression uses a `From` clause to declare a range variable `cust` for each `Customer` object in the `customers` collection.</span></span> <span data-ttu-id="247e9-124">`Where` 句では、範囲変数を使用して、指定された地域の顧客に出力を制限します。</span><span class="sxs-lookup"><span data-stu-id="247e9-124">The `Where` clause uses the range variable to restrict the output to customers from the specified region.</span></span> <span data-ttu-id="247e9-125">`For Each` ループでは、クエリ結果に各顧客の会社名が表示されます。</span><span class="sxs-lookup"><span data-stu-id="247e9-125">The `For Each` loop displays the company name for each customer in the query result.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#23)]  
  
## <a name="example"></a><span data-ttu-id="247e9-126">例</span><span class="sxs-lookup"><span data-stu-id="247e9-126">Example</span></span>  
 <span data-ttu-id="247e9-127">次の例では、`Where` 句で `And` および `Or` 論理演算子を使用します。</span><span class="sxs-lookup"><span data-stu-id="247e9-127">The following example uses `And` and `Or` logical operators in the `Where` clause.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#31)]  
  
## <a name="see-also"></a><span data-ttu-id="247e9-128">参照</span><span class="sxs-lookup"><span data-stu-id="247e9-128">See also</span></span>

- [<span data-ttu-id="247e9-129">Visual Basic における LINQ の概要</span><span class="sxs-lookup"><span data-stu-id="247e9-129">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="247e9-130">クエリ</span><span class="sxs-lookup"><span data-stu-id="247e9-130">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="247e9-131">From 句</span><span class="sxs-lookup"><span data-stu-id="247e9-131">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="247e9-132">Select 句</span><span class="sxs-lookup"><span data-stu-id="247e9-132">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="247e9-133">For Each...Next ステートメント</span><span class="sxs-lookup"><span data-stu-id="247e9-133">For Each...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
