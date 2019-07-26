---
title: Visual Basic における配列の次元
ms.date: 07/20/2015
helpviewer_keywords:
- dimensions, arrays
- arrays [Visual Basic], dimensions
- arrays [Visual Basic], rectangular
- arrays [Visual Basic], rank
- rectangular arrays
- ranking, arrays
ms.assetid: 385e911b-18c1-4e98-9924-c6d279101dd9
ms.openlocfilehash: bbc9e523e9b74cf380c65135e7416f1feba01a2e
ms.sourcegitcommit: 463f3f050cecc0b6403e67f19a61f870fb8e7b7d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/26/2019
ms.locfileid: "68512892"
---
# <a name="array-dimensions-in-visual-basic"></a><span data-ttu-id="76e2c-102">Visual Basic における配列の次元</span><span class="sxs-lookup"><span data-stu-id="76e2c-102">Array Dimensions in Visual Basic</span></span>

<span data-ttu-id="76e2c-103">*ディメンション*は、配列の要素の指定を変更できる方向です。</span><span class="sxs-lookup"><span data-stu-id="76e2c-103">A *dimension* is a direction in which you can vary the specification of an array's elements.</span></span> <span data-ttu-id="76e2c-104">月の各日の売上合計を保持する配列には、1つのディメンション (その月の日付) があります。</span><span class="sxs-lookup"><span data-stu-id="76e2c-104">An array that holds the sales total for each day of the month has one dimension (the day of the month).</span></span> <span data-ttu-id="76e2c-105">月の各日の売上合計を部門別に保持する配列には、2つのディメンション (部署番号とその月の日) があります。</span><span class="sxs-lookup"><span data-stu-id="76e2c-105">An array that holds the sales total by department for each day of the month has two dimensions (the department number and the day of the month).</span></span> <span data-ttu-id="76e2c-106">配列が持つ次元の数を*ランク*と呼びます。</span><span class="sxs-lookup"><span data-stu-id="76e2c-106">The number of dimensions an array has is called its *rank*.</span></span>

> [!NOTE]
> <span data-ttu-id="76e2c-107"><xref:System.Array.Rank%2A>プロパティを使用して、配列の次元数を確認できます。</span><span class="sxs-lookup"><span data-stu-id="76e2c-107">You can use the <xref:System.Array.Rank%2A> property to determine the how many dimensions an array has.</span></span>

## <a name="working-with-dimensions"></a><span data-ttu-id="76e2c-108">ディメンションの操作</span><span class="sxs-lookup"><span data-stu-id="76e2c-108">Working with Dimensions</span></span>

<span data-ttu-id="76e2c-109">配列の要素を指定するには、各次元の*インデックス*または*添字*を指定します。</span><span class="sxs-lookup"><span data-stu-id="76e2c-109">You specify an element of an array by supplying an *index* or *subscript* for each of its dimensions.</span></span> <span data-ttu-id="76e2c-110">要素は、インデックス0からそのディメンションの最大インデックスまで、各ディメンションに沿って連続しています。</span><span class="sxs-lookup"><span data-stu-id="76e2c-110">The elements are contiguous along each dimension from index 0 through the highest index for that dimension.</span></span>

<span data-ttu-id="76e2c-111">次の図は、異なるランクを持つ配列の概念構造を示しています。</span><span class="sxs-lookup"><span data-stu-id="76e2c-111">The following illustrations show the conceptual structure of arrays with different ranks.</span></span> <span data-ttu-id="76e2c-112">図の各要素は、それにアクセスするインデックス値を示しています。</span><span class="sxs-lookup"><span data-stu-id="76e2c-112">Each element in the illustrations shows the index values that access it.</span></span> <span data-ttu-id="76e2c-113">たとえば、インデックス`(1, 0)`を指定することにより、2次元配列の2番目の行の最初の要素にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="76e2c-113">For example, you can access the first element of the second row of the two-dimensional array by specifying indexes `(1, 0)`.</span></span>

![1次元配列を示す図。](./media/array-dimensions/one-dimensional-array.gif)

![2次元配列を示す図。](./media/array-dimensions/two-dimensional-array.gif)

![3次元配列を示す図。](./media/array-dimensions/three-dimensional-array.gif)

### <a name="one-dimension"></a><span data-ttu-id="76e2c-117">1つのディメンション</span><span class="sxs-lookup"><span data-stu-id="76e2c-117">One Dimension</span></span>

