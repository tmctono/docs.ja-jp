---
title: 引数の値渡しと参照渡し
ms.date: 07/20/2015
helpviewer_keywords:
- ByRef keyword [Visual Basic], passing arguments by reference
- Visual Basic code, procedures
- passing arguments [Visual Basic], by value or by reference
- ByVal keyword [Visual Basic], passing arguments by value
- arguments [Visual Basic], passing by value or by reference
- argument passing [Visual Basic], by value or by reference
ms.assetid: fd8a9de6-7178-44d5-a9bf-458d4ad907c2
ms.openlocfilehash: b7430b209f53a0a924ec587a0097178baf0075e3
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "91059221"
---
# <a name="passing-arguments-by-value-and-by-reference-visual-basic"></a><span data-ttu-id="e4a72-102">引数の値渡しと参照渡し (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e4a72-102">Passing Arguments by Value and by Reference (Visual Basic)</span></span>

<span data-ttu-id="e4a72-103">Visual Basic では、プロシージャに引数を渡すときに、"*値*" 渡しまたは "*参照*" 渡しにすることができます。</span><span class="sxs-lookup"><span data-stu-id="e4a72-103">In Visual Basic, you can pass an argument to a procedure *by value* or *by reference*.</span></span> <span data-ttu-id="e4a72-104">これは "*引渡し方法*" と呼ばれ、引数の基になる呼び出し元のコードのプログラミング要素をプロシージャが変更できるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="e4a72-104">This is known as the *passing mechanism*, and it determines whether the procedure can modify the programming element underlying the argument in the calling code.</span></span> <span data-ttu-id="e4a72-105">プロシージャの宣言で [ByVal](../../../language-reference/modifiers/byval.md) または [ByRef](../../../language-reference/modifiers/byref.md) キーワードを指定することによって、各パラメーターの引渡し方法を決定します。</span><span class="sxs-lookup"><span data-stu-id="e4a72-105">The procedure declaration determines the passing mechanism for each parameter by specifying the [ByVal](../../../language-reference/modifiers/byval.md) or [ByRef](../../../language-reference/modifiers/byref.md) keyword.</span></span>  
  
## <a name="distinctions"></a><span data-ttu-id="e4a72-106">相違点</span><span class="sxs-lookup"><span data-stu-id="e4a72-106">Distinctions</span></span>  

 <span data-ttu-id="e4a72-107">プロシージャに引数を渡すときは、相互作用するいくつかの相違点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="e4a72-107">When passing an argument to a procedure, be aware of several different distinctions that interact with each other:</span></span>  
  
- <span data-ttu-id="e4a72-108">基になるプログラミング要素が変更可能か変更不可能か</span><span class="sxs-lookup"><span data-stu-id="e4a72-108">Whether the underlying programming element is modifiable or nonmodifiable</span></span>  
  
- <span data-ttu-id="e4a72-109">引数自体が変更可能か変更不可能か</span><span class="sxs-lookup"><span data-stu-id="e4a72-109">Whether the argument itself is modifiable or nonmodifiable</span></span>  
  
- <span data-ttu-id="e4a72-110">引数が値渡しか参照渡しか</span><span class="sxs-lookup"><span data-stu-id="e4a72-110">Whether the argument is being passed by value or by reference</span></span>  
  
