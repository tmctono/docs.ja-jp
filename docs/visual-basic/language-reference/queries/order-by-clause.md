---
title: Order By 句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryOrderBy
- vb.QueryAscending
- vb.QueryDescending
helpviewer_keywords:
- queries [Visual Basic], Order By
- Order By clause [Visual Basic]
- Order By statement [Visual Basic]
ms.assetid: fa911282-6b81-44c7-acfa-46b5bb93df75
ms.openlocfilehash: f8ee46b12e84f99629c3a92057fc3a7bb8a3c2e8
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004955"
---
# <a name="order-by-clause-visual-basic"></a><span data-ttu-id="b9301-102">Order By 句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b9301-102">Order By Clause (Visual Basic)</span></span>
<span data-ttu-id="b9301-103">クエリ結果の並べ替え順序を指定します。</span><span class="sxs-lookup"><span data-stu-id="b9301-103">Specifies the sort order for a query result.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9301-104">構文</span><span class="sxs-lookup"><span data-stu-id="b9301-104">Syntax</span></span>  
  
```vb  
Order By orderExp1 [ Ascending | Descending ] [, orderExp2 [...] ]  
```  
  
## <a name="parts"></a><span data-ttu-id="b9301-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="b9301-105">Parts</span></span>  
 `orderExp1`  
 <span data-ttu-id="b9301-106">必須。</span><span class="sxs-lookup"><span data-stu-id="b9301-106">Required.</span></span> <span data-ttu-id="b9301-107">返された値の順序付け方法を示す、現在のクエリ結果の1つまたは複数のフィールド。</span><span class="sxs-lookup"><span data-stu-id="b9301-107">One or more fields from the current query result that identify how to order the returned values.</span></span> <span data-ttu-id="b9301-108">フィールド名は、コンマ (,) で区切る必要があります。</span><span class="sxs-lookup"><span data-stu-id="b9301-108">The field names must be separated by commas (,).</span></span> <span data-ttu-id="b9301-109">`Ascending` または `Descending` キーワードを使用して、昇順または降順で並べ替えられた各フィールドを識別できます。</span><span class="sxs-lookup"><span data-stu-id="b9301-109">You can identify each field as sorted in ascending or descending order by using the `Ascending` or `Descending` keywords.</span></span> <span data-ttu-id="b9301-110">`Ascending` または `Descending` キーワードが指定されていない場合、既定の並べ替え順序は昇順です。</span><span class="sxs-lookup"><span data-stu-id="b9301-110">If no `Ascending` or `Descending` keyword is specified, the default sort order is ascending.</span></span> <span data-ttu-id="b9301-111">並べ替え順序のフィールドは、左から右に優先されます。</span><span class="sxs-lookup"><span data-stu-id="b9301-111">The sort order fields are given precedence from left to right.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b9301-112">コメント</span><span class="sxs-lookup"><span data-stu-id="b9301-112">Remarks</span></span>  
 <span data-ttu-id="b9301-113">`Order By` 句を使用して、クエリの結果を並べ替えることができます。</span><span class="sxs-lookup"><span data-stu-id="b9301-113">You can use the `Order By` clause to sort the results of a query.</span></span> <span data-ttu-id="b9301-114">`Order By` 句では、現在のスコープの範囲変数に基づいてのみ結果を並べ替えることができます。</span><span class="sxs-lookup"><span data-stu-id="b9301-114">The `Order By` clause can only sort a result based on the range variable for the current scope.</span></span> <span data-ttu-id="b9301-115">たとえば、`Select` 句では、クエリ式に新しいスコープを追加し、そのスコープに新しいイテレーション変数を指定します。</span><span class="sxs-lookup"><span data-stu-id="b9301-115">For example, the `Select` clause introduces a new scope in a query expression with new iteration variables for that scope.</span></span> <span data-ttu-id="b9301-116">クエリ内の `Select` 句の前に定義された範囲変数は、`Select` 句の後では使用できません。</span><span class="sxs-lookup"><span data-stu-id="b9301-116">Range variables defined before a `Select` clause in a query are not available after the `Select` clause.</span></span> <span data-ttu-id="b9301-117">したがって、`Select` 句で使用できないフィールドで結果を並べ替える場合は、`Order By` 句を `Select` 句の前に配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b9301-117">Therefore, if you want to order your results by a field that is not available in the `Select` clause, you must put the `Order By` clause before the `Select` clause.</span></span> <span data-ttu-id="b9301-118">これを行う必要がある場合の1つの例は、結果の一部として返されないフィールドによってクエリを並べ替える場合です。</span><span class="sxs-lookup"><span data-stu-id="b9301-118">One example of when you would have to do this is when you want to sort your query by fields that are not returned as part of the result.</span></span>  
  
 <span data-ttu-id="b9301-119">フィールドの昇順と降順の順序は、フィールドのデータ型の <xref:System.IComparable> インターフェイスの実装によって決定されます。</span><span class="sxs-lookup"><span data-stu-id="b9301-119">Ascending and descending order for a field is determined by the implementation of the <xref:System.IComparable> interface for the data type of the field.</span></span> <span data-ttu-id="b9301-120">データ型に <xref:System.IComparable> インターフェイスが実装されていない場合、並べ替え順序は無視されます。</span><span class="sxs-lookup"><span data-stu-id="b9301-120">If the data type does not implement the <xref:System.IComparable> interface, the sort order is ignored.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b9301-121">例</span><span class="sxs-lookup"><span data-stu-id="b9301-121">Example</span></span>  
 <span data-ttu-id="b9301-122">次のクエリ式では、`From` 句を使用して、`books` コレクションの範囲変数 `book` を宣言します。</span><span class="sxs-lookup"><span data-stu-id="b9301-122">The following query expression uses a `From` clause to declare a range variable `book` for the `books` collection.</span></span> <span data-ttu-id="b9301-123">`Order By` 句は、クエリの結果を価格で昇順に並べ替えます (既定値)。</span><span class="sxs-lookup"><span data-stu-id="b9301-123">The `Order By` clause sorts the query result by price in ascending order (the default).</span></span> <span data-ttu-id="b9301-124">同じ価格の書籍は、タイトルの昇順で並べ替えられます。</span><span class="sxs-lookup"><span data-stu-id="b9301-124">Books with the same price are sorted by title in ascending order.</span></span> <span data-ttu-id="b9301-125">`Select` 句は、クエリによって返される値として `Title` と `Price` プロパティを選択します。</span><span class="sxs-lookup"><span data-stu-id="b9301-125">The `Select` clause selects the `Title` and `Price` properties as the values returned by the query.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#24)]  
  
