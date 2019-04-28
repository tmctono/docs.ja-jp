---
title: 配列の変換 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [Visual Basic], converting type
- type conversion [Visual Basic], arrays
- conversions [Visual Basic], type
- arrays [Visual Basic], data types
- conversions [Visual Basic], data type
- object arrays [Visual Basic], converting type
- data type conversion [Visual Basic], array conversions
- conversions [Visual Basic], array types
- object arrays
ms.assetid: fceff7d2-a1b7-44c7-b9aa-8bd831d8a444
ms.openlocfilehash: 88002e2c099ed9503beddb190d243aadcc1087fc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61908025"
---
# <a name="array-conversions-visual-basic"></a><span data-ttu-id="0bb55-102">配列の変換 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0bb55-102">Array Conversions (Visual Basic)</span></span>
<span data-ttu-id="0bb55-103">別の配列型に、配列型を変換するには、次の条件を満たす指定。</span><span class="sxs-lookup"><span data-stu-id="0bb55-103">You can convert an array type to a different array type provided you meet the following conditions:</span></span>  
  
- <span data-ttu-id="0bb55-104">**ランクが等しい。**</span><span class="sxs-lookup"><span data-stu-id="0bb55-104">**Equal Rank.**</span></span> <span data-ttu-id="0bb55-105">2 つの配列のランクは同じである必要があります、つまり、同じ次元数があります。</span><span class="sxs-lookup"><span data-stu-id="0bb55-105">The ranks of the two arrays must be the same, that is, they must have the same number of dimensions.</span></span> <span data-ttu-id="0bb55-106">ただし、それぞれの次元の長さが同じである必要はありません。</span><span class="sxs-lookup"><span data-stu-id="0bb55-106">However, the lengths of the respective dimensions do not need to be the same.</span></span>  
  
