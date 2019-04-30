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
ms.openlocfilehash: 0b4e7c9e253f94e1e28700c8669d28799ab69d91
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62053718"
---
# <a name="array-dimensions-in-visual-basic"></a><span data-ttu-id="45a6b-102">Visual Basic における配列の次元</span><span class="sxs-lookup"><span data-stu-id="45a6b-102">Array Dimensions in Visual Basic</span></span>
<span data-ttu-id="45a6b-103">A*ディメンション*は、方向が配列の要素の仕様を変更できます。</span><span class="sxs-lookup"><span data-stu-id="45a6b-103">A *dimension* is a direction in which you can vary the specification of an array's elements.</span></span> <span data-ttu-id="45a6b-104">月の日付ごとの売上合計を保持する配列には、1 つのディメンション (月の日) があります。</span><span class="sxs-lookup"><span data-stu-id="45a6b-104">An array that holds the sales total for each day of the month has one dimension (the day of the month).</span></span> <span data-ttu-id="45a6b-105">1 か月の日付ごとに売上を部門別合計保持する配列には、2 つのディメンション (部門の番号と月の日) があります。</span><span class="sxs-lookup"><span data-stu-id="45a6b-105">An array that holds the sales total by department for each day of the month has two dimensions (the department number and the day of the month).</span></span> <span data-ttu-id="45a6b-106">配列の次元数と呼ばれる、*ランク*します。</span><span class="sxs-lookup"><span data-stu-id="45a6b-106">The number of dimensions an array has is called its *rank*.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="45a6b-107">使用することができます、<xref:System.Array.Rank%2A>プロパティの配列に次元数があります。</span><span class="sxs-lookup"><span data-stu-id="45a6b-107">You can use the <xref:System.Array.Rank%2A> property to determine the how many dimensions an array has.</span></span>  
  
## <a name="working-with-dimensions"></a><span data-ttu-id="45a6b-108">ディメンションの使用</span><span class="sxs-lookup"><span data-stu-id="45a6b-108">Working with Dimensions</span></span>  
 <span data-ttu-id="45a6b-109">指定することによって、配列の要素を指定する、*インデックス*または*添字*の各次元。</span><span class="sxs-lookup"><span data-stu-id="45a6b-109">You specify an element of an array by supplying an *index* or *subscript* for each of its dimensions.</span></span> <span data-ttu-id="45a6b-110">要素は、そのディメンションの最も大きいインデックスをインデックス 0 から各次元の連続しています。</span><span class="sxs-lookup"><span data-stu-id="45a6b-110">The elements are contiguous along each dimension from index 0 through the highest index for that dimension.</span></span>  
  
 <span data-ttu-id="45a6b-111">次の図は、ランクが異なる配列の概念の構造を示しています。</span><span class="sxs-lookup"><span data-stu-id="45a6b-111">The following illustrations show the conceptual structure of arrays with different ranks.</span></span> <span data-ttu-id="45a6b-112">図内の各要素は、これにアクセスするインデックス値を示します。</span><span class="sxs-lookup"><span data-stu-id="45a6b-112">Each element in the illustrations shows the index values that access it.</span></span> <span data-ttu-id="45a6b-113">たとえば、インデックスを指定することで 2 次元配列の 2 つ目の行の最初の要素をアクセス`(1, 0)`します。</span><span class="sxs-lookup"><span data-stu-id="45a6b-113">For example, you can access the first element of the second row of the two-dimensional array by specifying indexes `(1, 0)`.</span></span>  
  
 ![1 次元配列を示す図。](./media/array-dimensions/one-dimensional-array.gif)  
  
 ![2 次元の配列を示す図。](./media/array-dimensions/two-dimensional-array.gif)  
  
 ![3 次元の配列を示す図。](./media/array-dimensions/three-dimensional-array.gif)  
  
### <a name="one-dimension"></a><span data-ttu-id="45a6b-117">1 つのディメンション</span><span class="sxs-lookup"><span data-stu-id="45a6b-117">One Dimension</span></span>  
 <span data-ttu-id="45a6b-118">多くの配列では、各年齢の人の数などの 1 つだけディメンションを持ちます。</span><span class="sxs-lookup"><span data-stu-id="45a6b-118">Many arrays have only one dimension, such as the number of people of each age.</span></span> <span data-ttu-id="45a6b-119">要素を指定する唯一の要件は、その要素数を保持する期間です。</span><span class="sxs-lookup"><span data-stu-id="45a6b-119">The only requirement to specify an element is the age for which that element holds the count.</span></span> <span data-ttu-id="45a6b-120">そのため、このような配列は、1 つのみのインデックスを使用します。</span><span class="sxs-lookup"><span data-stu-id="45a6b-120">Therefore, such an array uses only one index.</span></span> <span data-ttu-id="45a6b-121">次の例を保持する変数の宣言を*1 次元配列*年齢が 0 ~ 120 の有効期間の数します。</span><span class="sxs-lookup"><span data-stu-id="45a6b-121">The following example declares a variable to hold a *one-dimensional array* of age counts for ages 0 through 120.</span></span>  
  
