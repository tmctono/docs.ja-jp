---
title: '方法 : 配列を別の配列に代入する'
ms.date: 07/20/2015
helpviewer_keywords:
- covariance, arrays
- arrays [Visual Basic], assigning
- arrays [Visual Basic], covariance
ms.assetid: 1ae89ea5-f292-4282-bcfc-e9b06b37fbd5
ms.openlocfilehash: be5337e36c2cc7ad9f9b32182b8575ac66bb4a50
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351890"
---
# <a name="how-to-assign-one-array-to-another-array-visual-basic"></a><span data-ttu-id="a3aab-102">方法: 配列を別の配列に代入する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a3aab-102">How to: Assign One Array to Another Array (Visual Basic)</span></span>

<span data-ttu-id="a3aab-103">配列はオブジェクトであるため、他の種類のオブジェクトと同様に代入ステートメントで使用できます。</span><span class="sxs-lookup"><span data-stu-id="a3aab-103">Because arrays are objects, you can use them in assignment statements like other object types.</span></span> <span data-ttu-id="a3aab-104">配列変数は、配列要素とランクおよび長さの情報を構成するデータへのポインターを保持し、割り当てによってこのポインターのみがコピーされます。</span><span class="sxs-lookup"><span data-stu-id="a3aab-104">An array variable holds a pointer to the data constituting the array elements and the rank and length information, and an assignment copies only this pointer.</span></span>

### <a name="to-assign-one-array-to-another-array"></a><span data-ttu-id="a3aab-105">1つの配列を別の配列に割り当てるには</span><span class="sxs-lookup"><span data-stu-id="a3aab-105">To assign one array to another array</span></span>

1. <span data-ttu-id="a3aab-106">2つの配列のランク (次元の数) と互換性のある要素のデータ型が同じであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a3aab-106">Ensure that the two arrays have the same rank (number of dimensions) and compatible element data types.</span></span>

2. <span data-ttu-id="a3aab-107">標準の代入ステートメントを使用して、コピー元の配列をコピー先の配列に代入します。</span><span class="sxs-lookup"><span data-stu-id="a3aab-107">Use a standard assignment statement to assign the source array to the destination array.</span></span> <span data-ttu-id="a3aab-108">配列名のいずれかをかっこで囲んでください。</span><span class="sxs-lookup"><span data-stu-id="a3aab-108">Do not follow either array name with parentheses.</span></span>

    ```vb
    Dim formArray() As System.Windows.Forms.Form
    Dim controlArray() As System.Windows.Forms.Control
    controlArray = formArray
    ```

<span data-ttu-id="a3aab-109">1つの配列を別の配列に割り当てる場合は、次の規則が適用されます。</span><span class="sxs-lookup"><span data-stu-id="a3aab-109">When you assign one array to another, the following rules apply:</span></span>

- <span data-ttu-id="a3aab-110">**ランクが等しいこと。**</span><span class="sxs-lookup"><span data-stu-id="a3aab-110">**Equal Ranks.**</span></span> <span data-ttu-id="a3aab-111">コピー先の配列のランク (次元数) は、ソース配列と同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3aab-111">The rank (number of dimensions) of the destination array must be the same as that of the source array.</span></span>

  <span data-ttu-id="a3aab-112">2つの配列のランクが等しい場合、次元は同じである必要はありません。</span><span class="sxs-lookup"><span data-stu-id="a3aab-112">Provided the ranks of the two arrays are equal, the dimensions do not need to be equal.</span></span> <span data-ttu-id="a3aab-113">指定されたディメンション内の要素の数は、割り当て時に変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a3aab-113">The number of elements in a given dimension can change during assignment.</span></span>

- <span data-ttu-id="a3aab-114">**要素の型。**</span><span class="sxs-lookup"><span data-stu-id="a3aab-114">**Element Types.**</span></span> <span data-ttu-id="a3aab-115">両方の配列に*参照型*の要素が含まれているか、両方の配列が*値の型*の要素を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3aab-115">Either both arrays must have *reference type* elements or both arrays must have *value type* elements.</span></span> <span data-ttu-id="a3aab-116">詳細については、「[値型と参照型](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a3aab-116">For more information, see [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).</span></span>

  - <span data-ttu-id="a3aab-117">両方の配列に値型の要素がある場合、要素のデータ型はまったく同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3aab-117">If both arrays have value type elements, the element data types must be exactly the same.</span></span> <span data-ttu-id="a3aab-118">唯一の例外は、`Enum` 要素の配列を、その `Enum`の基本型の配列に割り当てることができることです。</span><span class="sxs-lookup"><span data-stu-id="a3aab-118">The only exception to this is that you can assign an array of `Enum` elements to an array of the base type of that `Enum`.</span></span>

  - <span data-ttu-id="a3aab-119">両方の配列に参照型の要素がある場合、ソース要素の型は、変換先の要素の型から派生する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3aab-119">If both arrays have reference type elements, the source element type must derive from the destination element type.</span></span> <span data-ttu-id="a3aab-120">この場合、2つの配列は、要素と同じ継承関係を持ちます。</span><span class="sxs-lookup"><span data-stu-id="a3aab-120">When this is the case, the two arrays have the same inheritance relationship as their elements.</span></span> <span data-ttu-id="a3aab-121">これは、*配列の共変性*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="a3aab-121">This is called *array covariance*.</span></span>

<span data-ttu-id="a3aab-122">上記の規則に違反すると、コンパイラはエラーを報告します。たとえば、データ型に互換性がない場合や、ランクが等しくない場合などです。</span><span class="sxs-lookup"><span data-stu-id="a3aab-122">The compiler reports an error if the above rules are violated, for example if the data types are not compatible or the ranks are unequal.</span></span> <span data-ttu-id="a3aab-123">コードにエラー処理を追加して、割り当てを試行する前に配列に互換性があることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="a3aab-123">You can add error handling to your code to make sure that the arrays are compatible before attempting an assignment.</span></span> <span data-ttu-id="a3aab-124">例外がスローされないようにする場合は、 [TryCast Operator](../../../../visual-basic/language-reference/operators/trycast-operator.md)キーワードを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="a3aab-124">You can also use the [TryCast Operator](../../../../visual-basic/language-reference/operators/trycast-operator.md) keyword if you want to avoid throwing an exception.</span></span>

## <a name="see-also"></a><span data-ttu-id="a3aab-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="a3aab-125">See also</span></span>

- [<span data-ttu-id="a3aab-126">配列</span><span class="sxs-lookup"><span data-stu-id="a3aab-126">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="a3aab-127">配列のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="a3aab-127">Troubleshooting Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)
- [<span data-ttu-id="a3aab-128">Enum ステートメント</span><span class="sxs-lookup"><span data-stu-id="a3aab-128">Enum Statement</span></span>](../../../../visual-basic/language-reference/statements/enum-statement.md)
- [<span data-ttu-id="a3aab-129">配列変換</span><span class="sxs-lookup"><span data-stu-id="a3aab-129">Array Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)
