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
ms.openlocfilehash: 28e59753a35ab67b15fbc549df5bb8a3489aba5a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352606"
---
# <a name="passing-arguments-by-value-and-by-reference-visual-basic"></a><span data-ttu-id="90706-102">引数の値渡しと参照渡し (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="90706-102">Passing Arguments by Value and by Reference (Visual Basic)</span></span>
<span data-ttu-id="90706-103">Visual Basic では、値または*参照に* *よって*プロシージャに引数を渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="90706-103">In Visual Basic, you can pass an argument to a procedure *by value* or *by reference*.</span></span> <span data-ttu-id="90706-104">これは、*引き渡し機構*と呼ばれ、プロシージャが呼び出し元のコードの引数の基になるプログラミング要素を変更できるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="90706-104">This is known as the *passing mechanism*, and it determines whether the procedure can modify the programming element underlying the argument in the calling code.</span></span> <span data-ttu-id="90706-105">プロシージャ宣言は、 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)または[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)キーワードを指定することによって、各パラメーターの引き渡し機構を決定します。</span><span class="sxs-lookup"><span data-stu-id="90706-105">The procedure declaration determines the passing mechanism for each parameter by specifying the [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) keyword.</span></span>  
  
## <a name="distinctions"></a><span data-ttu-id="90706-106">区分</span><span class="sxs-lookup"><span data-stu-id="90706-106">Distinctions</span></span>  
 <span data-ttu-id="90706-107">プロシージャに引数を渡すときは、相互作用するいくつかの異なる違いに注意してください。</span><span class="sxs-lookup"><span data-stu-id="90706-107">When passing an argument to a procedure, be aware of several different distinctions that interact with each other:</span></span>  
  
- <span data-ttu-id="90706-108">基になるプログラミング要素が変更可能か変更不可能か</span><span class="sxs-lookup"><span data-stu-id="90706-108">Whether the underlying programming element is modifiable or nonmodifiable</span></span>  
  
- <span data-ttu-id="90706-109">引数自体が変更可能か変更不可能か</span><span class="sxs-lookup"><span data-stu-id="90706-109">Whether the argument itself is modifiable or nonmodifiable</span></span>  
  
- <span data-ttu-id="90706-110">引数が値渡しか参照渡しか</span><span class="sxs-lookup"><span data-stu-id="90706-110">Whether the argument is being passed by value or by reference</span></span>  
  
- <span data-ttu-id="90706-111">引数のデータ型が値型であるか、参照型であるか</span><span class="sxs-lookup"><span data-stu-id="90706-111">Whether the argument data type is a value type or a reference type</span></span>  
  
 <span data-ttu-id="90706-112">詳細については、「変更可能な引数と変更できない[引数の違い](./differences-between-modifiable-and-nonmodifiable-arguments.md)」と「[引数を値で渡す場合と参照渡しの](./differences-between-passing-an-argument-by-value-and-by-reference.md)違い」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="90706-112">For more information, see [Differences Between Modifiable and Nonmodifiable Arguments](./differences-between-modifiable-and-nonmodifiable-arguments.md) and [Differences Between Passing an Argument By Value and By Reference](./differences-between-passing-an-argument-by-value-and-by-reference.md).</span></span>  
  
## <a name="choice-of-passing-mechanism"></a><span data-ttu-id="90706-113">渡すメカニズムの選択</span><span class="sxs-lookup"><span data-stu-id="90706-113">Choice of Passing Mechanism</span></span>  
 <span data-ttu-id="90706-114">引数ごとに、渡すメカニズムを慎重に選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="90706-114">You should choose the passing mechanism carefully for each argument.</span></span>  
  
- <span data-ttu-id="90706-115">**保護**。</span><span class="sxs-lookup"><span data-stu-id="90706-115">**Protection**.</span></span> <span data-ttu-id="90706-116">2つの渡すメカニズムの中で最も重要なのは、変更する変数を呼び出すことによる影響です。</span><span class="sxs-lookup"><span data-stu-id="90706-116">In choosing between the two passing mechanisms, the most important criterion is the exposure of calling variables to change.</span></span> <span data-ttu-id="90706-117">引数 `ByRef` を渡す利点は、プロシージャが引数を使用して呼び出し元のコードに値を返すことができることです。</span><span class="sxs-lookup"><span data-stu-id="90706-117">The advantage of passing an argument `ByRef` is that the procedure can return a value to the calling code through that argument.</span></span> <span data-ttu-id="90706-118">引数 `ByVal` を渡す利点は、プロシージャによって変数が変更されるのを防ぐことです。</span><span class="sxs-lookup"><span data-stu-id="90706-118">The advantage of passing an argument `ByVal` is that it protects a variable from being changed by the procedure.</span></span>  
  