<span data-ttu-id="76e2c-118">多くの配列には、各年齢の人の数など、ディメンションが1つしかありません。</span><span class="sxs-lookup"><span data-stu-id="76e2c-118">Many arrays have only one dimension, such as the number of people of each age.</span></span> <span data-ttu-id="76e2c-119">要素を指定する唯一の要件は、その要素がカウントを保持する期間です。</span><span class="sxs-lookup"><span data-stu-id="76e2c-119">The only requirement to specify an element is the age for which that element holds the count.</span></span> <span data-ttu-id="76e2c-120">したがって、このような配列では、インデックスを1つだけ使用します。</span><span class="sxs-lookup"><span data-stu-id="76e2c-120">Therefore, such an array uses only one index.</span></span> <span data-ttu-id="76e2c-121">次の例では、0 ~ 120 の年齢の年齢カウントの*1 次元配列*を保持する変数を宣言しています。</span><span class="sxs-lookup"><span data-stu-id="76e2c-121">The following example declares a variable to hold a *one-dimensional array* of age counts for ages 0 through 120.</span></span>

```vb
Dim ageCounts(120) As UInteger
```

### <a name="two-dimensions"></a><span data-ttu-id="76e2c-122">2つのディメンション</span><span class="sxs-lookup"><span data-stu-id="76e2c-122">Two Dimensions</span></span>

<span data-ttu-id="76e2c-123">一部の配列には、キャンパス上の各建物の各フロアのオフィス数など、2つの次元があります。</span><span class="sxs-lookup"><span data-stu-id="76e2c-123">Some arrays have two dimensions, such as the number of offices on each floor of each building on a campus.</span></span> <span data-ttu-id="76e2c-124">要素の指定には、ビル番号とフロアの両方が必要です。各要素には、建物と床の組み合わせの数が保持されます。</span><span class="sxs-lookup"><span data-stu-id="76e2c-124">The specification of an element requires both the building number and the floor, and each element holds the count for that combination of building and floor.</span></span> <span data-ttu-id="76e2c-125">そのため、このような配列では2つのインデックスを使用します。</span><span class="sxs-lookup"><span data-stu-id="76e2c-125">Therefore, such an array uses two indexes.</span></span> <span data-ttu-id="76e2c-126">次の例では、オフィス数が 0 ~ 40 で、床が 0 ~ 5 の*2 次元配列*を保持する変数を宣言しています。</span><span class="sxs-lookup"><span data-stu-id="76e2c-126">The following example declares a variable to hold a *two-dimensional array* of office counts, for buildings 0 through 40 and floors 0 through 5.</span></span>

```vb
Dim officeCounts(40, 5) As Byte
```

<span data-ttu-id="76e2c-127">2次元配列は、*四角形配列*とも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="76e2c-127">A two-dimensional array is also called a *rectangular array*.</span></span>

### <a name="three-dimensions"></a><span data-ttu-id="76e2c-128">3次元</span><span class="sxs-lookup"><span data-stu-id="76e2c-128">Three Dimensions</span></span>

<span data-ttu-id="76e2c-129">3次元空間の値など、いくつかの配列には3つの次元があります。</span><span class="sxs-lookup"><span data-stu-id="76e2c-129">A few arrays have three dimensions, such as values in three-dimensional space.</span></span> <span data-ttu-id="76e2c-130">このような配列では、3つのインデックスが使用されます。この場合、物理空間の x、y、z 座標を表します。</span><span class="sxs-lookup"><span data-stu-id="76e2c-130">Such an array uses three indexes, which in this case represent the x, y, and z coordinates of physical space.</span></span> <span data-ttu-id="76e2c-131">次の例では、3次元ボリュームのさまざまな点で、航空温度の*3 次元配列*を保持する変数を宣言しています。</span><span class="sxs-lookup"><span data-stu-id="76e2c-131">The following example declares a variable to hold a *three-dimensional array* of air temperatures at various points in a three-dimensional volume.</span></span>

```vb
Dim airTemperatures(99, 99, 24) As Single
```

### <a name="more-than-three-dimensions"></a><span data-ttu-id="76e2c-132">3次元以上</span><span class="sxs-lookup"><span data-stu-id="76e2c-132">More than Three Dimensions</span></span>

<span data-ttu-id="76e2c-133">配列の次元は最大で32次元ですが、少なくとも3つを超えることはほとんどありません。</span><span class="sxs-lookup"><span data-stu-id="76e2c-133">Although an array can have as many as 32 dimensions, it is rare to have more than three.</span></span>

> [!NOTE]
> <span data-ttu-id="76e2c-134">配列にディメンションを追加すると、配列に必要なストレージの合計容量が大幅に増加するので、多次元配列を使用することを考慮してください。</span><span class="sxs-lookup"><span data-stu-id="76e2c-134">When you add dimensions to an array, the total storage needed by the array increases considerably, so use multidimensional arrays with care.</span></span>

