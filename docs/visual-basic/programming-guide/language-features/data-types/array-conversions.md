---
title: 配列の変換
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
ms.openlocfilehash: 622ebe8a77f2dfbeb35e0408be48622d93d409c6
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345858"
---
# <a name="array-conversions-visual-basic"></a><span data-ttu-id="3da3a-102">配列の変換 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3da3a-102">Array Conversions (Visual Basic)</span></span>
<span data-ttu-id="3da3a-103">You can convert an array type to a different array type provided you meet the following conditions:</span><span class="sxs-lookup"><span data-stu-id="3da3a-103">You can convert an array type to a different array type provided you meet the following conditions:</span></span>  
  
- <span data-ttu-id="3da3a-104">**Equal Rank.**</span><span class="sxs-lookup"><span data-stu-id="3da3a-104">**Equal Rank.**</span></span> <span data-ttu-id="3da3a-105">The ranks of the two arrays must be the same, that is, they must have the same number of dimensions.</span><span class="sxs-lookup"><span data-stu-id="3da3a-105">The ranks of the two arrays must be the same, that is, they must have the same number of dimensions.</span></span> <span data-ttu-id="3da3a-106">However, the lengths of the respective dimensions do not need to be the same.</span><span class="sxs-lookup"><span data-stu-id="3da3a-106">However, the lengths of the respective dimensions do not need to be the same.</span></span>  
  