- <span data-ttu-id="90706-119">**パフォーマンス**。</span><span class="sxs-lookup"><span data-stu-id="90706-119">**Performance**.</span></span> <span data-ttu-id="90706-120">渡されるメカニズムは、コードのパフォーマンスに影響を与える可能性がありますが、違いは通常は意味がありません。</span><span class="sxs-lookup"><span data-stu-id="90706-120">Although the passing mechanism can affect the performance of your code, the difference is usually insignificant.</span></span> <span data-ttu-id="90706-121">この例外の1つとして、`ByVal`渡される値の型があります。</span><span class="sxs-lookup"><span data-stu-id="90706-121">One exception to this is a value type passed `ByVal`.</span></span> <span data-ttu-id="90706-122">この場合、Visual Basic は、引数のデータコンテンツ全体をコピーします。</span><span class="sxs-lookup"><span data-stu-id="90706-122">In this case, Visual Basic copies the entire data contents of the argument.</span></span> <span data-ttu-id="90706-123">そのため、構造体などの大きな値の型の場合は、`ByRef`渡す方が効率的です。</span><span class="sxs-lookup"><span data-stu-id="90706-123">Therefore, for a large value type such as a structure, it can be more efficient to pass it `ByRef`.</span></span>  
  
     <span data-ttu-id="90706-124">参照型の場合は、データへのポインターのみがコピーされます (32 ビットプラットフォームでは4バイト、64ビットプラットフォームでは8バイト)。</span><span class="sxs-lookup"><span data-stu-id="90706-124">For reference types, only the pointer to the data is copied (four bytes on 32-bit platforms, eight bytes on 64-bit platforms).</span></span> <span data-ttu-id="90706-125">そのため、型 `String` の引数または `Object` の値によって、パフォーマンスを損なうことなく渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="90706-125">Therefore, you can pass arguments of type `String` or `Object` by value without harming performance.</span></span>  
  
