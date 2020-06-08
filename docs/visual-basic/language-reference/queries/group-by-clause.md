---
title: Group By 句
ms.date: 07/20/2015
f1_keywords:
- vb.QueryGroupByInto
- vb.QueryGroupBy
- vb.QueryGroupRef
- vb.QueryGroupInto
- vb.QueryGroup
helpviewer_keywords:
- queries [Visual Basic], Group By
- Group By statement [Visual Basic]
- Group By clause [Visual Basic]
ms.assetid: b1b5dcea-6654-473b-a2db-01f7e4c265d7
ms.openlocfilehash: 5fce4f818e22373de7f1b37b941fd88155f3a33f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84359891"
---
# <a name="group-by-clause-visual-basic"></a><span data-ttu-id="765de-102">Group By 句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="765de-102">Group By Clause (Visual Basic)</span></span>
<span data-ttu-id="765de-103">クエリ結果の要素をグループ化します。</span><span class="sxs-lookup"><span data-stu-id="765de-103">Groups the elements of a query result.</span></span> <span data-ttu-id="765de-104">これを使用して、グループごとに集計関数を適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="765de-104">Can also be used to apply aggregate functions to each group.</span></span> <span data-ttu-id="765de-105">グループ化操作は、1 つ以上のキーに基づきます。</span><span class="sxs-lookup"><span data-stu-id="765de-105">The grouping operation is based on one or more keys.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="765de-106">構文</span><span class="sxs-lookup"><span data-stu-id="765de-106">Syntax</span></span>  
  
```vb  
Group [ listField1 [, listField2 [...] ] By keyExp1 [, keyExp2 [...] ]  
  Into aggregateList  
```  
  
## <a name="parts"></a><span data-ttu-id="765de-107">指定項目</span><span class="sxs-lookup"><span data-stu-id="765de-107">Parts</span></span>  
  
- <span data-ttu-id="765de-108">`listField1`、`listField2`</span><span class="sxs-lookup"><span data-stu-id="765de-108">`listField1`, `listField2`</span></span>  
  
     <span data-ttu-id="765de-109">任意。</span><span class="sxs-lookup"><span data-stu-id="765de-109">Optional.</span></span> <span data-ttu-id="765de-110">グループ化された結果に含めるフィールドを明示的に示す、クエリ変数の 1 つ以上のフィールドです。</span><span class="sxs-lookup"><span data-stu-id="765de-110">One or more fields of the query variable or variables that explicitly identify the fields to be included in the grouped result.</span></span> <span data-ttu-id="765de-111">フィールドを指定しない場合、グループ化された結果にはクエリ変数のすべてのフィールドが含まれます。</span><span class="sxs-lookup"><span data-stu-id="765de-111">If no fields are specified, all fields of the query variable or variables are included in the grouped result.</span></span>  
  
- `keyExp1`  
  
     <span data-ttu-id="765de-112">必須です。</span><span class="sxs-lookup"><span data-stu-id="765de-112">Required.</span></span> <span data-ttu-id="765de-113">要素のグループを決定するために使用するキーを識別する式です。</span><span class="sxs-lookup"><span data-stu-id="765de-113">An expression that identifies the key to use to determine the groups of elements.</span></span> <span data-ttu-id="765de-114">複数のキーを指定して、複合キーを指定できます。</span><span class="sxs-lookup"><span data-stu-id="765de-114">You can specify more than one key to specify a composite key.</span></span>  
  
- `keyExp2`  
  
     <span data-ttu-id="765de-115">任意。</span><span class="sxs-lookup"><span data-stu-id="765de-115">Optional.</span></span> <span data-ttu-id="765de-116">`keyExp1` と結合して複合キーを作成する 1 つ以上の追加キーです。</span><span class="sxs-lookup"><span data-stu-id="765de-116">One or more additional keys that are combined with `keyExp1` to create a composite key.</span></span>  
  