## <a name="example"></a><span data-ttu-id="b9301-126">例</span><span class="sxs-lookup"><span data-stu-id="b9301-126">Example</span></span>  
 <span data-ttu-id="b9301-127">次のクエリ式では、`Order By` 句を使用して、クエリ結果を価格で降順に並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="b9301-127">The following query expression uses the `Order By` clause to sort the query result by price in descending order.</span></span> <span data-ttu-id="b9301-128">同じ価格の書籍は、タイトルの昇順で並べ替えられます。</span><span class="sxs-lookup"><span data-stu-id="b9301-128">Books with the same price are sorted by title in ascending order.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#25)]  
  
## <a name="example"></a><span data-ttu-id="b9301-129">例</span><span class="sxs-lookup"><span data-stu-id="b9301-129">Example</span></span>  
 <span data-ttu-id="b9301-130">次のクエリ式では、`Select` 句を使用して、書籍のタイトル、価格、発行日、および作成者を選択します。</span><span class="sxs-lookup"><span data-stu-id="b9301-130">The following query expression uses a `Select` clause to select the book title, price, publish date, and author.</span></span> <span data-ttu-id="b9301-131">次に、新しいスコープの範囲変数の `Title`、`Price`、`PublishDate`、および `Author` の各フィールドを設定します。</span><span class="sxs-lookup"><span data-stu-id="b9301-131">It then populates the `Title`, `Price`, `PublishDate`, and `Author` fields of the range variable for the new scope.</span></span> <span data-ttu-id="b9301-132">`Order By` 句は、作成者名、書籍のタイトル、価格で新しい範囲変数を並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="b9301-132">The `Order By` clause orders the new range variable by author name, book title, and then price.</span></span> <span data-ttu-id="b9301-133">各列は、既定の順序 (昇順) で並べ替えられます。</span><span class="sxs-lookup"><span data-stu-id="b9301-133">Each column is sorted in the default order (ascending).</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#26)]  
  
## <a name="see-also"></a><span data-ttu-id="b9301-134">参照</span><span class="sxs-lookup"><span data-stu-id="b9301-134">See also</span></span>

- [<span data-ttu-id="b9301-135">Visual Basic における LINQ の概要</span><span class="sxs-lookup"><span data-stu-id="b9301-135">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="b9301-136">クエリ</span><span class="sxs-lookup"><span data-stu-id="b9301-136">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="b9301-137">Select 句</span><span class="sxs-lookup"><span data-stu-id="b9301-137">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="b9301-138">From 句</span><span class="sxs-lookup"><span data-stu-id="b9301-138">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
