---
title: 引数の値渡しと参照渡し (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- ByRef keyword [Visual Basic], passing arguments by reference
- Visual Basic code, procedures
- passing arguments [Visual Basic], by value or by reference
- ByVal keyword [Visual Basic], passing arguments by value
- arguments [Visual Basic], passing by value or by reference
- argument passing [Visual Basic], by value or by reference
ms.assetid: fd8a9de6-7178-44d5-a9bf-458d4ad907c2
ms.openlocfilehash: eb2260c6547d4f1cd7d9c23445ac38ac600e3535
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64638865"
---
# <a name="passing-arguments-by-value-and-by-reference-visual-basic"></a><span data-ttu-id="09b17-102">引数の値渡しと参照渡し (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="09b17-102">Passing Arguments by Value and by Reference (Visual Basic)</span></span>
<span data-ttu-id="09b17-103">Visual basic では、プロシージャに引数を渡すことができます*値によって*または*参照によって*します。</span><span class="sxs-lookup"><span data-stu-id="09b17-103">In Visual Basic, you can pass an argument to a procedure *by value* or *by reference*.</span></span> <span data-ttu-id="09b17-104">呼ばれます、*渡し*、し、プロシージャが呼び出し元のコードで引数を基になるプログラミングの要素を変更できるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="09b17-104">This is known as the *passing mechanism*, and it determines whether the procedure can modify the programming element underlying the argument in the calling code.</span></span> <span data-ttu-id="09b17-105">プロシージャ宣言では、各パラメーターの引き渡し方法を決定を指定して、 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)または[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)キーワード。</span><span class="sxs-lookup"><span data-stu-id="09b17-105">The procedure declaration determines the passing mechanism for each parameter by specifying the [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) keyword.</span></span>  
  
## <a name="distinctions"></a><span data-ttu-id="09b17-106">違いがあります。</span><span class="sxs-lookup"><span data-stu-id="09b17-106">Distinctions</span></span>  
 <span data-ttu-id="09b17-107">プロシージャに引数を渡すときは、相互作用をいくつかの違いに注意してください。</span><span class="sxs-lookup"><span data-stu-id="09b17-107">When passing an argument to a procedure, be aware of several different distinctions that interact with each other:</span></span>  
  
- <span data-ttu-id="09b17-108">基になるプログラミング要素が変更可能または変更不可能なのかどうか</span><span class="sxs-lookup"><span data-stu-id="09b17-108">Whether the underlying programming element is modifiable or nonmodifiable</span></span>  
  
- <span data-ttu-id="09b17-109">引数自体が変更可能または変更不可能なのかどうか</span><span class="sxs-lookup"><span data-stu-id="09b17-109">Whether the argument itself is modifiable or nonmodifiable</span></span>  
  
- <span data-ttu-id="09b17-110">値渡しまたは参照によって引数が渡されるかどうか</span><span class="sxs-lookup"><span data-stu-id="09b17-110">Whether the argument is being passed by value or by reference</span></span>  
  
- <span data-ttu-id="09b17-111">引数のデータ型は、値型または参照型かどうか</span><span class="sxs-lookup"><span data-stu-id="09b17-111">Whether the argument data type is a value type or a reference type</span></span>  
  
 <span data-ttu-id="09b17-112">詳細については、次を参照してください。[変更の間の相違点と変更できない引数](./differences-between-modifiable-and-nonmodifiable-arguments.md)と[の相違点の間の値と参照渡しによって引数を渡す](./differences-between-passing-an-argument-by-value-and-by-reference.md)します。</span><span class="sxs-lookup"><span data-stu-id="09b17-112">For more information, see [Differences Between Modifiable and Nonmodifiable Arguments](./differences-between-modifiable-and-nonmodifiable-arguments.md) and [Differences Between Passing an Argument By Value and By Reference](./differences-between-passing-an-argument-by-value-and-by-reference.md).</span></span>  
  
