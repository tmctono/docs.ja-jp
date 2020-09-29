---
title: LINQ クエリ操作での型の関係 (C#)
description: LINQ クエリの変数の型が相互に関連するしくみについて説明します。 LINQ クエリ操作は、データ ソース、クエリ、および実行において厳密に型指定されます。
ms.date: 07/20/2015
helpviewer_keywords:
- inferring type information [LINQ in C#]
- data sources [LINQ in C#], type relationships
- queries [LINQ in C#], type relationships
- relationships [LINQ in C#]
- type relationships [LINQ in C#]
- variable relationships [LINQ in C#]
- type information inferred [LINQ in C#]
- data transformations [LINQ in C#]
- LINQ [C#], type relationships
ms.assetid: 99118938-d47c-4d7e-bb22-2657a9f95268
ms.openlocfilehash: 78cdb550e59bc82386d34f0e2bf6b1cae11d72de
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203983"
---
# <a name="type-relationships-in-linq-query-operations-c"></a><span data-ttu-id="ede3d-104">LINQ クエリ操作での型の関係 (C#)</span><span class="sxs-lookup"><span data-stu-id="ede3d-104">Type Relationships in LINQ Query Operations (C#)</span></span>

<span data-ttu-id="ede3d-105">クエリを効果的に記述するには、クエリ操作全体における変数の型の相互関係を理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ede3d-105">To write queries effectively, you should understand how types of the variables in a complete query operation all relate to each other.</span></span> <span data-ttu-id="ede3d-106">これらの関係を理解しておくと、このドキュメント内の LINQ のサンプルやコード例を理解しやすくなります。</span><span class="sxs-lookup"><span data-stu-id="ede3d-106">If you understand these relationships you will more easily comprehend the LINQ samples and code examples in the documentation.</span></span> <span data-ttu-id="ede3d-107">また、`var` を使用して変数を暗黙的に型指定した場合に、背後でどのような処理が行われるかを理解することもできます。</span><span class="sxs-lookup"><span data-stu-id="ede3d-107">Furthermore, you will understand what occurs behind the scenes when variables are implicitly typed by using `var`.</span></span>  
  
 <span data-ttu-id="ede3d-108">LINQ クエリ操作は、データ ソース、クエリ自体、およびクエリの実行において厳密に型指定されます。</span><span class="sxs-lookup"><span data-stu-id="ede3d-108">LINQ query operations are strongly typed in the data source, in the query itself, and in the query execution.</span></span> <span data-ttu-id="ede3d-109">クエリの変数の型には、データ ソース内の要素の型および `foreach` ステートメントの反復変数の型との互換性が必要です。</span><span class="sxs-lookup"><span data-stu-id="ede3d-109">The type of the variables in the query must be compatible with the type of the elements in the data source and with the type of the iteration variable in the `foreach` statement.</span></span> <span data-ttu-id="ede3d-110">この厳密な型指定により、コンパイル時に型のエラーが検出され、実際にエラーが発生する前にそのエラーを修正できます。</span><span class="sxs-lookup"><span data-stu-id="ede3d-110">This strong typing guarantees that type errors are caught at compile time when they can be corrected before users encounter them.</span></span>  
  
 <span data-ttu-id="ede3d-111">これらの型の関係を示すために、後の例の大部分では、すべての変数に明示的な型指定を使用しています。</span><span class="sxs-lookup"><span data-stu-id="ede3d-111">In order to demonstrate these type relationships, most of the examples that follow use explicit typing for all variables.</span></span> <span data-ttu-id="ede3d-112">最後の例では、[var](../../../language-reference/keywords/var.md) を使用して暗黙的な型指定を行う場合でも、同じ基本原則が適用されることを示します。</span><span class="sxs-lookup"><span data-stu-id="ede3d-112">The last example shows how the same principles apply even when you use implicit typing by using [var](../../../language-reference/keywords/var.md).</span></span>  
  
## <a name="queries-that-do-not-transform-the-source-data"></a><span data-ttu-id="ede3d-113">ソース データを変換しないクエリ</span><span class="sxs-lookup"><span data-stu-id="ede3d-113">Queries that do not Transform the Source Data</span></span>  

 <span data-ttu-id="ede3d-114">次の図は、データの変換を行わない LINQ to Objects クエリ操作を示しています。</span><span class="sxs-lookup"><span data-stu-id="ede3d-114">The following illustration shows a LINQ to Objects query operation that performs no transformations on the data.</span></span> <span data-ttu-id="ede3d-115">ソースには文字列のシーケンスが含まれているので、クエリ出力も文字列のシーケンスです。</span><span class="sxs-lookup"><span data-stu-id="ede3d-115">The source contains a sequence of strings and the query output is also a sequence of strings.</span></span>  
  
 ![LINQ クエリ内のデータ型の関係を示す図。](./media/type-relationships-in-linq-query-operations/linq-query-data-type-relation.png)  
  
1. <span data-ttu-id="ede3d-117">データ ソースの型引数によって、範囲変数の型が決まります。</span><span class="sxs-lookup"><span data-stu-id="ede3d-117">The type argument of the data source determines the type of the range variable.</span></span>  
  
2. <span data-ttu-id="ede3d-118">選択したオブジェクトの型によって、クエリ変数の型が決まります。</span><span class="sxs-lookup"><span data-stu-id="ede3d-118">The type of the object that is selected determines the type of the query variable.</span></span> <span data-ttu-id="ede3d-119">ここでは、`name` は文字列です。</span><span class="sxs-lookup"><span data-stu-id="ede3d-119">Here `name` is a string.</span></span> <span data-ttu-id="ede3d-120">したがって、クエリ変数は `IEnumerable<string>` になります。</span><span class="sxs-lookup"><span data-stu-id="ede3d-120">Therefore, the query variable is an `IEnumerable<string>`.</span></span>  
  
3. <span data-ttu-id="ede3d-121">クエリ変数は、`foreach` ステートメントで反復処理されます。</span><span class="sxs-lookup"><span data-stu-id="ede3d-121">The query variable is iterated over in the `foreach` statement.</span></span> <span data-ttu-id="ede3d-122">クエリ変数は文字列のシーケンスなので、反復変数も文字列です。</span><span class="sxs-lookup"><span data-stu-id="ede3d-122">Because the query variable is a sequence of strings, the iteration variable is also a string.</span></span>  
  
## <a name="queries-that-transform-the-source-data"></a><span data-ttu-id="ede3d-123">ソース データを変換するクエリ</span><span class="sxs-lookup"><span data-stu-id="ede3d-123">Queries that Transform the Source Data</span></span>  

 <span data-ttu-id="ede3d-124">次の図は、単純なデータ変換を行う [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] クエリ操作を示しています。</span><span class="sxs-lookup"><span data-stu-id="ede3d-124">The following illustration shows a [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] query operation that performs a simple transformation on the data.</span></span> <span data-ttu-id="ede3d-125">このクエリは、`Customer` オブジェクトのシーケンスを入力として受け取り、`Name` プロパティのみを結果に選択します。</span><span class="sxs-lookup"><span data-stu-id="ede3d-125">The query takes a sequence of `Customer` objects as input, and selects only the `Name` property in the result.</span></span> <span data-ttu-id="ede3d-126">`Name` は文字列なので、クエリは出力として文字列のシーケンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="ede3d-126">Because `Name` is a string, the query produces a sequence of strings as output.</span></span>  
  
 ![データ型を変換するクエリを示す図。](./media/type-relationships-in-linq-query-operations/linq-query-transform-data-type.png)  
  
1. <span data-ttu-id="ede3d-128">データ ソースの型引数によって、範囲変数の型が決まります。</span><span class="sxs-lookup"><span data-stu-id="ede3d-128">The type argument of the data source determines the type of the range variable.</span></span>  
  
2. <span data-ttu-id="ede3d-129">`select` ステートメントは、完全な `Name` オブジェクトではなく、`Customer` プロパティを返します。</span><span class="sxs-lookup"><span data-stu-id="ede3d-129">The `select` statement returns the `Name` property instead of the complete `Customer` object.</span></span> <span data-ttu-id="ede3d-130">`Name` は文字列なので、`custNameQuery` の型引数は `string` ではなく `Customer` になります。</span><span class="sxs-lookup"><span data-stu-id="ede3d-130">Because `Name` is a string, the type argument of `custNameQuery` is `string`, not `Customer`.</span></span>  
  
3. <span data-ttu-id="ede3d-131">`custNameQuery` は文字列のシーケンスなので、`foreach` ループの反復変数も `string` です。</span><span class="sxs-lookup"><span data-stu-id="ede3d-131">Because `custNameQuery` is a sequence of strings, the `foreach` loop's iteration variable must also be a `string`.</span></span>  
  
 <span data-ttu-id="ede3d-132">次の図は、もう少し複雑な変換を示しています。</span><span class="sxs-lookup"><span data-stu-id="ede3d-132">The following illustration shows a slightly more complex transformation.</span></span> <span data-ttu-id="ede3d-133">`select` ステートメントは、元の `Customer` オブジェクトのメンバーを 2 つだけ取り込む匿名型を返します。</span><span class="sxs-lookup"><span data-stu-id="ede3d-133">The `select` statement returns an anonymous type that captures just two members of the original `Customer` object.</span></span>  
  
 ![データ型を変換するより複雑なクエリを示す図。](./media/type-relationships-in-linq-query-operations/linq-complex-query-transform-data-type.png)  
  
1. <span data-ttu-id="ede3d-135">データ ソースの型引数は、常にクエリの範囲変数の型です。</span><span class="sxs-lookup"><span data-stu-id="ede3d-135">The type argument of the data source is always the type of the range variable in the query.</span></span>  
  
2. <span data-ttu-id="ede3d-136">`select` ステートメントによって匿名型が生成されるため、クエリ変数は `var` を使用して暗黙的に型指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ede3d-136">Because the `select` statement produces an anonymous type, the query variable must be implicitly typed by using `var`.</span></span>  
  
3. <span data-ttu-id="ede3d-137">クエリ変数の型が暗黙的なので、`foreach` ループの反復変数も暗黙的にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ede3d-137">Because the type of the query variable is implicit, the iteration variable in the `foreach` loop must also be implicit.</span></span>  
  
## <a name="letting-the-compiler-infer-type-information"></a><span data-ttu-id="ede3d-138">コンパイラによる型情報の推論</span><span class="sxs-lookup"><span data-stu-id="ede3d-138">Letting the compiler infer type information</span></span>  

 <span data-ttu-id="ede3d-139">クエリ操作における変数の関係を理解することは大切ですが、この処理をコンパイラで自動的に行う方法もあります。</span><span class="sxs-lookup"><span data-stu-id="ede3d-139">Although you should understand the type relationships in a query operation, you have the option to let the compiler do all the work for you.</span></span> <span data-ttu-id="ede3d-140">[var](../../../language-reference/keywords/var.md) キーワードは、クエリ操作の任意のローカル変数に使用できます。</span><span class="sxs-lookup"><span data-stu-id="ede3d-140">The keyword [var](../../../language-reference/keywords/var.md) can be used for any local variable in a query operation.</span></span> <span data-ttu-id="ede3d-141">次の図は、前に説明した例 2 と類似しています。</span><span class="sxs-lookup"><span data-stu-id="ede3d-141">The following illustration is similar to example number 2 that was discussed earlier.</span></span> <span data-ttu-id="ede3d-142">ここでは、コンパイラがクエリ操作の各変数について、厳密な型を指定します。</span><span class="sxs-lookup"><span data-stu-id="ede3d-142">However, the compiler supplies the strong type for each variable in the query operation.</span></span>  
  
 ![暗黙的な入力による型フローを示す図。](./media/type-relationships-in-linq-query-operations/linq-type-flow-implicit-typing.png)  
  
 <span data-ttu-id="ede3d-144">`var` の詳細については、「[暗黙的に型指定されたローカル変数](../../classes-and-structs/implicitly-typed-local-variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ede3d-144">For more information about `var`, see [Implicitly Typed Local Variables](../../classes-and-structs/implicitly-typed-local-variables.md).</span></span>  