```  
Dim ageCounts(120) As UInteger  
```  
  
### <a name="two-dimensions"></a><span data-ttu-id="45a6b-122">2 つのディメンション</span><span class="sxs-lookup"><span data-stu-id="45a6b-122">Two Dimensions</span></span>  
 <span data-ttu-id="45a6b-123">一部の配列では、各ビルのキャンパス内の各床面のオフィスの数など、2 つのディメンションがあります。</span><span class="sxs-lookup"><span data-stu-id="45a6b-123">Some arrays have two dimensions, such as the number of offices on each floor of each building on a campus.</span></span> <span data-ttu-id="45a6b-124">要素の仕様は、建物番号と、床面の両方が必要ですし、各要素はビルとフロアの組み合わせの数を保持します。</span><span class="sxs-lookup"><span data-stu-id="45a6b-124">The specification of an element requires both the building number and the floor, and each element holds the count for that combination of building and floor.</span></span> <span data-ttu-id="45a6b-125">したがって、このような配列には、2 つのインデックスが使用されます。</span><span class="sxs-lookup"><span data-stu-id="45a6b-125">Therefore, such an array uses two indexes.</span></span> <span data-ttu-id="45a6b-126">次の例を保持する変数の宣言を*2 次元配列*office 数、0 ~ 40 のビルとフロアが 0 ~ 5 の。</span><span class="sxs-lookup"><span data-stu-id="45a6b-126">The following example declares a variable to hold a *two-dimensional array* of office counts, for buildings 0 through 40 and floors 0 through 5.</span></span>  
  
```  
Dim officeCounts(40, 5) As Byte  
```  
  
 <span data-ttu-id="45a6b-127">2 次元配列とも呼ばれますが、*長方形配列*します。</span><span class="sxs-lookup"><span data-stu-id="45a6b-127">A two-dimensional array is also called a *rectangular array*.</span></span>  
  
### <a name="three-dimensions"></a><span data-ttu-id="45a6b-128">3 つのディメンション</span><span class="sxs-lookup"><span data-stu-id="45a6b-128">Three Dimensions</span></span>  
 <span data-ttu-id="45a6b-129">いくつかの配列では、3 次元空間内の値などの 3 つのディメンションがあります。</span><span class="sxs-lookup"><span data-stu-id="45a6b-129">A few arrays have three dimensions, such as values in three-dimensional space.</span></span> <span data-ttu-id="45a6b-130">このような配列は、この場合、x、y、および物理領域の z 座標を表す 3 つのインデックスを使用します。</span><span class="sxs-lookup"><span data-stu-id="45a6b-130">Such an array uses three indexes, which in this case represent the x, y, and z coordinates of physical space.</span></span> <span data-ttu-id="45a6b-131">次の例を保持する変数の宣言を*3 次元配列*3 次元のボリュームでのさまざまなポイントでの気温。</span><span class="sxs-lookup"><span data-stu-id="45a6b-131">The following example declares a variable to hold a *three-dimensional array* of air temperatures at various points in a three-dimensional volume.</span></span>  
  
```  
Dim airTemperatures(99, 99, 24) As Single  
```  
  
### <a name="more-than-three-dimensions"></a><span data-ttu-id="45a6b-132">次の 3 つ以上のディメンション</span><span class="sxs-lookup"><span data-stu-id="45a6b-132">More than Three Dimensions</span></span>  
 <span data-ttu-id="45a6b-133">配列には、最大 32 次元できますが、は 3 つ以上あるまれです。</span><span class="sxs-lookup"><span data-stu-id="45a6b-133">Although an array can have as many as 32 dimensions, it is rare to have more than three.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="45a6b-134">配列にディメンションを追加するときに配列に必要な合計ストレージ増大、注意して使用して多次元配列をそのください。</span><span class="sxs-lookup"><span data-stu-id="45a6b-134">When you add dimensions to an array, the total storage needed by the array increases considerably, so use multidimensional arrays with care.</span></span>  
  
