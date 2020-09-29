---
title: 値型パラメーターの引き渡し - C# プログラミング ガイド
description: C# でメソッドに値型変数を値で渡す場合、どのような変更を行っても元のデータに影響を与えることはありません。 値を変更するには、参照渡しで渡します。
ms.date: 07/20/2015
helpviewer_keywords:
- method parameters [C#], value types
- parameters [C#], value
ms.assetid: 193ab86f-5f9b-4359-ac29-7cdf8afad3a6
ms.openlocfilehash: ccc97e2f6e8c6b2b8fd15206a8bcd5cd8a5a8431
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91186069"
---
# <a name="passing-value-type-parameters-c-programming-guide"></a><span data-ttu-id="6c8ed-104">値型パラメーターの引き渡し (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="6c8ed-104">Passing Value-Type Parameters (C# Programming Guide)</span></span>

<span data-ttu-id="6c8ed-105">データへの参照を含む[参照型](../../language-reference/keywords/reference-types.md)変数とは対照的に、[値型](../../language-reference/builtin-types/value-types.md)変数にはデータが直接含まれます。</span><span class="sxs-lookup"><span data-stu-id="6c8ed-105">A [value-type](../../language-reference/builtin-types/value-types.md) variable contains its data directly as opposed to a [reference-type](../../language-reference/keywords/reference-types.md) variable, which contains a reference to its data.</span></span> <span data-ttu-id="6c8ed-106">値型変数を値渡しでメソッドに渡すと、変数のコピーがメソッドに渡されます。</span><span class="sxs-lookup"><span data-stu-id="6c8ed-106">Passing a value-type variable to a method by value means passing a copy of the variable to the method.</span></span> <span data-ttu-id="6c8ed-107">メソッド内部で生じるパラメーターに対する変更の影響は、引数の変数に格納されている元のデータには及びません。</span><span class="sxs-lookup"><span data-stu-id="6c8ed-107">Any changes to the parameter that take place inside the method have no effect on the original data stored in the argument variable.</span></span> <span data-ttu-id="6c8ed-108">呼び出したメソッドで引数の値を変更する場合は、[ref](../../language-reference/keywords/ref.md) キーワードまたは [out](../../language-reference/keywords/out-parameter-modifier.md) キーワードを使用して、参照によって渡す必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c8ed-108">If you want the called method to change the value of the argument, you must pass it by reference, using the [ref](../../language-reference/keywords/ref.md) or [out](../../language-reference/keywords/out-parameter-modifier.md) keyword.</span></span> <span data-ttu-id="6c8ed-109">また、[in](../../language-reference/keywords/in-parameter-modifier.md) キーワードを使用し、参照で値パラメーターを渡してコピーを回避し、同時に値が変更されないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="6c8ed-109">You may also use the [in](../../language-reference/keywords/in-parameter-modifier.md) keyword to pass a value parameter by reference to avoid the copy while guaranteeing that the value will not be changed.</span></span> <span data-ttu-id="6c8ed-110">わかりやすくするために、次の例では `ref` を使用しています。</span><span class="sxs-lookup"><span data-stu-id="6c8ed-110">For simplicity, the following examples use `ref`.</span></span>  
  
## <a name="passing-value-types-by-value"></a><span data-ttu-id="6c8ed-111">値渡しによる値型の引き渡し</span><span class="sxs-lookup"><span data-stu-id="6c8ed-111">Passing Value Types by Value</span></span>  

 <span data-ttu-id="6c8ed-112">次の例では、値型のパラメーターを値渡しで渡す方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6c8ed-112">The following example demonstrates passing value-type parameters by value.</span></span> <span data-ttu-id="6c8ed-113">変数 `n` を、値渡しでメソッド `SquareIt` に渡します。</span><span class="sxs-lookup"><span data-stu-id="6c8ed-113">The variable `n` is passed by value to the method `SquareIt`.</span></span> <span data-ttu-id="6c8ed-114">メソッド内で生じた変更が、変数の元の値に影響することはありません。</span><span class="sxs-lookup"><span data-stu-id="6c8ed-114">Any changes that take place inside the method have no effect on the original value of the variable.</span></span>  
  
 [!code-csharp[csProgGuideParameters#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideParameters/CS/Parameters.cs#3)]  
  
 <span data-ttu-id="6c8ed-115">変数 `n` は値型です。</span><span class="sxs-lookup"><span data-stu-id="6c8ed-115">The variable `n` is a value type.</span></span> <span data-ttu-id="6c8ed-116">この変数には、そのデータである値 `5` が含まれます。</span><span class="sxs-lookup"><span data-stu-id="6c8ed-116">It contains its data, the value `5`.</span></span> <span data-ttu-id="6c8ed-117">`SquareIt` を呼び出すと、`n` の内容がパラメーター `x` にコピーされ、このパラメーターがメソッド内で 2 乗されます。</span><span class="sxs-lookup"><span data-stu-id="6c8ed-117">When `SquareIt` is invoked, the contents of `n` are copied into the parameter `x`, which is squared inside the method.</span></span> <span data-ttu-id="6c8ed-118">ただし、`Main` 内の `n` の値は、`SquareIt` メソッドを呼び出した後でも以前の値と同じままです。</span><span class="sxs-lookup"><span data-stu-id="6c8ed-118">In `Main`, however, the value of `n` is the same after calling the `SquareIt` method as it was before.</span></span> <span data-ttu-id="6c8ed-119">メソッド内で生じた変更の影響は、ローカル変数 `x` にのみ及びます。</span><span class="sxs-lookup"><span data-stu-id="6c8ed-119">The change that takes place inside the method only affects the local variable `x`.</span></span>  
  
## <a name="passing-value-types-by-reference"></a><span data-ttu-id="6c8ed-120">参照渡しによる値型の引き渡し</span><span class="sxs-lookup"><span data-stu-id="6c8ed-120">Passing Value Types by Reference</span></span>  

 <span data-ttu-id="6c8ed-121">次の例は、`ref` パラメーターとして引数を渡す点を除いて上記の例と同じです。</span><span class="sxs-lookup"><span data-stu-id="6c8ed-121">The following example is the same as the previous example, except that the argument is passed as a `ref` parameter.</span></span> <span data-ttu-id="6c8ed-122">基になる引数 `n` の値は、メソッド内で `x` が変更されると変わります。</span><span class="sxs-lookup"><span data-stu-id="6c8ed-122">The value of the underlying argument, `n`, is changed when `x` is changed in the method.</span></span>  
  
 [!code-csharp[csProgGuideParameters#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideParameters/CS/Parameters.cs#4)]  
  
 <span data-ttu-id="6c8ed-123">この例では、`n` の値が渡されるのではなく、`n` への参照が渡されています。</span><span class="sxs-lookup"><span data-stu-id="6c8ed-123">In this example, it is not the value of `n` that is passed; rather, a reference to `n` is passed.</span></span> <span data-ttu-id="6c8ed-124">つまり、パラメーター `x` は [int](../../language-reference/builtin-types/integral-numeric-types.md) ではなく、`int` への参照 (この場合は `n` への参照) となります。</span><span class="sxs-lookup"><span data-stu-id="6c8ed-124">The parameter `x` is not an [int](../../language-reference/builtin-types/integral-numeric-types.md); it is a reference to an `int`, in this case, a reference to `n`.</span></span> <span data-ttu-id="6c8ed-125">したがって、メソッド内で `x` が 2 乗された場合、`x` の参照先である `n` が実際に2乗されます。</span><span class="sxs-lookup"><span data-stu-id="6c8ed-125">Therefore, when `x` is squared inside the method, what actually is squared is what `x` refers to, `n`.</span></span>  
  
## <a name="swapping-value-types"></a><span data-ttu-id="6c8ed-126">値型のスワップ</span><span class="sxs-lookup"><span data-stu-id="6c8ed-126">Swapping Value Types</span></span>  

 <span data-ttu-id="6c8ed-127">引数の値を変更する一般的な例としてスワップ メソッドがあります。この方法では、2 つの変数をメソッドに渡してから、メソッドにより変数の中身を交換します。</span><span class="sxs-lookup"><span data-stu-id="6c8ed-127">A common example of changing the values of arguments is a swap method, where you pass two variables to the method, and the method swaps their contents.</span></span> <span data-ttu-id="6c8ed-128">スワップ メソッドへの引数の引き渡しは、参照渡しで行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c8ed-128">You must pass the arguments to the swap method by reference.</span></span> <span data-ttu-id="6c8ed-129">このようにしないと、メソッド内でパラメーターのローカル コピーどうしが交換され、呼び出し元のメソッドでは変更が行われません。</span><span class="sxs-lookup"><span data-stu-id="6c8ed-129">Otherwise, you swap local copies of the parameters inside the method, and no change occurs in the calling method.</span></span> <span data-ttu-id="6c8ed-130">次の例では、整数値が入れ替えられます。</span><span class="sxs-lookup"><span data-stu-id="6c8ed-130">The following example swaps integer values.</span></span>  
  
 [!code-csharp[csProgGuideParameters#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideParameters/CS/Parameters.cs#5)]  
  
 <span data-ttu-id="6c8ed-131">`SwapByRef` メソッドを呼び出す場合は、次の例に示すように呼び出しで `ref` キーワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="6c8ed-131">When you call the `SwapByRef` method, use the `ref` keyword in the call, as shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideParameters#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideParameters/CS/Parameters.cs#6)]  
  
## <a name="see-also"></a><span data-ttu-id="6c8ed-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="6c8ed-132">See also</span></span>

- [<span data-ttu-id="6c8ed-133">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="6c8ed-133">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="6c8ed-134">パラメーターの引き渡し</span><span class="sxs-lookup"><span data-stu-id="6c8ed-134">Passing Parameters</span></span>](./passing-parameters.md)
- [<span data-ttu-id="6c8ed-135">参照型パラメーターの引き渡し</span><span class="sxs-lookup"><span data-stu-id="6c8ed-135">Passing Reference-Type Parameters</span></span>](./passing-reference-type-parameters.md)