## <a name="choice-of-passing-mechanism"></a><span data-ttu-id="09b17-113">渡す機能の選択</span><span class="sxs-lookup"><span data-stu-id="09b17-113">Choice of Passing Mechanism</span></span>  
 <span data-ttu-id="09b17-114">慎重に各引数の引き渡し方法を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="09b17-114">You should choose the passing mechanism carefully for each argument.</span></span>  
  
- <span data-ttu-id="09b17-115">**保護**します。</span><span class="sxs-lookup"><span data-stu-id="09b17-115">**Protection**.</span></span> <span data-ttu-id="09b17-116">2 つの引数を渡す方法の選択、最も重要な条件を変更する変数を呼び出すことのリスクは。</span><span class="sxs-lookup"><span data-stu-id="09b17-116">In choosing between the two passing mechanisms, the most important criterion is the exposure of calling variables to change.</span></span> <span data-ttu-id="09b17-117">引数を渡すことの利点は、`ByRef`プロシージャがその引数から呼び出し元コードに値を返すことができます。</span><span class="sxs-lookup"><span data-stu-id="09b17-117">The advantage of passing an argument `ByRef` is that the procedure can return a value to the calling code through that argument.</span></span> <span data-ttu-id="09b17-118">引数を渡すことの利点は、`ByVal`からプロシージャによって変更されている変数を防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="09b17-118">The advantage of passing an argument `ByVal` is that it protects a variable from being changed by the procedure.</span></span>  
  
- <span data-ttu-id="09b17-119">**パフォーマンス**します。</span><span class="sxs-lookup"><span data-stu-id="09b17-119">**Performance**.</span></span> <span data-ttu-id="09b17-120">引き渡し方法が、コードのパフォーマンスに影響を与えることができますが、違いは通常の意味ではありません。</span><span class="sxs-lookup"><span data-stu-id="09b17-120">Although the passing mechanism can affect the performance of your code, the difference is usually insignificant.</span></span> <span data-ttu-id="09b17-121">1 つの例外は渡された値型`ByVal`します。</span><span class="sxs-lookup"><span data-stu-id="09b17-121">One exception to this is a value type passed `ByVal`.</span></span> <span data-ttu-id="09b17-122">この場合は、Visual Basic では、引数のデータ全体の内容をコピーします。</span><span class="sxs-lookup"><span data-stu-id="09b17-122">In this case, Visual Basic copies the entire data contents of the argument.</span></span> <span data-ttu-id="09b17-123">そのため、構造体などの大きな値型はなりますに渡すより効率的な`ByRef`します。</span><span class="sxs-lookup"><span data-stu-id="09b17-123">Therefore, for a large value type such as a structure, it can be more efficient to pass it `ByRef`.</span></span>  
  
     <span data-ttu-id="09b17-124">参照型でデータへのポインターにのみ、コピー (4 バイト、64 ビット プラットフォームでは 8 バイトである 32 ビット プラットフォームで) です。</span><span class="sxs-lookup"><span data-stu-id="09b17-124">For reference types, only the pointer to the data is copied (four bytes on 32-bit platforms, eight bytes on 64-bit platforms).</span></span> <span data-ttu-id="09b17-125">そのため、型の引数を渡すことができます`String`または`Object`パフォーマンスを損なわずに値渡し。</span><span class="sxs-lookup"><span data-stu-id="09b17-125">Therefore, you can pass arguments of type `String` or `Object` by value without harming performance.</span></span>  
  
