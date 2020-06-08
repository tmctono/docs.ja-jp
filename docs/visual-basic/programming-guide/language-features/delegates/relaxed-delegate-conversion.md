---
title: 厳密でないデリゲート変換
ms.date: 07/20/2015
helpviewer_keywords:
- relaxed delegate conversion [Visual Basic]
- delegates [Visual Basic], relaxed conversion
- conversions [Visual Basic], relaxed delegate
ms.assetid: 64f371d0-5416-4f65-b23b-adcbf556e81c
ms.openlocfilehash: a581ffae77c496908d2e4e38df53491a54ae2ab8
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410671"
---
# <a name="relaxed-delegate-conversion-visual-basic"></a><span data-ttu-id="0b36e-102">厳密でないデリゲート変換 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0b36e-102">Relaxed Delegate Conversion (Visual Basic)</span></span>
<span data-ttu-id="0b36e-103">厳密でないデリゲート変換を使用すると、シグネチャが同じでない場合でも、Sub プロシージャや関数をデリゲートまたはハンドラーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="0b36e-103">Relaxed delegate conversion enables you to assign subs and functions to delegates or handlers even when their signatures are not identical.</span></span> <span data-ttu-id="0b36e-104">したがって、デリゲートへのバインドは、メソッドの呼び出しに対して既に許可されているバインドと整合します。</span><span class="sxs-lookup"><span data-stu-id="0b36e-104">Therefore, binding to delegates becomes consistent with the binding already allowed for method invocations.</span></span>  
  
## <a name="parameters-and-return-type"></a><span data-ttu-id="0b36e-105">パラメーターと戻り値の型</span><span class="sxs-lookup"><span data-stu-id="0b36e-105">Parameters and Return Type</span></span>  
 <span data-ttu-id="0b36e-106">厳密なシグネチャ一致の代わりに、厳密でない変換では、`Option Strict` が `On` に設定されている場合は次の条件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b36e-106">In place of exact signature match, relaxed conversion requires that the following conditions be met when `Option Strict` is set to `On`:</span></span>  
  