## <a name="determination-of-the-passing-mechanism"></a><span data-ttu-id="90706-126">渡すメカニズムの決定</span><span class="sxs-lookup"><span data-stu-id="90706-126">Determination of the Passing Mechanism</span></span>  
 <span data-ttu-id="90706-127">プロシージャの宣言では、各パラメーターに渡すメカニズムを指定します。</span><span class="sxs-lookup"><span data-stu-id="90706-127">The procedure declaration specifies the passing mechanism for each parameter.</span></span> <span data-ttu-id="90706-128">呼び出し元のコードでは、`ByVal` メカニズムをオーバーライドすることはできません。</span><span class="sxs-lookup"><span data-stu-id="90706-128">The calling code can't override a `ByVal` mechanism.</span></span>  
  
 <span data-ttu-id="90706-129">パラメーターが `ByRef`で宣言されている場合、呼び出し元のコードでは、呼び出しで引数名をかっこで囲むことによって、機構を強制的に `ByVal` することができます。</span><span class="sxs-lookup"><span data-stu-id="90706-129">If a parameter is declared with `ByRef`, the calling code can force the mechanism to `ByVal` by enclosing the argument name in parentheses in the call.</span></span> <span data-ttu-id="90706-130">詳細については、「[方法: 引数を強制的に値で渡す](./how-to-force-an-argument-to-be-passed-by-value.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="90706-130">For more information, see [How to: Force an Argument to Be Passed by Value](./how-to-force-an-argument-to-be-passed-by-value.md).</span></span>  
  
 <span data-ttu-id="90706-131">Visual Basic の既定では、値渡しで引数を渡します。</span><span class="sxs-lookup"><span data-stu-id="90706-131">The default in Visual Basic is to pass arguments by value.</span></span>  
  
## <a name="when-to-pass-an-argument-by-value"></a><span data-ttu-id="90706-132">値渡しで引数を渡す場合</span><span class="sxs-lookup"><span data-stu-id="90706-132">When to Pass an Argument by Value</span></span>  
  
- <span data-ttu-id="90706-133">引数の基になる呼び出し元のコード要素が、不変の要素である場合は、対応するパラメーター [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)を宣言します。</span><span class="sxs-lookup"><span data-stu-id="90706-133">If the calling code element underlying the argument is a nonmodifiable element, declare the corresponding parameter [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).</span></span> <span data-ttu-id="90706-134">変更できない要素の値を変更できるコードはありません。</span><span class="sxs-lookup"><span data-stu-id="90706-134">No code can change the value of a nonmodifiable element.</span></span>  
  
- <span data-ttu-id="90706-135">基になる要素が変更可能であるが、プロシージャがその値を変更できないようにするには、パラメーター `ByVal`を宣言します。</span><span class="sxs-lookup"><span data-stu-id="90706-135">If the underlying element is modifiable, but you do not want the procedure to be able to change its value, declare the parameter `ByVal`.</span></span> <span data-ttu-id="90706-136">値渡しで渡される変更可能な要素の値を変更できるのは、呼び出し元のコードだけです。</span><span class="sxs-lookup"><span data-stu-id="90706-136">Only the calling code can change the value of a modifiable element passed by value.</span></span>  
  
## <a name="when-to-pass-an-argument-by-reference"></a><span data-ttu-id="90706-137">参照渡しで引数を渡す場合</span><span class="sxs-lookup"><span data-stu-id="90706-137">When to Pass an Argument by Reference</span></span>  
  
- <span data-ttu-id="90706-138">プロシージャが、呼び出し元のコード内の基になる要素を変更する必要がある場合は、対応するパラメーター [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)を宣言します。</span><span class="sxs-lookup"><span data-stu-id="90706-138">If the procedure has a genuine need to change the underlying element in the calling code, declare the corresponding parameter [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md).</span></span>  
  
- <span data-ttu-id="90706-139">コードの正しい実行が、呼び出し元のコードの基になる要素を変更するプロシージャに依存している場合は、パラメーター `ByRef`を宣言します。</span><span class="sxs-lookup"><span data-stu-id="90706-139">If the correct execution of the code depends on the procedure changing the underlying element in the calling code, declare the parameter `ByRef`.</span></span> <span data-ttu-id="90706-140">値渡しで渡す場合、または呼び出し元のコードが引数をかっこで囲むことによって `ByRef` 渡す機構をオーバーライドする場合は、プロシージャ呼び出しによって予期しない結果が生じる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="90706-140">If you pass it by value, or if the calling code overrides the `ByRef` passing mechanism by enclosing the argument in parentheses, the procedure call might produce unexpected results.</span></span>  
  
## <a name="example"></a><span data-ttu-id="90706-141">例</span><span class="sxs-lookup"><span data-stu-id="90706-141">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="90706-142">説明</span><span class="sxs-lookup"><span data-stu-id="90706-142">Description</span></span>  
 <span data-ttu-id="90706-143">次の例は、値渡しで引数を渡す場合と、参照渡しで渡す場合を示しています。</span><span class="sxs-lookup"><span data-stu-id="90706-143">The following example illustrates when to pass arguments by value and when to pass them by reference.</span></span> <span data-ttu-id="90706-144">プロシージャ `Calculate` には、`ByVal` と `ByRef` パラメーターの両方があります。</span><span class="sxs-lookup"><span data-stu-id="90706-144">Procedure `Calculate` has both a `ByVal` and a `ByRef` parameter.</span></span> <span data-ttu-id="90706-145">利子率、`rate`、および合計金額 `debt`を指定すると、手順のタスクは、`debt`の元の値に利率を適用した結果として得られる `debt` の新しい値を計算することになります。</span><span class="sxs-lookup"><span data-stu-id="90706-145">Given an interest rate, `rate`, and a sum of money, `debt`, the task of the procedure is to calculate a new value for `debt` that is the result of applying the interest rate to the original value of `debt`.</span></span> <span data-ttu-id="90706-146">`debt` は `ByRef` パラメーターであるため、新しい合計は `debt`に対応する呼び出し元のコードの引数の値に反映されます。</span><span class="sxs-lookup"><span data-stu-id="90706-146">Because `debt` is a `ByRef` parameter, the new total is reflected in the value of the argument in the calling code that corresponds to `debt`.</span></span> <span data-ttu-id="90706-147">パラメーター `rate` は、`Calculate` で値を変更してはならないため、`ByVal` パラメーターです。</span><span class="sxs-lookup"><span data-stu-id="90706-147">Parameter `rate` is a `ByVal` parameter because `Calculate` should not change its value.</span></span>  
  
### <a name="code"></a><span data-ttu-id="90706-148">コード</span><span class="sxs-lookup"><span data-stu-id="90706-148">Code</span></span>  
 [!code-vb[VbVbcnProcedures#74](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class2.vb#74)]  
  
## <a name="see-also"></a><span data-ttu-id="90706-149">参照</span><span class="sxs-lookup"><span data-stu-id="90706-149">See also</span></span>

- [<span data-ttu-id="90706-150">手順</span><span class="sxs-lookup"><span data-stu-id="90706-150">Procedures</span></span>](./index.md)
- [<span data-ttu-id="90706-151">プロシージャのパラメーターと引数</span><span class="sxs-lookup"><span data-stu-id="90706-151">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="90706-152">方法: プロシージャに引数を渡す</span><span class="sxs-lookup"><span data-stu-id="90706-152">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="90706-153">方法: プロシージャ引数の値を変更する</span><span class="sxs-lookup"><span data-stu-id="90706-153">How to: Change the Value of a Procedure Argument</span></span>](./how-to-change-the-value-of-a-procedure-argument.md)
- [<span data-ttu-id="90706-154">方法: プロシージャ引数の値が変化しないようにする</span><span class="sxs-lookup"><span data-stu-id="90706-154">How to: Protect a Procedure Argument Against Value Changes</span></span>](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [<span data-ttu-id="90706-155">方法: 引数の値渡しを強制する</span><span class="sxs-lookup"><span data-stu-id="90706-155">How to: Force an Argument to Be Passed by Value</span></span>](./how-to-force-an-argument-to-be-passed-by-value.md)
- [<span data-ttu-id="90706-156">位置と名前による引数渡し</span><span class="sxs-lookup"><span data-stu-id="90706-156">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)
- [<span data-ttu-id="90706-157">値型と参照型</span><span class="sxs-lookup"><span data-stu-id="90706-157">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