## <a name="determination-of-the-passing-mechanism"></a><span data-ttu-id="09b17-126">引数渡しの方法の決定</span><span class="sxs-lookup"><span data-stu-id="09b17-126">Determination of the Passing Mechanism</span></span>  
 <span data-ttu-id="09b17-127">プロシージャ宣言では、各パラメーターの引き渡し方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="09b17-127">The procedure declaration specifies the passing mechanism for each parameter.</span></span> <span data-ttu-id="09b17-128">呼び出し元のコードがオーバーライドすることはできません、`ByVal`メカニズム。</span><span class="sxs-lookup"><span data-stu-id="09b17-128">The calling code can't override a `ByVal` mechanism.</span></span>  
  
 <span data-ttu-id="09b17-129">パラメーターが宣言されている場合`ByRef`、呼び出し元のコードにするためのメカニズムを強制できます`ByVal`で引数名を呼び出しにかっこで囲みます。</span><span class="sxs-lookup"><span data-stu-id="09b17-129">If a parameter is declared with `ByRef`, the calling code can force the mechanism to `ByVal` by enclosing the argument name in parentheses in the call.</span></span> <span data-ttu-id="09b17-130">詳細については、「[方法 :引数の値渡しを強制](./how-to-force-an-argument-to-be-passed-by-value.md)します。</span><span class="sxs-lookup"><span data-stu-id="09b17-130">For more information, see [How to: Force an Argument to Be Passed by Value](./how-to-force-an-argument-to-be-passed-by-value.md).</span></span>  
  
 <span data-ttu-id="09b17-131">Visual Basic では既定では、引数を値渡しです。</span><span class="sxs-lookup"><span data-stu-id="09b17-131">The default in Visual Basic is to pass arguments by value.</span></span>  
  
## <a name="when-to-pass-an-argument-by-value"></a><span data-ttu-id="09b17-132">引数を値渡しする場合</span><span class="sxs-lookup"><span data-stu-id="09b17-132">When to Pass an Argument by Value</span></span>  
  
- <span data-ttu-id="09b17-133">呼び出し元に、引数の基になるコード要素が変更不可能な要素の場合は、対応するパラメーターを宣言[ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)します。</span><span class="sxs-lookup"><span data-stu-id="09b17-133">If the calling code element underlying the argument is a nonmodifiable element, declare the corresponding parameter [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).</span></span> <span data-ttu-id="09b17-134">変更不可能な要素の値は、コードでは変更ありません。</span><span class="sxs-lookup"><span data-stu-id="09b17-134">No code can change the value of a nonmodifiable element.</span></span>  
  
- <span data-ttu-id="09b17-135">基になる要素は変更できますが、その値を変更できるプロシージャしたくない場合、パラメーターを宣言`ByVal`します。</span><span class="sxs-lookup"><span data-stu-id="09b17-135">If the underlying element is modifiable, but you do not want the procedure to be able to change its value, declare the parameter `ByVal`.</span></span> <span data-ttu-id="09b17-136">呼び出し元のコードだけでは、値渡し変更可能な要素の値を変更できます。</span><span class="sxs-lookup"><span data-stu-id="09b17-136">Only the calling code can change the value of a modifiable element passed by value.</span></span>  
  
## <a name="when-to-pass-an-argument-by-reference"></a><span data-ttu-id="09b17-137">参照渡しで引数を渡す場合</span><span class="sxs-lookup"><span data-stu-id="09b17-137">When to Pass an Argument by Reference</span></span>  
  
- <span data-ttu-id="09b17-138">プロシージャの呼び出し元のコードで基になる要素を変更する必要が本当にある場合は、対応するパラメーターを宣言[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)します。</span><span class="sxs-lookup"><span data-stu-id="09b17-138">If the procedure has a genuine need to change the underlying element in the calling code, declare the corresponding parameter [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md).</span></span>  
  
- <span data-ttu-id="09b17-139">コードの適切な実行は、呼び出し元のコード内の基になる要素を変更するプロシージャに依存している場合は、パラメーターを宣言`ByRef`します。</span><span class="sxs-lookup"><span data-stu-id="09b17-139">If the correct execution of the code depends on the procedure changing the underlying element in the calling code, declare the parameter `ByRef`.</span></span> <span data-ttu-id="09b17-140">値を値によって渡す場合、または呼び出し元のコードをオーバーライドする場合、`ByRef`メカニズムの引数をかっこで囲んでを渡し、プロシージャの呼び出しが予期しない結果を生じる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="09b17-140">If you pass it by value, or if the calling code overrides the `ByRef` passing mechanism by enclosing the argument in parentheses, the procedure call might produce unexpected results.</span></span>  
  