## <a name="using-different-dimensions"></a><span data-ttu-id="45a6b-135">別のディメンションを使用します。</span><span class="sxs-lookup"><span data-stu-id="45a6b-135">Using Different Dimensions</span></span>  
 <span data-ttu-id="45a6b-136">当月の毎日の売り上げ高を追跡したいとします。</span><span class="sxs-lookup"><span data-stu-id="45a6b-136">Suppose you want to track sales amounts for every day of the present month.</span></span> <span data-ttu-id="45a6b-137">次の例として、月の日付ごとに 1 つを示しています 31 の要素を持つ 1 次元配列を宣言する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="45a6b-137">You might declare a one-dimensional array with 31 elements, one for each day of the month, as the following example shows.</span></span>  
  
```  
Dim salesAmounts(30) As Double  
```  
  
 <span data-ttu-id="45a6b-138">これで毎日についてだけでなく、1 か月の年の毎月のも、同じ情報を追跡したいとします。</span><span class="sxs-lookup"><span data-stu-id="45a6b-138">Now suppose you want to track the same information not only for every day of a month but also for every month of the year.</span></span> <span data-ttu-id="45a6b-139">次の例を示します (月) の 12 行と 31 列 (日) の 2 次元配列を宣言する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="45a6b-139">You might declare a two-dimensional array with 12 rows (for the months) and 31 columns (for the days), as the following example shows.</span></span>  
  
```  
Dim salesAmounts(11, 30) As Double  
```  
  
 <span data-ttu-id="45a6b-140">ようになりましたが対象とすると、配列は 1 年以上の情報を保持します。</span><span class="sxs-lookup"><span data-stu-id="45a6b-140">Now suppose you decide to have your array hold information for more than one year.</span></span> <span data-ttu-id="45a6b-141">5 年間の売り上げ高を追跡する場合は、次の例のように 5 レイヤー、12 行は、31 列と 3 次元の配列を宣言できます。</span><span class="sxs-lookup"><span data-stu-id="45a6b-141">If you want to track sales amounts for 5 years, you could declare a three-dimensional array with 5 layers, 12 rows, and 31 columns, as the following example shows.</span></span>  
  
```  
Dim salesAmounts(4, 11, 30) As Double  
```  
  
 <span data-ttu-id="45a6b-142">各インデックスが 0 から、最大容量の各次元に異なるので、注意してください。`salesAmounts`そのディメンションの 1 つ必要な長さよりも小さいとして宣言されています。</span><span class="sxs-lookup"><span data-stu-id="45a6b-142">Note that, because each index varies from 0 to its maximum, each dimension of `salesAmounts` is declared as one less than the required length for that dimension.</span></span> <span data-ttu-id="45a6b-143">新しい次元ごとに、配列のサイズが増えることにも注意してください。</span><span class="sxs-lookup"><span data-stu-id="45a6b-143">Note also that the size of the array increases with each new dimension.</span></span> <span data-ttu-id="45a6b-144">上記の例では、3 つのサイズは、それぞれ 31、372、および 1,860 要素です。</span><span class="sxs-lookup"><span data-stu-id="45a6b-144">The three sizes in the preceding examples are 31, 372, and 1,860 elements respectively.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="45a6b-145">使用せずに配列を作成することができます、`Dim`ステートメントまたは`New`句。</span><span class="sxs-lookup"><span data-stu-id="45a6b-145">You can create an array without using the `Dim` statement or the `New` clause.</span></span> <span data-ttu-id="45a6b-146">たとえば、呼び出すことができます、<xref:System.Array.CreateInstance%2A>メソッド、または別のコンポーネントをこのように作成された配列、コードを渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="45a6b-146">For example, you can call the <xref:System.Array.CreateInstance%2A> method, or another component can pass your code an array created in this manner.</span></span> <span data-ttu-id="45a6b-147">このような配列には、0 以外の下限を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="45a6b-147">Such an array can have a lower bound other than 0.</span></span> <span data-ttu-id="45a6b-148">常を使用してディメンションの下限の境界をテストすることができます、<xref:System.Array.GetLowerBound%2A>メソッドまたは`LBound`関数。</span><span class="sxs-lookup"><span data-stu-id="45a6b-148">You can always test for the lower bound of a dimension by using the <xref:System.Array.GetLowerBound%2A> method or the `LBound` function.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45a6b-149">関連項目</span><span class="sxs-lookup"><span data-stu-id="45a6b-149">See also</span></span>

- [<span data-ttu-id="45a6b-150">配列</span><span class="sxs-lookup"><span data-stu-id="45a6b-150">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="45a6b-151">配列のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="45a6b-151">Troubleshooting Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)