- <span data-ttu-id="e4a72-111">引数のデータ型が値型か参照型か</span><span class="sxs-lookup"><span data-stu-id="e4a72-111">Whether the argument data type is a value type or a reference type</span></span>  
  
 <span data-ttu-id="e4a72-112">詳細については、「[Differences Between Modifiable and Nonmodifiable Arguments (変更できる引数と変更できない引数の違い)](./differences-between-modifiable-and-nonmodifiable-arguments.md)」および「[Differences Between Passing an Argument By Value and By Reference (引数の値渡しと参照渡しの違い)](./differences-between-passing-an-argument-by-value-and-by-reference.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e4a72-112">For more information, see [Differences Between Modifiable and Nonmodifiable Arguments](./differences-between-modifiable-and-nonmodifiable-arguments.md) and [Differences Between Passing an Argument By Value and By Reference](./differences-between-passing-an-argument-by-value-and-by-reference.md).</span></span>  
  
## <a name="choice-of-passing-mechanism"></a><span data-ttu-id="e4a72-113">引渡し方法の選択</span><span class="sxs-lookup"><span data-stu-id="e4a72-113">Choice of Passing Mechanism</span></span>  

 <span data-ttu-id="e4a72-114">引数ごとに引渡し方法を慎重に選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e4a72-114">You should choose the passing mechanism carefully for each argument.</span></span>  
  
- <span data-ttu-id="e4a72-115">**保護**。</span><span class="sxs-lookup"><span data-stu-id="e4a72-115">**Protection**.</span></span> <span data-ttu-id="e4a72-116">2 つの引渡し方法のいずれかを選択する際に、最も重要な基準は、呼び出し元の変数が変更の影響を受けるかどうかです。</span><span class="sxs-lookup"><span data-stu-id="e4a72-116">In choosing between the two passing mechanisms, the most important criterion is the exposure of calling variables to change.</span></span> <span data-ttu-id="e4a72-117">引数を `ByRef` で渡す利点は、プロシージャがその引数を使用して呼び出し元のコードに値を返すことができることです。</span><span class="sxs-lookup"><span data-stu-id="e4a72-117">The advantage of passing an argument `ByRef` is that the procedure can return a value to the calling code through that argument.</span></span> <span data-ttu-id="e4a72-118">引数を `ByVal` で渡す利点は、プロシージャによって変更されないように変数を保護することです。</span><span class="sxs-lookup"><span data-stu-id="e4a72-118">The advantage of passing an argument `ByVal` is that it protects a variable from being changed by the procedure.</span></span>  
  
- <span data-ttu-id="e4a72-119">**パフォーマンス**。</span><span class="sxs-lookup"><span data-stu-id="e4a72-119">**Performance**.</span></span> <span data-ttu-id="e4a72-120">引渡し方法はコードのパフォーマンスに影響を与える可能性がありますが、通常、その違いはわずかです。</span><span class="sxs-lookup"><span data-stu-id="e4a72-120">Although the passing mechanism can affect the performance of your code, the difference is usually insignificant.</span></span> <span data-ttu-id="e4a72-121">唯一の例外は、`ByVal` で渡される値型です。</span><span class="sxs-lookup"><span data-stu-id="e4a72-121">One exception to this is a value type passed `ByVal`.</span></span> <span data-ttu-id="e4a72-122">この場合、Visual Basic では引数のデータ コンテンツ全体をコピーします。</span><span class="sxs-lookup"><span data-stu-id="e4a72-122">In this case, Visual Basic copies the entire data contents of the argument.</span></span> <span data-ttu-id="e4a72-123">そのため、構造体などの大きな値型の場合、`ByRef` で渡す方が効率的です。</span><span class="sxs-lookup"><span data-stu-id="e4a72-123">Therefore, for a large value type such as a structure, it can be more efficient to pass it `ByRef`.</span></span>  
  
     <span data-ttu-id="e4a72-124">参照型の場合、データへのポインターだけがコピーされます (32 ビット プラットフォームでは 4 バイト、64 ビット プラットフォームでは 8 バイト)。</span><span class="sxs-lookup"><span data-stu-id="e4a72-124">For reference types, only the pointer to the data is copied (four bytes on 32-bit platforms, eight bytes on 64-bit platforms).</span></span> <span data-ttu-id="e4a72-125">そのため、パフォーマンスを損なうことなく、`String` または `Object` 型の引数を値渡しにすることができます。</span><span class="sxs-lookup"><span data-stu-id="e4a72-125">Therefore, you can pass arguments of type `String` or `Object` by value without harming performance.</span></span>  
  
## <a name="determination-of-the-passing-mechanism"></a><span data-ttu-id="e4a72-126">引渡し方法の決定</span><span class="sxs-lookup"><span data-stu-id="e4a72-126">Determination of the Passing Mechanism</span></span>  

 <span data-ttu-id="e4a72-127">プロシージャの宣言で、各パラメーターの引渡し方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="e4a72-127">The procedure declaration specifies the passing mechanism for each parameter.</span></span> <span data-ttu-id="e4a72-128">呼び出し元のコードは、引渡し方法 `ByVal` をオーバーライドできません。</span><span class="sxs-lookup"><span data-stu-id="e4a72-128">The calling code can't override a `ByVal` mechanism.</span></span>  
  
 <span data-ttu-id="e4a72-129">パラメーターが `ByRef` で宣言されている場合、呼び出し元のコードは、呼び出しで引数名をかっこで囲むことによって、引渡し方法を強制的に `ByVal` にすることができます。</span><span class="sxs-lookup"><span data-stu-id="e4a72-129">If a parameter is declared with `ByRef`, the calling code can force the mechanism to `ByVal` by enclosing the argument name in parentheses in the call.</span></span> <span data-ttu-id="e4a72-130">詳細については、「[方法:方法: 引数の値渡しを強制する](./how-to-force-an-argument-to-be-passed-by-value.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e4a72-130">For more information, see [How to: Force an Argument to Be Passed by Value](./how-to-force-an-argument-to-be-passed-by-value.md).</span></span>  
  
 <span data-ttu-id="e4a72-131">Visual Basic の既定では、引数は値渡しになります。</span><span class="sxs-lookup"><span data-stu-id="e4a72-131">The default in Visual Basic is to pass arguments by value.</span></span>  
  
## <a name="when-to-pass-an-argument-by-value"></a><span data-ttu-id="e4a72-132">引数を値渡しにする場合</span><span class="sxs-lookup"><span data-stu-id="e4a72-132">When to Pass an Argument by Value</span></span>  
  
- <span data-ttu-id="e4a72-133">引数の基になる呼び出し元のコードの要素が変更不可能な要素である場合は、対応するパラメーターを [ByVal](../../../language-reference/modifiers/byval.md) で宣言します。</span><span class="sxs-lookup"><span data-stu-id="e4a72-133">If the calling code element underlying the argument is a nonmodifiable element, declare the corresponding parameter [ByVal](../../../language-reference/modifiers/byval.md).</span></span> <span data-ttu-id="e4a72-134">コードは、変更不可能な要素の値を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="e4a72-134">No code can change the value of a nonmodifiable element.</span></span>  
  
- <span data-ttu-id="e4a72-135">基になる要素が変更可能であっても、プロシージャがその値を変更できないようにする場合は、パラメーターを `ByVal` で宣言します。</span><span class="sxs-lookup"><span data-stu-id="e4a72-135">If the underlying element is modifiable, but you do not want the procedure to be able to change its value, declare the parameter `ByVal`.</span></span> <span data-ttu-id="e4a72-136">値渡しされた変更可能な要素の値を変更できるのは、呼び出し元のコードだけです。</span><span class="sxs-lookup"><span data-stu-id="e4a72-136">Only the calling code can change the value of a modifiable element passed by value.</span></span>  
  
## <a name="when-to-pass-an-argument-by-reference"></a><span data-ttu-id="e4a72-137">引数を参照渡しにする場合</span><span class="sxs-lookup"><span data-stu-id="e4a72-137">When to Pass an Argument by Reference</span></span>  
  
- <span data-ttu-id="e4a72-138">プロシージャが呼び出し元のコードの基になる要素を変更する必要がある場合は、対応するパラメーターを [ByRef](../../../language-reference/modifiers/byref.md) で宣言します。</span><span class="sxs-lookup"><span data-stu-id="e4a72-138">If the procedure has a genuine need to change the underlying element in the calling code, declare the corresponding parameter [ByRef](../../../language-reference/modifiers/byref.md).</span></span>  
  
- <span data-ttu-id="e4a72-139">コードを正しく実行するには、呼び出し元のコードの基になる要素をプロシージャが変更する必要がある場合は、パラメーターを `ByRef` で宣言します。</span><span class="sxs-lookup"><span data-stu-id="e4a72-139">If the correct execution of the code depends on the procedure changing the underlying element in the calling code, declare the parameter `ByRef`.</span></span> <span data-ttu-id="e4a72-140">値渡しにした場合や、呼び出し元のコードで引数をかっこで囲むことによって引渡し方法 `ByRef` をオーバーライドした場合、プロシージャ呼び出しによって予期しない結果が生じる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e4a72-140">If you pass it by value, or if the calling code overrides the `ByRef` passing mechanism by enclosing the argument in parentheses, the procedure call might produce unexpected results.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e4a72-141">例</span><span class="sxs-lookup"><span data-stu-id="e4a72-141">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="e4a72-142">説明</span><span class="sxs-lookup"><span data-stu-id="e4a72-142">Description</span></span>  

 <span data-ttu-id="e4a72-143">次の例は、引数を値渡しにする場合と参照渡しにする場合を示しています。</span><span class="sxs-lookup"><span data-stu-id="e4a72-143">The following example illustrates when to pass arguments by value and when to pass them by reference.</span></span> <span data-ttu-id="e4a72-144">`Calculate` プロシージャには、`ByVal` パラメーターと `ByRef` パラメーターの両方があります。</span><span class="sxs-lookup"><span data-stu-id="e4a72-144">Procedure `Calculate` has both a `ByVal` and a `ByRef` parameter.</span></span> <span data-ttu-id="e4a72-145">このプロシージャのタスクは、指定された `rate` (金利) と `debt` (合計金額) を使用して、`debt` の新しい値を計算することです。これは、`debt` の元の値に金利を適用した結果です。</span><span class="sxs-lookup"><span data-stu-id="e4a72-145">Given an interest rate, `rate`, and a sum of money, `debt`, the task of the procedure is to calculate a new value for `debt` that is the result of applying the interest rate to the original value of `debt`.</span></span> <span data-ttu-id="e4a72-146">`debt` は `ByRef` パラメーターであるため、新しい合計は、`debt` に対応する呼び出し元のコードの引数の値に反映されます。</span><span class="sxs-lookup"><span data-stu-id="e4a72-146">Because `debt` is a `ByRef` parameter, the new total is reflected in the value of the argument in the calling code that corresponds to `debt`.</span></span> <span data-ttu-id="e4a72-147">`Calculate` が値を変更しないようにする必要があるため、`rate` パラメーターは `ByVal` パラメーターです。</span><span class="sxs-lookup"><span data-stu-id="e4a72-147">Parameter `rate` is a `ByVal` parameter because `Calculate` should not change its value.</span></span>  
  
### <a name="code"></a><span data-ttu-id="e4a72-148">コード</span><span class="sxs-lookup"><span data-stu-id="e4a72-148">Code</span></span>  

 [!code-vb[VbVbcnProcedures#74](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class2.vb#74)]  
  
## <a name="see-also"></a><span data-ttu-id="e4a72-149">関連項目</span><span class="sxs-lookup"><span data-stu-id="e4a72-149">See also</span></span>

- [<span data-ttu-id="e4a72-150">手順</span><span class="sxs-lookup"><span data-stu-id="e4a72-150">Procedures</span></span>](./index.md)
- [<span data-ttu-id="e4a72-151">プロシージャのパラメーターと引数</span><span class="sxs-lookup"><span data-stu-id="e4a72-151">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="e4a72-152">方法: プロシージャに引数を渡す</span><span class="sxs-lookup"><span data-stu-id="e4a72-152">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="e4a72-153">方法: プロシージャ引数の値を変更する</span><span class="sxs-lookup"><span data-stu-id="e4a72-153">How to: Change the Value of a Procedure Argument</span></span>](./how-to-change-the-value-of-a-procedure-argument.md)
- [<span data-ttu-id="e4a72-154">方法: プロシージャ引数の値が変更されないように保護する</span><span class="sxs-lookup"><span data-stu-id="e4a72-154">How to: Protect a Procedure Argument Against Value Changes</span></span>](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [<span data-ttu-id="e4a72-155">方法: 引数の値渡しを強制する</span><span class="sxs-lookup"><span data-stu-id="e4a72-155">How to: Force an Argument to Be Passed by Value</span></span>](./how-to-force-an-argument-to-be-passed-by-value.md)
- [<span data-ttu-id="e4a72-156">位置と名前による引数渡し</span><span class="sxs-lookup"><span data-stu-id="e4a72-156">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)
- [<span data-ttu-id="e4a72-157">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="e4a72-157">Value Types and Reference Types</span></span>](../data-types/value-types-and-reference-types.md)