## <a name="example"></a><span data-ttu-id="09b17-141">例</span><span class="sxs-lookup"><span data-stu-id="09b17-141">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="09b17-142">説明</span><span class="sxs-lookup"><span data-stu-id="09b17-142">Description</span></span>  
 <span data-ttu-id="09b17-143">次の例は、引数を値渡しする場合と参照渡しする場合を示しています。</span><span class="sxs-lookup"><span data-stu-id="09b17-143">The following example illustrates when to pass arguments by value and when to pass them by reference.</span></span> <span data-ttu-id="09b17-144">プロシージャ`Calculate`両方を持つ、`ByVal`と`ByRef`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="09b17-144">Procedure `Calculate` has both a `ByVal` and a `ByRef` parameter.</span></span> <span data-ttu-id="09b17-145">利率を指定された`rate`との合計金額、`debt`の新しい値を計算するが、プロシージャのタスク`debt`の元の値を利率を適用した結果である`debt`します。</span><span class="sxs-lookup"><span data-stu-id="09b17-145">Given an interest rate, `rate`, and a sum of money, `debt`, the task of the procedure is to calculate a new value for `debt` that is the result of applying the interest rate to the original value of `debt`.</span></span> <span data-ttu-id="09b17-146">`debt`は、`ByRef`パラメーターに対応する呼び出し元のコードで引数の値に、新しい合計が反映されます`debt`します。</span><span class="sxs-lookup"><span data-stu-id="09b17-146">Because `debt` is a `ByRef` parameter, the new total is reflected in the value of the argument in the calling code that corresponds to `debt`.</span></span> <span data-ttu-id="09b17-147">パラメーター`rate`は、`ByVal`パラメーターのため`Calculate`その値を変更しないでください。</span><span class="sxs-lookup"><span data-stu-id="09b17-147">Parameter `rate` is a `ByVal` parameter because `Calculate` should not change its value.</span></span>  
  
### <a name="code"></a><span data-ttu-id="09b17-148">コード</span><span class="sxs-lookup"><span data-stu-id="09b17-148">Code</span></span>  
 [!code-vb[VbVbcnProcedures#74](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class2.vb#74)]  
  
## <a name="see-also"></a><span data-ttu-id="09b17-149">関連項目</span><span class="sxs-lookup"><span data-stu-id="09b17-149">See also</span></span>

- [<span data-ttu-id="09b17-150">プロシージャ</span><span class="sxs-lookup"><span data-stu-id="09b17-150">Procedures</span></span>](./index.md)
- [<span data-ttu-id="09b17-151">プロシージャのパラメーターと引数</span><span class="sxs-lookup"><span data-stu-id="09b17-151">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="09b17-152">方法: プロシージャに引数を渡す</span><span class="sxs-lookup"><span data-stu-id="09b17-152">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="09b17-153">方法: プロシージャ引数の値を変更します。</span><span class="sxs-lookup"><span data-stu-id="09b17-153">How to: Change the Value of a Procedure Argument</span></span>](./how-to-change-the-value-of-a-procedure-argument.md)
- [<span data-ttu-id="09b17-154">方法: プロシージャ引数の値が変化しません。</span><span class="sxs-lookup"><span data-stu-id="09b17-154">How to: Protect a Procedure Argument Against Value Changes</span></span>](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [<span data-ttu-id="09b17-155">方法: 引数の値渡しを強制します。</span><span class="sxs-lookup"><span data-stu-id="09b17-155">How to: Force an Argument to Be Passed by Value</span></span>](./how-to-force-an-argument-to-be-passed-by-value.md)
- [<span data-ttu-id="09b17-156">位置と名前による引数渡し</span><span class="sxs-lookup"><span data-stu-id="09b17-156">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)
- [<span data-ttu-id="09b17-157">値型と参照型</span><span class="sxs-lookup"><span data-stu-id="09b17-157">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
