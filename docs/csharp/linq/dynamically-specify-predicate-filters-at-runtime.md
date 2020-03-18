---
title: 実行時における述語フィルターの動的指定 (C# での LINQ)
description: C# で LINQ を使用して、実行時に述語フィルターを動的に指定する方法について説明します。
ms.date: 12/01/2016
ms.assetid: 90238470-0767-497c-916c-52d0d16845e0
ms.openlocfilehash: 314be8f98b9ff014f14bef11a1f3581eff8574b4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "61659944"
---
# <a name="dynamically-specify-predicate-filters-at-runtime"></a><span data-ttu-id="e0a5b-103">実行時における述語フィルターの動的指定</span><span class="sxs-lookup"><span data-stu-id="e0a5b-103">Dynamically specify predicate filters at runtime</span></span>

<span data-ttu-id="e0a5b-104">`where` 句のソース要素に適用しなければならない述語の数が実行時までわからない場合があります。</span><span class="sxs-lookup"><span data-stu-id="e0a5b-104">In some cases, you don't know until run time how many predicates you have to apply to source elements in the `where` clause.</span></span> <span data-ttu-id="e0a5b-105">複数の述語フィルターを動的に指定する方法として、次の例のように、<xref:System.Linq.Enumerable.Contains%2A> メソッドを使用する方法があります。</span><span class="sxs-lookup"><span data-stu-id="e0a5b-105">One way to dynamically specify multiple predicate filters is to use the <xref:System.Linq.Enumerable.Contains%2A> method, as shown in the following example.</span></span> <span data-ttu-id="e0a5b-106">この例は 2 段階構築になっています。</span><span class="sxs-lookup"><span data-stu-id="e0a5b-106">The example is constructed in two ways.</span></span> <span data-ttu-id="e0a5b-107">最初に、プログラムで提供される値にフィルターを適用してプログラムを実行します。</span><span class="sxs-lookup"><span data-stu-id="e0a5b-107">First, the project is run by filtering on values that are provided in the program.</span></span> <span data-ttu-id="e0a5b-108">次に、実行時に提供された入力を利用してプログラムをもう一度実行します。</span><span class="sxs-lookup"><span data-stu-id="e0a5b-108">Then the project is run again by using input provided at run time.</span></span>

## <a name="to-filter-by-using-the-contains-method"></a><span data-ttu-id="e0a5b-109">Contains メソッドを使用してフィルター処理するには</span><span class="sxs-lookup"><span data-stu-id="e0a5b-109">To filter by using the Contains method</span></span>

1. <span data-ttu-id="e0a5b-110">新しいコンソール アプリケーションを開き、それに `PredicateFilters` という名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="e0a5b-110">Open a new console application and name it `PredicateFilters`.</span></span>

2. <span data-ttu-id="e0a5b-111">「`StudentClass`オブジェクトのコレクションを照会する[」から ](query-a-collection-of-objects.md) クラスをコピーし、クラス `PredicateFilters` の下の名前空間 `Program` に貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="e0a5b-111">Copy the `StudentClass` class from [Query a collection of objects](query-a-collection-of-objects.md) and paste it into namespace `PredicateFilters` underneath class `Program`.</span></span> <span data-ttu-id="e0a5b-112">`StudentClass` は、`Student` オブジェクトの一覧を提供します。</span><span class="sxs-lookup"><span data-stu-id="e0a5b-112">`StudentClass` provides a list of `Student` objects.</span></span>

3. <span data-ttu-id="e0a5b-113">`Main` で `StudentClass` メソッドをコメント アウトします。</span><span class="sxs-lookup"><span data-stu-id="e0a5b-113">Comment out the `Main` method in `StudentClass`.</span></span>

4. <span data-ttu-id="e0a5b-114">クラス `Program` を次のコードで置き換えます。</span><span class="sxs-lookup"><span data-stu-id="e0a5b-114">Replace class `Program` with the following code:</span></span>

     [!code-csharp[csProgGuideLINQ#26](~/samples/snippets/csharp/concepts/linq/how-to-dynamically-specify-predicate-filters-at-runtime_1.cs)]

5. <span data-ttu-id="e0a5b-115">次の行をクラス `Main` の `DynamicPredicates` メソッドに追加します。`ids` の宣言の下です。</span><span class="sxs-lookup"><span data-stu-id="e0a5b-115">Add the following line to the `Main` method in class `DynamicPredicates`, under the declaration of `ids`.</span></span>

     ```csharp
     QueryById(ids);
     ```

6. <span data-ttu-id="e0a5b-116">プロジェクトを実行します。</span><span class="sxs-lookup"><span data-stu-id="e0a5b-116">Run the project.</span></span>

7. <span data-ttu-id="e0a5b-117">次の出力がコンソール ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="e0a5b-117">The following output is displayed in a console window:</span></span>

     <span data-ttu-id="e0a5b-118">Garcia: 114</span><span class="sxs-lookup"><span data-stu-id="e0a5b-118">Garcia: 114</span></span>

     <span data-ttu-id="e0a5b-119">O'Donnell: 112</span><span class="sxs-lookup"><span data-stu-id="e0a5b-119">O'Donnell: 112</span></span>

     <span data-ttu-id="e0a5b-120">Omelchenko: 111</span><span class="sxs-lookup"><span data-stu-id="e0a5b-120">Omelchenko: 111</span></span>

8. <span data-ttu-id="e0a5b-121">次の手順はプロジェクトをもう一度実行することですが、今度は配列 `ids` の代わりに実行時に提供された入力を使用します。</span><span class="sxs-lookup"><span data-stu-id="e0a5b-121">The next step is to run the project again, this time by using input entered at run time instead of array `ids`.</span></span> <span data-ttu-id="e0a5b-122">`QueryByID(ids)` メソッドで `QueryByID(args)` を `Main` に変更します。</span><span class="sxs-lookup"><span data-stu-id="e0a5b-122">Change `QueryByID(ids)` to `QueryByID(args)` in the `Main` method.</span></span>

9. <span data-ttu-id="e0a5b-123">コマンド ライン引数 `122 117 120 115` でプロジェクトを実行します。</span><span class="sxs-lookup"><span data-stu-id="e0a5b-123">Run the project with the command line arguments `122 117 120 115`.</span></span> <span data-ttu-id="e0a5b-124">プロジェクトが実行されると、これらの値が `args` メソッドのパラメーター、`Main` の要素になります。</span><span class="sxs-lookup"><span data-stu-id="e0a5b-124">When the project is run, those values become elements of `args`, the parameter of the `Main` method.</span></span>

10. <span data-ttu-id="e0a5b-125">次の出力がコンソール ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="e0a5b-125">The following output is displayed in a console window:</span></span>

     <span data-ttu-id="e0a5b-126">Adams: 120</span><span class="sxs-lookup"><span data-stu-id="e0a5b-126">Adams: 120</span></span>

     <span data-ttu-id="e0a5b-127">Feng: 117</span><span class="sxs-lookup"><span data-stu-id="e0a5b-127">Feng: 117</span></span>

     <span data-ttu-id="e0a5b-128">Garcia: 115</span><span class="sxs-lookup"><span data-stu-id="e0a5b-128">Garcia: 115</span></span>

     <span data-ttu-id="e0a5b-129">Tucker: 122</span><span class="sxs-lookup"><span data-stu-id="e0a5b-129">Tucker: 122</span></span>

## <a name="to-filter-by-using-a-switch-statement"></a><span data-ttu-id="e0a5b-130">switch ステートメントを使用してフィルター処理するには</span><span class="sxs-lookup"><span data-stu-id="e0a5b-130">To filter by using a switch statement</span></span>

1. <span data-ttu-id="e0a5b-131">`switch` ステートメントを使用し、あらかじめ決定されている代替クエリから選択できます。</span><span class="sxs-lookup"><span data-stu-id="e0a5b-131">You can use a `switch` statement to select among predetermined alternative queries.</span></span> <span data-ttu-id="e0a5b-132">次の例では、`studentQuery` は、実行時に指定された学年に基づき、別の `where` 句を使用します。</span><span class="sxs-lookup"><span data-stu-id="e0a5b-132">In the following example, `studentQuery` uses a different `where` clause depending on which grade level, or year, is specified at run time.</span></span>

2. <span data-ttu-id="e0a5b-133">次のメソッドをコピーし、クラス `DynamicPredicates` に貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="e0a5b-133">Copy the following method and paste it into class `DynamicPredicates`.</span></span>

     [!code-csharp[csProgGuideLINQ#27](~/samples/snippets/csharp/concepts/linq//how-to-dynamically-specify-predicate-filters-at-runtime_2.cs)]

3. <span data-ttu-id="e0a5b-134">`Main` メソッドで、`QueryByID` の呼び出しを次の呼び出しに置換します。この呼び出しは、`args` 配列の最初の要素をその引数として送信します (`QueryByYear(args[0])`)。</span><span class="sxs-lookup"><span data-stu-id="e0a5b-134">In the `Main` method, replace the call to `QueryByID` with the following call, which sends the first element from the `args` array as its argument: `QueryByYear(args[0])`.</span></span>

4. <span data-ttu-id="e0a5b-135">1 から 4 の整数をコマンド ライン引数としてプロジェクトを実行します。</span><span class="sxs-lookup"><span data-stu-id="e0a5b-135">Run the project with a command line argument of an integer value between 1 and 4.</span></span>

## <a name="see-also"></a><span data-ttu-id="e0a5b-136">参照</span><span class="sxs-lookup"><span data-stu-id="e0a5b-136">See also</span></span>

- [<span data-ttu-id="e0a5b-137">統合言語クエリ (LINQ)</span><span class="sxs-lookup"><span data-stu-id="e0a5b-137">Language Integrated Query (LINQ)</span></span>](index.md)
- [<span data-ttu-id="e0a5b-138">where 句</span><span class="sxs-lookup"><span data-stu-id="e0a5b-138">where clause</span></span>](../language-reference/keywords/where-clause.md)