## <a name="using-different-dimensions"></a><span data-ttu-id="76e2c-135">異なる次元の使用</span><span class="sxs-lookup"><span data-stu-id="76e2c-135">Using Different Dimensions</span></span>

<span data-ttu-id="76e2c-136">今月の各日の売上高を追跡するとします。</span><span class="sxs-lookup"><span data-stu-id="76e2c-136">Suppose you want to track sales amounts for every day of the present month.</span></span> <span data-ttu-id="76e2c-137">次の例に示すように、31個の要素を持つ1次元配列を、その月の各日に1つ宣言できます。</span><span class="sxs-lookup"><span data-stu-id="76e2c-137">You might declare a one-dimensional array with 31 elements, one for each day of the month, as the following example shows.</span></span>

```vb
Dim salesAmounts(30) As Double
```

<span data-ttu-id="76e2c-138">次に、1か月のすべての日についてだけでなく、すべての月についても同じ情報を追跡するとします。</span><span class="sxs-lookup"><span data-stu-id="76e2c-138">Now suppose you want to track the same information not only for every day of a month but also for every month of the year.</span></span> <span data-ttu-id="76e2c-139">次の例に示すように、12行 (月) と31列 (曜日) を含む2次元配列を宣言できます。</span><span class="sxs-lookup"><span data-stu-id="76e2c-139">You might declare a two-dimensional array with 12 rows (for the months) and 31 columns (for the days), as the following example shows.</span></span>

```vb
Dim salesAmounts(11, 30) As Double
```

<span data-ttu-id="76e2c-140">ここで、配列に複数の年の情報を保持することにしたとします。</span><span class="sxs-lookup"><span data-stu-id="76e2c-140">Now suppose you decide to have your array hold information for more than one year.</span></span> <span data-ttu-id="76e2c-141">5年間の売上高を追跡する場合は、次の例に示すように、5つのレイヤー、12行、および31列を含む3次元配列を宣言できます。</span><span class="sxs-lookup"><span data-stu-id="76e2c-141">If you want to track sales amounts for 5 years, you could declare a three-dimensional array with 5 layers, 12 rows, and 31 columns, as the following example shows.</span></span>

```vb
Dim salesAmounts(4, 11, 30) As Double
```

<span data-ttu-id="76e2c-142">各インデックスは0から最大値まで変化するため、の各次元は`salesAmounts` 、その次元で必要な長さより1つの値として宣言されます。</span><span class="sxs-lookup"><span data-stu-id="76e2c-142">Note that, because each index varies from 0 to its maximum, each dimension of `salesAmounts` is declared as one less than the required length for that dimension.</span></span> <span data-ttu-id="76e2c-143">また、新しいディメンションごとに配列のサイズが増加することにも注意してください。</span><span class="sxs-lookup"><span data-stu-id="76e2c-143">Note also that the size of the array increases with each new dimension.</span></span> <span data-ttu-id="76e2c-144">前の例の3つのサイズは、それぞれ31、372、および1860要素です。</span><span class="sxs-lookup"><span data-stu-id="76e2c-144">The three sizes in the preceding examples are 31, 372, and 1,860 elements respectively.</span></span>

> [!NOTE]
> <span data-ttu-id="76e2c-145">`Dim` ステートメント`New`または句を使用せずに配列を作成できます。</span><span class="sxs-lookup"><span data-stu-id="76e2c-145">You can create an array without using the `Dim` statement or the `New` clause.</span></span> <span data-ttu-id="76e2c-146">たとえば、 <xref:System.Array.CreateInstance%2A>メソッドを呼び出すことができます。または、別のコンポーネントが、この方法で作成された配列をコードに渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="76e2c-146">For example, you can call the <xref:System.Array.CreateInstance%2A> method, or another component can pass your code an array created in this manner.</span></span> <span data-ttu-id="76e2c-147">このような配列は、0以外の下限を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="76e2c-147">Such an array can have a lower bound other than 0.</span></span> <span data-ttu-id="76e2c-148">ディメンションの下限は、 <xref:System.Array.GetLowerBound%2A>メソッド`LBound`または関数を使用していつでもテストできます。</span><span class="sxs-lookup"><span data-stu-id="76e2c-148">You can always test for the lower bound of a dimension by using the <xref:System.Array.GetLowerBound%2A> method or the `LBound` function.</span></span>

## <a name="see-also"></a><span data-ttu-id="76e2c-149">関連項目</span><span class="sxs-lookup"><span data-stu-id="76e2c-149">See also</span></span>

- [<span data-ttu-id="76e2c-150">配列</span><span class="sxs-lookup"><span data-stu-id="76e2c-150">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="76e2c-151">配列のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="76e2c-151">Troubleshooting Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)