- <span data-ttu-id="0bb55-107">**要素のデータ型。**</span><span class="sxs-lookup"><span data-stu-id="0bb55-107">**Element Data Type.**</span></span> <span data-ttu-id="0bb55-108">両方の配列の要素のデータ型は、参照型である必要があります。</span><span class="sxs-lookup"><span data-stu-id="0bb55-108">The data types of the elements of both arrays must be reference types.</span></span> <span data-ttu-id="0bb55-109">変換することはできません、`Integer`配列を`Long`配列、またはさらに、`Object`に少なくとも 1 つの値の型が関係するための配列。</span><span class="sxs-lookup"><span data-stu-id="0bb55-109">You cannot convert an `Integer` array to a `Long` array, or even to an `Object` array, because at least one value type is involved.</span></span> <span data-ttu-id="0bb55-110">詳細については、「 [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0bb55-110">For more information, see [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).</span></span>  
  
- <span data-ttu-id="0bb55-111">**でもです。**</span><span class="sxs-lookup"><span data-stu-id="0bb55-111">**Convertibility.**</span></span> <span data-ttu-id="0bb55-112">2 つの配列の要素型の間で、拡張または縮小、変換できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="0bb55-112">A conversion, either widening or narrowing, must be possible between the element types of the two arrays.</span></span> <span data-ttu-id="0bb55-113">この要件に失敗した例は、間の変換を実行しようとした、`String`とクラスの配列から派生した<xref:System.Attribute?displayProperty=nameWithType>します。</span><span class="sxs-lookup"><span data-stu-id="0bb55-113">An example that fails this requirement is an attempted conversion between a `String` array and an array of a class derived from <xref:System.Attribute?displayProperty=nameWithType>.</span></span> <span data-ttu-id="0bb55-114">これら 2 つの型が共通の何もあるし、それらの間の任意の種類の変換は存在しません。</span><span class="sxs-lookup"><span data-stu-id="0bb55-114">These two types have nothing in common, and no conversion of any kind exists between them.</span></span>  
  
 <span data-ttu-id="0bb55-115">1 つの配列型の間の変換は拡大またはそれぞれの要素の変換を拡大または縮小するかどうかに応じて縮小します。</span><span class="sxs-lookup"><span data-stu-id="0bb55-115">A conversion of one array type to another is widening or narrowing depending on whether the conversion of the respective elements is widening or narrowing.</span></span> <span data-ttu-id="0bb55-116">詳細については、「 [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0bb55-116">For more information, see [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span></span>  
  
## <a name="conversion-to-an-object-array"></a><span data-ttu-id="0bb55-117">オブジェクトの配列への変換</span><span class="sxs-lookup"><span data-stu-id="0bb55-117">Conversion to an Object Array</span></span>  
 <span data-ttu-id="0bb55-118">宣言すると、`Object`初期化せず、要素の型の配列が`Object`は初期化されていない限り、します。</span><span class="sxs-lookup"><span data-stu-id="0bb55-118">When you declare an `Object` array without initializing it, its element type is `Object` as long as it remains uninitialized.</span></span> <span data-ttu-id="0bb55-119">特定のクラスの配列に設定するとそのクラスの型にかかります。</span><span class="sxs-lookup"><span data-stu-id="0bb55-119">When you set it to an array of a specific class, it takes on the type of that class.</span></span> <span data-ttu-id="0bb55-120">ただし、基になる型は、まだ`Object`、関連付けられていないクラスの別の配列を後で設定できます。</span><span class="sxs-lookup"><span data-stu-id="0bb55-120">However, its underlying type is still `Object`, and you can subsequently set it to another array of an unrelated class.</span></span> <span data-ttu-id="0bb55-121">すべてのクラスから派生するので`Object`、任意のクラスから、配列の要素の型を変更するには、他のクラス。</span><span class="sxs-lookup"><span data-stu-id="0bb55-121">Since all classes derive from `Object`, you can change the array's element type from any class to any other class.</span></span>  
  
 <span data-ttu-id="0bb55-122">次の例では、変換が存在しない型の間で`student`と`String`から派生して両方`Object`ので、すべての割り当ては有効です。</span><span class="sxs-lookup"><span data-stu-id="0bb55-122">In the following example, no conversion exists between types `student` and `String`, but both derive from `Object`, so all assignments are valid.</span></span>  
  
```  
' Assume student has already been defined as a class.  
Dim testArray() As Object  
' testArray is still an Object array at this point.  
Dim names() As String = New String(3) {"Name0", "Name1", "Name2", "Name3"}  
testArray = New student(3) {}  
' testArray is now of type student().  
testArray = names  
' testArray is now a String array.  
```  
  
### <a name="underlying-type-of-an-array"></a><span data-ttu-id="0bb55-123">基になる配列の型</span><span class="sxs-lookup"><span data-stu-id="0bb55-123">Underlying Type of an Array</span></span>  
 <span data-ttu-id="0bb55-124">特定のクラスを使用して配列を宣言していた場合、基になる要素の種類はそのクラスです。</span><span class="sxs-lookup"><span data-stu-id="0bb55-124">If you originally declare an array with a specific class, its underlying element type is that class.</span></span> <span data-ttu-id="0bb55-125">設定した場合、その後別のクラスの配列に、2 つのクラス間の変換が必要があります。</span><span class="sxs-lookup"><span data-stu-id="0bb55-125">If you subsequently set it to an array of another class, there must be a conversion between the two classes.</span></span>  
  
 <span data-ttu-id="0bb55-126">次の例では、`students`は、`student`配列。</span><span class="sxs-lookup"><span data-stu-id="0bb55-126">In the following example, `students` is a `student` array.</span></span> <span data-ttu-id="0bb55-127">間で変換が存在しないため`String`と`student`、最後のステートメントは失敗します。</span><span class="sxs-lookup"><span data-stu-id="0bb55-127">Since no conversion exists between `String` and `student`, the last statement fails.</span></span>  
  
```  
Dim students() As student  
Dim names() As String = New String(3) {"Name0", "Name1", "Name2", "Name3"}  
students = New Student(3) {}  
' The following statement fails at compile time.  
students = names  
```  
  
## <a name="see-also"></a><span data-ttu-id="0bb55-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="0bb55-128">See also</span></span>

- [<span data-ttu-id="0bb55-129">データの種類</span><span class="sxs-lookup"><span data-stu-id="0bb55-129">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [<span data-ttu-id="0bb55-130">Visual Basic における型変換</span><span class="sxs-lookup"><span data-stu-id="0bb55-130">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [<span data-ttu-id="0bb55-131">暗黙の型変換と明示的な型変換</span><span class="sxs-lookup"><span data-stu-id="0bb55-131">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="0bb55-132">文字列とその他の型との変換</span><span class="sxs-lookup"><span data-stu-id="0bb55-132">Conversions Between Strings and Other Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)
- [<span data-ttu-id="0bb55-133">方法: オブジェクトを Visual Basic で別の型に変換します。</span><span class="sxs-lookup"><span data-stu-id="0bb55-133">How to: Convert an Object to Another Type in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)
- [<span data-ttu-id="0bb55-134">データの種類</span><span class="sxs-lookup"><span data-stu-id="0bb55-134">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="0bb55-135">データ型変換関数</span><span class="sxs-lookup"><span data-stu-id="0bb55-135">Type Conversion Functions</span></span>](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="0bb55-136">配列</span><span class="sxs-lookup"><span data-stu-id="0bb55-136">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
