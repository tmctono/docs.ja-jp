---
title: Select 句
ms.date: 07/20/2015
f1_keywords:
- vb.QuerySelect
helpviewer_keywords:
- Select statement [Visual Basic]
- Select clause [Visual Basic]
- queries [Visual Basic], Select
ms.assetid: 27a3f61c-5960-4692-9b91-4d0c4b6178fe
ms.openlocfilehash: d96423efbee075a7ad257df72471c71e38e09b63
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "90875741"
---
# <a name="select-clause-visual-basic"></a><span data-ttu-id="da374-102">Select 句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="da374-102">Select Clause (Visual Basic)</span></span>

<span data-ttu-id="da374-103">クエリの結果を定義します。</span><span class="sxs-lookup"><span data-stu-id="da374-103">Defines the result of a query.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da374-104">構文</span><span class="sxs-lookup"><span data-stu-id="da374-104">Syntax</span></span>  
  
```vb  
Select [ var1 = ] fieldName1 [, [ var2 = ] fieldName2 [...] ]  
```  
  
## <a name="parts"></a><span data-ttu-id="da374-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="da374-105">Parts</span></span>  

 `var1`  
 <span data-ttu-id="da374-106">任意。</span><span class="sxs-lookup"><span data-stu-id="da374-106">Optional.</span></span> <span data-ttu-id="da374-107">列式の結果を参照するために使用できる別名。</span><span class="sxs-lookup"><span data-stu-id="da374-107">An alias that can be used to reference the results of the column expression.</span></span>  
  
 `fieldName1`  
 <span data-ttu-id="da374-108">必須です。</span><span class="sxs-lookup"><span data-stu-id="da374-108">Required.</span></span> <span data-ttu-id="da374-109">クエリ結果に返されるフィールドの名前。</span><span class="sxs-lookup"><span data-stu-id="da374-109">The name of the field to return in the query result.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="da374-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="da374-110">Remarks</span></span>  

 <span data-ttu-id="da374-111">`Select` 句を使用して、クエリから返される結果を定義できます。</span><span class="sxs-lookup"><span data-stu-id="da374-111">You can use the `Select` clause to define the results to return from a query.</span></span> <span data-ttu-id="da374-112">これにより、クエリによって作成された新しい匿名型のメンバーを定義することも、クエリによって返される名前付きの型のメンバーを対象にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="da374-112">This enables you to either define the members of a new anonymous type that is created by a query, or to target the members of a named type that is returned by a query.</span></span> <span data-ttu-id="da374-113">`Select` 句は、クエリには必要ありません。</span><span class="sxs-lookup"><span data-stu-id="da374-113">The `Select` clause is not required for a query.</span></span> <span data-ttu-id="da374-114">`Select` 句が指定されていない場合、クエリは、現在のスコープで識別される範囲変数のすべてのメンバーに基づいて型を返します。</span><span class="sxs-lookup"><span data-stu-id="da374-114">If no `Select` clause is specified, the query will return a type based on all members of the range variables identified for the current scope.</span></span> <span data-ttu-id="da374-115">詳細については、「[匿名型](../../programming-guide/language-features/objects-and-classes/anonymous-types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="da374-115">For more information, see [Anonymous Types](../../programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span> <span data-ttu-id="da374-116">クエリで名前付きの型を作成すると、型 <xref:System.Collections.Generic.IEnumerable%601> の結果が返されます。ここで `T` は作成された型です。</span><span class="sxs-lookup"><span data-stu-id="da374-116">When a query creates a named type, it will return a result of type <xref:System.Collections.Generic.IEnumerable%601> where `T` is the created type.</span></span>  
  
 <span data-ttu-id="da374-117">`Select` 句は、現在のスコープ内の任意の変数を参照できます。</span><span class="sxs-lookup"><span data-stu-id="da374-117">The `Select` clause can reference any variables in the current scope.</span></span> <span data-ttu-id="da374-118">これには、`From` 句 (または `From` 句) で識別される範囲変数が含まれます。</span><span class="sxs-lookup"><span data-stu-id="da374-118">This includes range variables identified in the `From` clause (or `From` clauses).</span></span> <span data-ttu-id="da374-119">また、`Aggregate`、`Let`、`Group By`、`Group Join` の各句による別名で作成された新しい変数、またはクエリ式の前の `Select` 句からの変数も含まれます。</span><span class="sxs-lookup"><span data-stu-id="da374-119">It also includes any new variables created with an alias by the `Aggregate`, `Let`, `Group By`, or `Group Join` clauses, or variables from a previous `Select` clause in the query expression.</span></span> <span data-ttu-id="da374-120">また、`Select` 句には静的な値を含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="da374-120">The `Select` clause can also include static values.</span></span> <span data-ttu-id="da374-121">たとえば、次のコード例は、`Select` 句で `ProductName`、`Price`、`Discount`、および `DiscountedPrice` の 4 つのメンバーを持つ新しい匿名型としてクエリ結果を定義するクエリ式を示しています。</span><span class="sxs-lookup"><span data-stu-id="da374-121">For example, the following code example shows a query expression in which the `Select` clause defines the query result as a new anonymous type with four members: `ProductName`, `Price`, `Discount`, and `DiscountedPrice`.</span></span> <span data-ttu-id="da374-122">`ProductName` メンバーと `Price` メンバーの値は、`From` 句で定義されている製品の範囲変数から取得されます。</span><span class="sxs-lookup"><span data-stu-id="da374-122">The `ProductName` and `Price` member values are taken from the product range variable that is defined in the `From` clause.</span></span> <span data-ttu-id="da374-123">`DiscountedPrice` メンバーの値は、`Let` 句で計算されます。</span><span class="sxs-lookup"><span data-stu-id="da374-123">The `DiscountedPrice` member value is calculated in the `Let` clause.</span></span> <span data-ttu-id="da374-124">`Discount` メンバーは静的な値です。</span><span class="sxs-lookup"><span data-stu-id="da374-124">The `Discount` member is a static value.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#27)]  
  
 <span data-ttu-id="da374-125">`Select` 句には、後続のクエリ句の範囲変数の新しいセットが導入され、以前の範囲変数はスコープに含まれなくなりました。</span><span class="sxs-lookup"><span data-stu-id="da374-125">The `Select` clause introduces a new set of range variables for subsequent query clauses, and previous range variables are no longer in scope.</span></span> <span data-ttu-id="da374-126">クエリ式の最後の `Select` 句によって、クエリの戻り値が決まります。</span><span class="sxs-lookup"><span data-stu-id="da374-126">The last `Select` clause in a query expression determines the return value of the query.</span></span> <span data-ttu-id="da374-127">たとえば、次のクエリでは、合計が 500 を超えるすべての顧客の注文の会社名と注文 ID が返されます。</span><span class="sxs-lookup"><span data-stu-id="da374-127">For example, the following query returns the company name and order ID for every customer order for which the total exceeds 500.</span></span> <span data-ttu-id="da374-128">最初の `Select` 句は、`Where` 句と 2 番目の `Select` 句の範囲変数を識別します。</span><span class="sxs-lookup"><span data-stu-id="da374-128">The first `Select` clause identifies the range variables for the `Where` clause and the second `Select` clause.</span></span> <span data-ttu-id="da374-129">2 番目の `Select` 句は、クエリによって返される値を新しい匿名型として識別します。</span><span class="sxs-lookup"><span data-stu-id="da374-129">The second `Select` clause identifies the values returned by the query as a new anonymous type.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#28)]  
  
 <span data-ttu-id="da374-130">`Select` 句が返される項目を 1 つ識別する場合、クエリ式はその 1 つの項目の型のコレクションを返します。</span><span class="sxs-lookup"><span data-stu-id="da374-130">If the `Select` clause identifies a single item to return, the query expression returns a collection of the type of that single item.</span></span> <span data-ttu-id="da374-131">`Select` 句が返される項目を複数識別する場合、クエリ式は、選択した項目に基づいて、新しい匿名型のコレクションを返します。</span><span class="sxs-lookup"><span data-stu-id="da374-131">If the `Select` clause identifies multiple items to return, the query expression returns a collection of a new anonymous type, based on the selected items.</span></span> <span data-ttu-id="da374-132">たとえば、次の 2 つのクエリは、`Select` 句に基づいて 2 つの異なる型のコレクションを返します。</span><span class="sxs-lookup"><span data-stu-id="da374-132">For example, the following two queries return collections of two different types based on the `Select` clause.</span></span> <span data-ttu-id="da374-133">最初のクエリは、会社名のコレクションを文字列として返します。</span><span class="sxs-lookup"><span data-stu-id="da374-133">The first query returns a collection of company names as strings.</span></span> <span data-ttu-id="da374-134">2 番目のクエリは、会社名と住所情報が入力された `Customer` オブジェクトのコレクションを返します。</span><span class="sxs-lookup"><span data-stu-id="da374-134">The second query returns a collection of `Customer` objects populated with the company names and address information.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#29)]  
  
## <a name="example"></a><span data-ttu-id="da374-135">例</span><span class="sxs-lookup"><span data-stu-id="da374-135">Example</span></span>  

 <span data-ttu-id="da374-136">次のクエリ式では、`From` 句を使用して、`customers` コレクションに対して `cust` 範囲変数を宣言しています。</span><span class="sxs-lookup"><span data-stu-id="da374-136">The following query expression uses a `From` clause to declare a range variable `cust` for the `customers` collection.</span></span> <span data-ttu-id="da374-137">`Select` 句は、顧客名と ID 値を選択し、新しい範囲変数に対して `CompanyName` 列と `CustomerID` 列を設定します。</span><span class="sxs-lookup"><span data-stu-id="da374-137">The `Select` clause selects the customer name and ID value and populates the `CompanyName` and `CustomerID` columns of the new range variable.</span></span> <span data-ttu-id="da374-138">`For Each` ステートメントは、返された各オブジェクトをループし、各レコードの `CompanyName` 列と `CustomerID` 列を表示します。</span><span class="sxs-lookup"><span data-stu-id="da374-138">The `For Each` statement loops over each returned object and displays the `CompanyName` and `CustomerID` columns for each record.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#30)]  
  
## <a name="see-also"></a><span data-ttu-id="da374-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="da374-139">See also</span></span>

- [<span data-ttu-id="da374-140">Visual Basic における LINQ の概要</span><span class="sxs-lookup"><span data-stu-id="da374-140">Introduction to LINQ in Visual Basic</span></span>](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="da374-141">クエリ</span><span class="sxs-lookup"><span data-stu-id="da374-141">Queries</span></span>](index.md)
- [<span data-ttu-id="da374-142">From 句</span><span class="sxs-lookup"><span data-stu-id="da374-142">From Clause</span></span>](from-clause.md)
- [<span data-ttu-id="da374-143">WHERE 句</span><span class="sxs-lookup"><span data-stu-id="da374-143">Where Clause</span></span>](where-clause.md)
- [<span data-ttu-id="da374-144">Order By 句</span><span class="sxs-lookup"><span data-stu-id="da374-144">Order By Clause</span></span>](order-by-clause.md)
- [<span data-ttu-id="da374-145">匿名型</span><span class="sxs-lookup"><span data-stu-id="da374-145">Anonymous Types</span></span>](../../programming-guide/language-features/objects-and-classes/anonymous-types.md)
