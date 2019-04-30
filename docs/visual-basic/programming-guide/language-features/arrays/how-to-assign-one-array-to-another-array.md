---
title: '方法: 別の配列 (Visual Basic) を 1 つの配列を割り当てる'
ms.date: 07/20/2015
helpviewer_keywords:
- covariance, arrays
- arrays [Visual Basic], assigning
- arrays [Visual Basic], covariance
ms.assetid: 1ae89ea5-f292-4282-bcfc-e9b06b37fbd5
ms.openlocfilehash: 78497de3a9aea55320639c55a151a1260a960159
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62053679"
---
# <a name="how-to-assign-one-array-to-another-array-visual-basic"></a><span data-ttu-id="7a797-102">方法: 別の配列 (Visual Basic) を 1 つの配列を割り当てる</span><span class="sxs-lookup"><span data-stu-id="7a797-102">How to: Assign One Array to Another Array (Visual Basic)</span></span>

<span data-ttu-id="7a797-103">配列がオブジェクトであるため、他のオブジェクト型のような代入ステートメントで使用することができます。</span><span class="sxs-lookup"><span data-stu-id="7a797-103">Because arrays are objects, you can use them in assignment statements like other object types.</span></span> <span data-ttu-id="7a797-104">配列変数の配列の要素と、ランク、および長さの情報を構成するデータにポインターを保持し、割り当ては、このポインターのみをコピーします。</span><span class="sxs-lookup"><span data-stu-id="7a797-104">An array variable holds a pointer to the data constituting the array elements and the rank and length information, and an assignment copies only this pointer.</span></span>

### <a name="to-assign-one-array-to-another-array"></a><span data-ttu-id="7a797-105">別の配列に 1 つの配列を割り当てる</span><span class="sxs-lookup"><span data-stu-id="7a797-105">To assign one array to another array</span></span>

1. <span data-ttu-id="7a797-106">2 つの配列に同じランク (次元数) と互換性のある要素のデータ型があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7a797-106">Ensure that the two arrays have the same rank (number of dimensions) and compatible element data types.</span></span>

2. <span data-ttu-id="7a797-107">標準の代入ステートメントを使用して、コピー先の配列を元の配列を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="7a797-107">Use a standard assignment statement to assign the source array to the destination array.</span></span> <span data-ttu-id="7a797-108">いずれの配列名をかっこでは使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="7a797-108">Do not follow either array name with parentheses.</span></span>

    ```vb
    Dim formArray() As System.Windows.Forms.Form
    Dim controlArray() As System.Windows.Forms.Control
    controlArray = formArray
    ```

<span data-ttu-id="7a797-109">別に 1 つの配列を割り当てた場合、次の規則が適用されます。</span><span class="sxs-lookup"><span data-stu-id="7a797-109">When you assign one array to another, the following rules apply:</span></span>

- <span data-ttu-id="7a797-110">**ランクが等しい。**</span><span class="sxs-lookup"><span data-stu-id="7a797-110">**Equal Ranks.**</span></span> <span data-ttu-id="7a797-111">コピー先配列のランク (次元数) は、ソース配列と同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="7a797-111">The rank (number of dimensions) of the destination array must be the same as that of the source array.</span></span>

  <span data-ttu-id="7a797-112">2 つの配列のランクが等しい、指定されたディメンションは等値である必要はありません。</span><span class="sxs-lookup"><span data-stu-id="7a797-112">Provided the ranks of the two arrays are equal, the dimensions do not need to be equal.</span></span> <span data-ttu-id="7a797-113">割り当ての際に、特定の次元の要素の数を変更できます。</span><span class="sxs-lookup"><span data-stu-id="7a797-113">The number of elements in a given dimension can change during assignment.</span></span>

- <span data-ttu-id="7a797-114">**要素の型。**</span><span class="sxs-lookup"><span data-stu-id="7a797-114">**Element Types.**</span></span> <span data-ttu-id="7a797-115">両方の配列のいずれかがいる必要があります*参照型*要素、または両方の配列が必要*値の型*要素。</span><span class="sxs-lookup"><span data-stu-id="7a797-115">Either both arrays must have *reference type* elements or both arrays must have *value type* elements.</span></span> <span data-ttu-id="7a797-116">詳細については、「 [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a797-116">For more information, see [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).</span></span>

  - <span data-ttu-id="7a797-117">両方の配列には、値型の要素がある、要素のデータ型正確に同じでなければなりません。</span><span class="sxs-lookup"><span data-stu-id="7a797-117">If both arrays have value type elements, the element data types must be exactly the same.</span></span> <span data-ttu-id="7a797-118">唯一の例外は、の配列を割り当てることができます`Enum`の基本型の配列に要素`Enum`します。</span><span class="sxs-lookup"><span data-stu-id="7a797-118">The only exception to this is that you can assign an array of `Enum` elements to an array of the base type of that `Enum`.</span></span>

  - <span data-ttu-id="7a797-119">両方の配列には、参照型の要素がある、ソース要素の型が変換先の要素の型から派生する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7a797-119">If both arrays have reference type elements, the source element type must derive from the destination element type.</span></span> <span data-ttu-id="7a797-120">これが、大文字と小文字の場合は、その要素として同じ継承関係がある 2 つの配列。</span><span class="sxs-lookup"><span data-stu-id="7a797-120">When this is the case, the two arrays have the same inheritance relationship as their elements.</span></span> <span data-ttu-id="7a797-121">これは呼び出されます*配列の共変性*します。</span><span class="sxs-lookup"><span data-stu-id="7a797-121">This is called *array covariance*.</span></span>

<span data-ttu-id="7a797-122">コンパイラは、エラー場合は、上記の規則違反の例のデータ型に互換性がない場合や、ランクが等しくないを報告します。</span><span class="sxs-lookup"><span data-stu-id="7a797-122">The compiler reports an error if the above rules are violated, for example if the data types are not compatible or the ranks are unequal.</span></span> <span data-ttu-id="7a797-123">割り当てを試行する前に、配列に互換性があるかどうかを確認するコードにエラー処理を追加できます。</span><span class="sxs-lookup"><span data-stu-id="7a797-123">You can add error handling to your code to make sure that the arrays are compatible before attempting an assignment.</span></span> <span data-ttu-id="7a797-124">使用することも、 [TryCast 演算子](../../../../visual-basic/language-reference/operators/trycast-operator.md)例外をスローしないようにする場合は、キーワード。</span><span class="sxs-lookup"><span data-stu-id="7a797-124">You can also use the [TryCast Operator](../../../../visual-basic/language-reference/operators/trycast-operator.md) keyword if you want to avoid throwing an exception.</span></span>

## <a name="see-also"></a><span data-ttu-id="7a797-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="7a797-125">See also</span></span>

- [<span data-ttu-id="7a797-126">配列</span><span class="sxs-lookup"><span data-stu-id="7a797-126">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="7a797-127">配列のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="7a797-127">Troubleshooting Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)
- [<span data-ttu-id="7a797-128">Enum ステートメント</span><span class="sxs-lookup"><span data-stu-id="7a797-128">Enum Statement</span></span>](../../../../visual-basic/language-reference/statements/enum-statement.md)
- [<span data-ttu-id="7a797-129">配列変換</span><span class="sxs-lookup"><span data-stu-id="7a797-129">Array Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)