- `aggregateList`  
  
     <span data-ttu-id="765de-117">必須です。</span><span class="sxs-lookup"><span data-stu-id="765de-117">Required.</span></span> <span data-ttu-id="765de-118">グループの集計方法を示す 1 つ以上の式です。</span><span class="sxs-lookup"><span data-stu-id="765de-118">One or more expressions that identify how the groups are aggregated.</span></span> <span data-ttu-id="765de-119">グループ化された結果のメンバー名を示すには、次のいずれかの形式で、 `Group` キーワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="765de-119">To identify a member name for the grouped results, use the `Group` keyword, which can be in either of the following forms:</span></span>  
  
    ```vb  
    Into Group  
    ```  
  
     <span data-ttu-id="765de-120">\- または -</span><span class="sxs-lookup"><span data-stu-id="765de-120">-or-</span></span>  
  
    ```vb  
    Into <alias> = Group  
    ```  
  
     <span data-ttu-id="765de-121">グループに適用する集計関数を含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="765de-121">You can also include aggregate functions to apply to the group.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="765de-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="765de-122">Remarks</span></span>  
 <span data-ttu-id="765de-123">`Group By` 句を使用して、クエリの結果をグループに分割できます。</span><span class="sxs-lookup"><span data-stu-id="765de-123">You can use the `Group By` clause to break the results of a query into groups.</span></span> <span data-ttu-id="765de-124">グループ化は、1 つのキー、または複数のキーで構成される複合キーに基づいて行われます。</span><span class="sxs-lookup"><span data-stu-id="765de-124">The grouping is based on a key or a composite key consisting of multiple keys.</span></span> <span data-ttu-id="765de-125">一致するキー値と関連付けられた要素は、同じグループに入れられます。</span><span class="sxs-lookup"><span data-stu-id="765de-125">Elements that are associated with matching key values are included in the same group.</span></span>  
  
 <span data-ttu-id="765de-126">グループの参照に使用するメンバー名を示すには、 `aggregateList` 句の `Into` パラメーターと `Group` キーワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="765de-126">You use the `aggregateList` parameter of the `Into` clause and the `Group` keyword to identify the member name that is used to reference the group.</span></span> <span data-ttu-id="765de-127">`Into` 句に集計関数を含めることで、グループ化された要素の値を計算することもできます。</span><span class="sxs-lookup"><span data-stu-id="765de-127">You can also include aggregate functions in the `Into` clause to compute values for the grouped elements.</span></span> <span data-ttu-id="765de-128">標準的な集計関数の一覧については、「 [Aggregate Clause](aggregate-clause.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="765de-128">For a list of standard aggregate functions, see [Aggregate Clause](aggregate-clause.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="765de-129">例</span><span class="sxs-lookup"><span data-stu-id="765de-129">Example</span></span>  
 <span data-ttu-id="765de-130">以下のコード例では、場所 (国/地域) に基づいて顧客の一覧をグループ化し、各グループ内の顧客の数を返します。</span><span class="sxs-lookup"><span data-stu-id="765de-130">The following code example groups a list of customers based on their location (country/region) and provides a count of the customers in each group.</span></span> <span data-ttu-id="765de-131">結果は、国/地域名によって並べ替えられます。</span><span class="sxs-lookup"><span data-stu-id="765de-131">The results are ordered by country/region name.</span></span> <span data-ttu-id="765de-132">グループ化した結果は、市区町村名によって並べ替えられます。</span><span class="sxs-lookup"><span data-stu-id="765de-132">The grouped results are ordered by city name.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="765de-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="765de-133">See also</span></span>

- [<span data-ttu-id="765de-134">Visual Basic における LINQ の概要</span><span class="sxs-lookup"><span data-stu-id="765de-134">Introduction to LINQ in Visual Basic</span></span>](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="765de-135">クエリ</span><span class="sxs-lookup"><span data-stu-id="765de-135">Queries</span></span>](index.md)
- [<span data-ttu-id="765de-136">Select 句</span><span class="sxs-lookup"><span data-stu-id="765de-136">Select Clause</span></span>](select-clause.md)
- [<span data-ttu-id="765de-137">From 句</span><span class="sxs-lookup"><span data-stu-id="765de-137">From Clause</span></span>](from-clause.md)
- [<span data-ttu-id="765de-138">Order By 句</span><span class="sxs-lookup"><span data-stu-id="765de-138">Order By Clause</span></span>](order-by-clause.md)
- [<span data-ttu-id="765de-139">Aggregate 句</span><span class="sxs-lookup"><span data-stu-id="765de-139">Aggregate Clause</span></span>](aggregate-clause.md)
- [<span data-ttu-id="765de-140">Group Join 句</span><span class="sxs-lookup"><span data-stu-id="765de-140">Group Join Clause</span></span>](group-join-clause.md)