- <span data-ttu-id="0b36e-107">各デリゲート パラメーターのデータ型から、割り当てられた関数または `Sub` の対応するパラメーターのデータ型に、拡大変換が存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b36e-107">A widening conversion must exist from the data type of each delegate parameter to the data type of the corresponding parameter of the assigned function or `Sub`.</span></span> <span data-ttu-id="0b36e-108">次の例では、デリゲート `Del1` に 1 つのパラメーター `Integer` があります。</span><span class="sxs-lookup"><span data-stu-id="0b36e-108">In the following example, the delegate `Del1` has one parameter, an `Integer`.</span></span> <span data-ttu-id="0b36e-109">割り当てられたラムダ式のパラメーター `m` には、`Integer` からの拡大変換に対するデータ型、`Long` や `Double` などが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b36e-109">Parameter `m` in the assigned lambda expressions must have a data type for which there is a widening conversion from `Integer`, such as `Long` or `Double`.</span></span>  
  
     [!code-vb[VbVbalrRelaxedDelegates#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#1)]  
  
     [!code-vb[VbVbalrRelaxedDelegates#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#2)]  
  
     <span data-ttu-id="0b36e-110">縮小変換が許可されるのは、`Option Strict` が `Off` に設定されている場合のみです。</span><span class="sxs-lookup"><span data-stu-id="0b36e-110">Narrowing conversions are permitted only when `Option Strict` is set to `Off`.</span></span>  
  
     [!code-vb[VbVbalrRelaxedDelegates#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module2.vb#8)]  
  
- <span data-ttu-id="0b36e-111">割り当てられた関数または `Sub` の戻り値の型から、デリゲートの戻り値の型への逆方向に、拡大変換が存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b36e-111">A widening conversion must exist in the opposite direction from the return type of the assigned function or `Sub` to the return type of the delegate.</span></span> <span data-ttu-id="0b36e-112">次の例では、`del1` の戻り値の型が `Integer` であるため、割り当てられている各ラムダ式の本体は、`Integer` に拡大変換されるデータ型に評価される必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b36e-112">In the following examples, the body of each assigned lambda expression must evaluate to a data type that widens to `Integer` because the return type of `del1` is `Integer`.</span></span>  
  
     [!code-vb[VbVbalrRelaxedDelegates#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#3)]  
  
 <span data-ttu-id="0b36e-113">`Option Strict` が `Off` に設定されている場合、拡大制限は両方向で削除されます。</span><span class="sxs-lookup"><span data-stu-id="0b36e-113">If `Option Strict` is set to `Off`, the widening restriction is removed in both directions.</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module2.vb#4)]  
  
## <a name="omitting-parameter-specifications"></a><span data-ttu-id="0b36e-114">パラメーターの指定値の省略</span><span class="sxs-lookup"><span data-stu-id="0b36e-114">Omitting Parameter Specifications</span></span>  
 <span data-ttu-id="0b36e-115">厳密でないデリゲートを使用すると、割り当てられたメソッドで、パラメーターの指定値を完全に省略することもできます。</span><span class="sxs-lookup"><span data-stu-id="0b36e-115">Relaxed delegates also allow you to completely omit parameter specifications in the assigned method:</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#5)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#6)]  
  
 <span data-ttu-id="0b36e-116">一部のパラメーターを指定する一方で他のパラメーターを省略することはできません。</span><span class="sxs-lookup"><span data-stu-id="0b36e-116">Note that you cannot specify some parameters and omit others.</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#15)]  
  
 <span data-ttu-id="0b36e-117">パラメーターを省略する機能は、イベント ハンドラーを定義する状況などで役立ちます。このような場合、複雑なパラメーターが複数関係しています。</span><span class="sxs-lookup"><span data-stu-id="0b36e-117">The ability to omit parameters is helpful in a situation such as defining an event handler, where several complex parameters are involved.</span></span> <span data-ttu-id="0b36e-118">一部のイベント ハンドラーについては、そのハンドラーに対する引数が使用されません。</span><span class="sxs-lookup"><span data-stu-id="0b36e-118">The arguments to some event handlers are not used.</span></span> <span data-ttu-id="0b36e-119">ハンドラーは、イベントが登録されているコントロールの状態に直接アクセスし、引数を無視します。</span><span class="sxs-lookup"><span data-stu-id="0b36e-119">Instead, the handler directly accesses the state of the control on which the event is registered, and ignores the arguments.</span></span> <span data-ttu-id="0b36e-120">厳密でないデリゲートを使用すると、あいまいな結果がないときに、このような宣言の引数を省略できます。</span><span class="sxs-lookup"><span data-stu-id="0b36e-120">Relaxed delegates allow you to omit the arguments in such declarations when no ambiguities result.</span></span> <span data-ttu-id="0b36e-121">次の例では、完全に指定されたメソッド `OnClick` を `RelaxedOnClick` として書き直すことができます。</span><span class="sxs-lookup"><span data-stu-id="0b36e-121">In the following example, the fully specified method `OnClick` can be rewritten as `RelaxedOnClick`.</span></span>  
  
```vb  
Sub OnClick(ByVal sender As Object, ByVal e As EventArgs) Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
  
Sub RelaxedOnClick() Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
```  
  
## <a name="addressof-examples"></a><span data-ttu-id="0b36e-122">AddressOf の例</span><span class="sxs-lookup"><span data-stu-id="0b36e-122">AddressOf Examples</span></span>  
 <span data-ttu-id="0b36e-123">前の例では、ラムダ式を使用して、型の関係を簡単に確認できます。</span><span class="sxs-lookup"><span data-stu-id="0b36e-123">Lambda expressions are used in the previous examples to make the type relationships easy to see.</span></span> <span data-ttu-id="0b36e-124">ただし、`AddressOf`、`Handles`、または `AddHandler` が使用されているデリゲート割り当てに対して、同じ緩和が許可されています。</span><span class="sxs-lookup"><span data-stu-id="0b36e-124">However, the same relaxations are permitted for delegate assignments that use `AddressOf`, `Handles`, or `AddHandler`.</span></span>  
  
 <span data-ttu-id="0b36e-125">次の例では、関数 `f1`、`f2`、`f3`、`f4` のすべてを `Del1` に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="0b36e-125">In the following example, functions `f1`, `f2`, `f3`, and `f4` can all be assigned to `Del1`.</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#1)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#7)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#9)]  
  
 <span data-ttu-id="0b36e-126">次の例は、`Option Strict` が `Off` に設定されている場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="0b36e-126">The following example is valid only when `Option Strict` is set to `Off`.</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module2.vb#14)]  
  
## <a name="dropping-function-returns"></a><span data-ttu-id="0b36e-127">関数の戻り値の破棄</span><span class="sxs-lookup"><span data-stu-id="0b36e-127">Dropping Function Returns</span></span>  
 <span data-ttu-id="0b36e-128">厳密でないデリゲート変換を使用すると、関数を `Sub` デリゲートに割り当てて、関数の戻り値を効果的に無視できます。</span><span class="sxs-lookup"><span data-stu-id="0b36e-128">Relaxed delegate conversion enables you to assign a function to a `Sub` delegate, effectively ignoring the return value of the function.</span></span> <span data-ttu-id="0b36e-129">ただし、`Sub` を関数デリゲートに割り当てることはできません。</span><span class="sxs-lookup"><span data-stu-id="0b36e-129">However, you cannot assign a `Sub` to a function delegate.</span></span> <span data-ttu-id="0b36e-130">次の例では、関数 `doubler` のアドレスが `Sub` デリゲート `Del3` に割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="0b36e-130">In the following example, the address of function `doubler` is assigned to `Sub` delegate `Del3`.</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#10)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="0b36e-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="0b36e-131">See also</span></span>

- [<span data-ttu-id="0b36e-132">ラムダ式</span><span class="sxs-lookup"><span data-stu-id="0b36e-132">Lambda Expressions</span></span>](../procedures/lambda-expressions.md)
- [<span data-ttu-id="0b36e-133">拡大変換と縮小変換</span><span class="sxs-lookup"><span data-stu-id="0b36e-133">Widening and Narrowing Conversions</span></span>](../data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="0b36e-134">デリゲート</span><span class="sxs-lookup"><span data-stu-id="0b36e-134">Delegates</span></span>](index.md)
- [<span data-ttu-id="0b36e-135">方法: Visual Basic でプロシージャを別のプロシージャに渡す</span><span class="sxs-lookup"><span data-stu-id="0b36e-135">How to: Pass Procedures to Another Procedure in Visual Basic</span></span>](how-to-pass-procedures-to-another-procedure.md)
- [<span data-ttu-id="0b36e-136">ローカル型の推論</span><span class="sxs-lookup"><span data-stu-id="0b36e-136">Local Type Inference</span></span>](../variables/local-type-inference.md)
- [<span data-ttu-id="0b36e-137">Option Strict ステートメント</span><span class="sxs-lookup"><span data-stu-id="0b36e-137">Option Strict Statement</span></span>](../../../language-reference/statements/option-strict-statement.md)