- <span data-ttu-id="3da3a-107">**Element Data Type.**</span><span class="sxs-lookup"><span data-stu-id="3da3a-107">**Element Data Type.**</span></span> <span data-ttu-id="3da3a-108">The data types of the elements of both arrays must be reference types.</span><span class="sxs-lookup"><span data-stu-id="3da3a-108">The data types of the elements of both arrays must be reference types.</span></span> <span data-ttu-id="3da3a-109">You cannot convert an `Integer` array to a `Long` array, or even to an `Object` array, because at least one value type is involved.</span><span class="sxs-lookup"><span data-stu-id="3da3a-109">You cannot convert an `Integer` array to a `Long` array, or even to an `Object` array, because at least one value type is involved.</span></span> <span data-ttu-id="3da3a-110">詳細については、「 [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3da3a-110">For more information, see [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).</span></span>  
  
- <span data-ttu-id="3da3a-111">**Convertibility.**</span><span class="sxs-lookup"><span data-stu-id="3da3a-111">**Convertibility.**</span></span> <span data-ttu-id="3da3a-112">A conversion, either widening or narrowing, must be possible between the element types of the two arrays.</span><span class="sxs-lookup"><span data-stu-id="3da3a-112">A conversion, either widening or narrowing, must be possible between the element types of the two arrays.</span></span> <span data-ttu-id="3da3a-113">An example that fails this requirement is an attempted conversion between a `String` array and an array of a class derived from <xref:System.Attribute?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="3da3a-113">An example that fails this requirement is an attempted conversion between a `String` array and an array of a class derived from <xref:System.Attribute?displayProperty=nameWithType>.</span></span> <span data-ttu-id="3da3a-114">These two types have nothing in common, and no conversion of any kind exists between them.</span><span class="sxs-lookup"><span data-stu-id="3da3a-114">These two types have nothing in common, and no conversion of any kind exists between them.</span></span>  
  
 <span data-ttu-id="3da3a-115">A conversion of one array type to another is widening or narrowing depending on whether the conversion of the respective elements is widening or narrowing.</span><span class="sxs-lookup"><span data-stu-id="3da3a-115">A conversion of one array type to another is widening or narrowing depending on whether the conversion of the respective elements is widening or narrowing.</span></span> <span data-ttu-id="3da3a-116">詳細については、「 [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3da3a-116">For more information, see [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span></span>  
  
## <a name="conversion-to-an-object-array"></a><span data-ttu-id="3da3a-117">Conversion to an Object Array</span><span class="sxs-lookup"><span data-stu-id="3da3a-117">Conversion to an Object Array</span></span>  
 <span data-ttu-id="3da3a-118">When you declare an `Object` array without initializing it, its element type is `Object` as long as it remains uninitialized.</span><span class="sxs-lookup"><span data-stu-id="3da3a-118">When you declare an `Object` array without initializing it, its element type is `Object` as long as it remains uninitialized.</span></span> <span data-ttu-id="3da3a-119">When you set it to an array of a specific class, it takes on the type of that class.</span><span class="sxs-lookup"><span data-stu-id="3da3a-119">When you set it to an array of a specific class, it takes on the type of that class.</span></span> <span data-ttu-id="3da3a-120">However, its underlying type is still `Object`, and you can subsequently set it to another array of an unrelated class.</span><span class="sxs-lookup"><span data-stu-id="3da3a-120">However, its underlying type is still `Object`, and you can subsequently set it to another array of an unrelated class.</span></span> <span data-ttu-id="3da3a-121">Since all classes derive from `Object`, you can change the array's element type from any class to any other class.</span><span class="sxs-lookup"><span data-stu-id="3da3a-121">Since all classes derive from `Object`, you can change the array's element type from any class to any other class.</span></span>  
  
 <span data-ttu-id="3da3a-122">In the following example, no conversion exists between types `student` and `String`, but both derive from `Object`, so all assignments are valid.</span><span class="sxs-lookup"><span data-stu-id="3da3a-122">In the following example, no conversion exists between types `student` and `String`, but both derive from `Object`, so all assignments are valid.</span></span>  
  
```vb  
' Assume student has already been defined as a class.  
Dim testArray() As Object  
' testArray is still an Object array at this point.  
Dim names() As String = New String(3) {"Name0", "Name1", "Name2", "Name3"}  
testArray = New student(3) {}  
' testArray is now of type student().  
testArray = names  
' testArray is now a String array.  
```  
  
### <a name="underlying-type-of-an-array"></a><span data-ttu-id="3da3a-123">Underlying Type of an Array</span><span class="sxs-lookup"><span data-stu-id="3da3a-123">Underlying Type of an Array</span></span>  
 <span data-ttu-id="3da3a-124">If you originally declare an array with a specific class, its underlying element type is that class.</span><span class="sxs-lookup"><span data-stu-id="3da3a-124">If you originally declare an array with a specific class, its underlying element type is that class.</span></span> <span data-ttu-id="3da3a-125">If you subsequently set it to an array of another class, there must be a conversion between the two classes.</span><span class="sxs-lookup"><span data-stu-id="3da3a-125">If you subsequently set it to an array of another class, there must be a conversion between the two classes.</span></span>  
  
 <span data-ttu-id="3da3a-126">In the following example, `students` is a `student` array.</span><span class="sxs-lookup"><span data-stu-id="3da3a-126">In the following example, `students` is a `student` array.</span></span> <span data-ttu-id="3da3a-127">Since no conversion exists between `String` and `student`, the last statement fails.</span><span class="sxs-lookup"><span data-stu-id="3da3a-127">Since no conversion exists between `String` and `student`, the last statement fails.</span></span>  
  
```vb  
Dim students() As student  
Dim names() As String = New String(3) {"Name0", "Name1", "Name2", "Name3"}  
students = New Student(3) {}  
' The following statement fails at compile time.  
students = names  
```  
  
## <a name="see-also"></a><span data-ttu-id="3da3a-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="3da3a-128">See also</span></span>

- [<span data-ttu-id="3da3a-129">データの種類</span><span class="sxs-lookup"><span data-stu-id="3da3a-129">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [<span data-ttu-id="3da3a-130">Type Conversions in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3da3a-130">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [<span data-ttu-id="3da3a-131">暗黙の型変換と明示的な型変換</span><span class="sxs-lookup"><span data-stu-id="3da3a-131">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="3da3a-132">文字列とその他の型との変換</span><span class="sxs-lookup"><span data-stu-id="3da3a-132">Conversions Between Strings and Other Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)
- [<span data-ttu-id="3da3a-133">How to: Convert an Object to Another Type in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3da3a-133">How to: Convert an Object to Another Type in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)
- [<span data-ttu-id="3da3a-134">データの種類</span><span class="sxs-lookup"><span data-stu-id="3da3a-134">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="3da3a-135">データ型変換関数</span><span class="sxs-lookup"><span data-stu-id="3da3a-135">Type Conversion Functions</span></span>](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="3da3a-136">配列</span><span class="sxs-lookup"><span data-stu-id="3da3a-136">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
