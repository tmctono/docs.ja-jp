---
title: Where 句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryWhere
helpviewer_keywords:
- Where statement [Visual Basic]
- queries [Visual Basic], Where
- Where clause [Visual Basic]
ms.assetid: 48b5c2c5-3181-429c-8545-894296798c89
ms.openlocfilehash: 5632e69039baebb3d1f1fd90c04586d9e50fe40f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61945211"
---
# <a name="where-clause-visual-basic"></a><span data-ttu-id="66606-102">Where 句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="66606-102">Where Clause (Visual Basic)</span></span>
<span data-ttu-id="66606-103">クエリのフィルター処理条件を指定します。</span><span class="sxs-lookup"><span data-stu-id="66606-103">Specifies the filtering condition for a query.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66606-104">構文</span><span class="sxs-lookup"><span data-stu-id="66606-104">Syntax</span></span>  
  
```  
Where condition  
```  
  
## <a name="parts"></a><span data-ttu-id="66606-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="66606-105">Parts</span></span>  
 `condition`  
 <span data-ttu-id="66606-106">必須。</span><span class="sxs-lookup"><span data-stu-id="66606-106">Required.</span></span> <span data-ttu-id="66606-107">コレクション内の現在の項目の値が出力コレクションに含めるかどうかを決定する式。</span><span class="sxs-lookup"><span data-stu-id="66606-107">An expression that determines whether the values for the current item in the collection are included in the output collection.</span></span> <span data-ttu-id="66606-108">式を評価する必要があります、`Boolean`値またはと同等の`Boolean`値。</span><span class="sxs-lookup"><span data-stu-id="66606-108">The expression must evaluate to a `Boolean` value or the equivalent of a `Boolean` value.</span></span> <span data-ttu-id="66606-109">条件の評価が場合`True`要素は、クエリの結果に含まれる以外、それ以外の場合、クエリ結果から要素を除外します。</span><span class="sxs-lookup"><span data-stu-id="66606-109">If the condition evaluates to `True`, the element is included in the query result; otherwise, the element is excluded from the query result.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="66606-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="66606-110">Remarks</span></span>  
 <span data-ttu-id="66606-111">`Where`句では、特定の条件を満たす要素のみを選択してクエリのデータをフィルター処理することができます。</span><span class="sxs-lookup"><span data-stu-id="66606-111">The `Where` clause enables you to filter query data by selecting only elements that meet certain criteria.</span></span> <span data-ttu-id="66606-112">要素の値を持つが、`Where`句を評価する`True`クエリの結果に含まれるその他の要素が除外されます。</span><span class="sxs-lookup"><span data-stu-id="66606-112">Elements whose values cause the `Where` clause to evaluate to `True` are included in the query result; other elements are excluded.</span></span> <span data-ttu-id="66606-113">使用される式を`Where`に句を評価する必要があります、`Boolean`またはと同等の`Boolean`、整数に評価されるなど`False`その値が 0 の場合。</span><span class="sxs-lookup"><span data-stu-id="66606-113">The expression that is used in a `Where` clause must evaluate to a `Boolean` or the equivalent of a `Boolean`, such as an Integer that evaluates to `False` when its value is zero.</span></span> <span data-ttu-id="66606-114">複数の式を組み合わせることができます、`Where`句などの論理演算子を使用して、 `And`、 `Or`、 `AndAlso`、 `OrElse`、 `Is`、および`IsNot`します。</span><span class="sxs-lookup"><span data-stu-id="66606-114">You can combine multiple expressions in a `Where` clause by using logical operators such as `And`, `Or`, `AndAlso`, `OrElse`, `Is`, and `IsNot`.</span></span>  
  
 <span data-ttu-id="66606-115">既定では、アクセスされるまでクエリ式は評価されません-たとえばがのときにデータ バインドまたはで反復されたり、`For`ループします。</span><span class="sxs-lookup"><span data-stu-id="66606-115">By default, query expressions are not evaluated until they are accessed—for example, when they are data-bound or iterated through in a `For` loop.</span></span> <span data-ttu-id="66606-116">結果として、`Where`句は、クエリがアクセスされるまでは評価されません。</span><span class="sxs-lookup"><span data-stu-id="66606-116">As a result, the `Where` clause is not evaluated until the query is accessed.</span></span> <span data-ttu-id="66606-117">外部で使用されるクエリに値があるかどうか、`Where`句で、適切な値が使用されるように、`Where`句、クエリの実行時にします。</span><span class="sxs-lookup"><span data-stu-id="66606-117">If you have values external to the query that are used in the `Where` clause, ensure that the appropriate value is used in the `Where` clause at the time the query is executed.</span></span> <span data-ttu-id="66606-118">クエリの実行の詳細については、次を参照してください。[書き込みで初めて Your の LINQ クエリ](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md)します。</span><span class="sxs-lookup"><span data-stu-id="66606-118">For more information about query execution, see [Writing Your First LINQ Query](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).</span></span>  
  
 <span data-ttu-id="66606-119">内の関数を呼び出すことができます、`Where`句をコレクション内の現在の要素から計算または値に対して操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="66606-119">You can call functions within a `Where` clause to perform a calculation or operation on a value from the current element in the collection.</span></span> <span data-ttu-id="66606-120">関数を呼び出して、`Where`句アクセスされた場合の代わりに定義がときにすぐに実行するクエリが発生することができます。</span><span class="sxs-lookup"><span data-stu-id="66606-120">Calling a function in a `Where` clause can cause the query to be executed immediately when it is defined instead of when it is accessed.</span></span> <span data-ttu-id="66606-121">クエリの実行の詳細については、次を参照してください。[書き込みで初めて Your の LINQ クエリ](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md)します。</span><span class="sxs-lookup"><span data-stu-id="66606-121">For more information about query execution, see [Writing Your First LINQ Query](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="66606-122">例</span><span class="sxs-lookup"><span data-stu-id="66606-122">Example</span></span>  
 <span data-ttu-id="66606-123">次のクエリ式は、`From`範囲変数を宣言する句`cust`各`Customer`オブジェクト、`customers`コレクション。</span><span class="sxs-lookup"><span data-stu-id="66606-123">The following query expression uses a `From` clause to declare a range variable `cust` for each `Customer` object in the `customers` collection.</span></span> <span data-ttu-id="66606-124">`Where`句では、範囲変数を使用して、指定されたリージョンからお客様に、出力を制限します。</span><span class="sxs-lookup"><span data-stu-id="66606-124">The `Where` clause uses the range variable to restrict the output to customers from the specified region.</span></span> <span data-ttu-id="66606-125">`For Each`ループは、クエリ結果の各顧客の会社名を表示します。</span><span class="sxs-lookup"><span data-stu-id="66606-125">The `For Each` loop displays the company name for each customer in the query result.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#23)]  
  
## <a name="example"></a><span data-ttu-id="66606-126">例</span><span class="sxs-lookup"><span data-stu-id="66606-126">Example</span></span>  
 <span data-ttu-id="66606-127">次の例では`And`と`Or`の論理演算子、`Where`句。</span><span class="sxs-lookup"><span data-stu-id="66606-127">The following example uses `And` and `Or` logical operators in the `Where` clause.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#31)]  
  
## <a name="see-also"></a><span data-ttu-id="66606-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="66606-128">See also</span></span>

- [<span data-ttu-id="66606-129">Visual Basic における LINQ の概要</span><span class="sxs-lookup"><span data-stu-id="66606-129">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="66606-130">クエリ</span><span class="sxs-lookup"><span data-stu-id="66606-130">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="66606-131">From 句</span><span class="sxs-lookup"><span data-stu-id="66606-131">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="66606-132">Select 句</span><span class="sxs-lookup"><span data-stu-id="66606-132">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="66606-133">For Each...Next ステートメント</span><span class="sxs-lookup"><span data-stu-id="66606-133">For Each...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
