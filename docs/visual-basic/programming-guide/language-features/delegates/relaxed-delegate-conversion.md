---
title: 厳密でないデリゲート変換
ms.date: 07/20/2015
helpviewer_keywords:
- relaxed delegate conversion [Visual Basic]
- delegates [Visual Basic], relaxed conversion
- conversions [Visual Basic], relaxed delegate
ms.assetid: 64f371d0-5416-4f65-b23b-adcbf556e81c
ms.openlocfilehash: ffb242842553382ba26121333c38fc65eaa168a9
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345219"
---
# <a name="relaxed-delegate-conversion-visual-basic"></a><span data-ttu-id="df212-102">厳密でないデリゲート変換 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="df212-102">Relaxed Delegate Conversion (Visual Basic)</span></span>
<span data-ttu-id="df212-103">厳密でないデリゲート変換を使用すると、シグネチャが同一でない場合でも、デリゲートまたはハンドラーにサブルーチンおよび関数を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="df212-103">Relaxed delegate conversion enables you to assign subs and functions to delegates or handlers even when their signatures are not identical.</span></span> <span data-ttu-id="df212-104">したがって、デリゲートへのバインドは、メソッドの呼び出しに対して既に許可されているバインディングと一致します。</span><span class="sxs-lookup"><span data-stu-id="df212-104">Therefore, binding to delegates becomes consistent with the binding already allowed for method invocations.</span></span>  
  
## <a name="parameters-and-return-type"></a><span data-ttu-id="df212-105">パラメーターと戻り値の型</span><span class="sxs-lookup"><span data-stu-id="df212-105">Parameters and Return Type</span></span>  
 <span data-ttu-id="df212-106">厳密なシグネチャ一致の代わりに、`Option Strict` が `On`に設定されている場合は、次の条件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="df212-106">In place of exact signature match, relaxed conversion requires that the following conditions be met when `Option Strict` is set to `On`:</span></span>  
  
- <span data-ttu-id="df212-107">拡大変換は、各デリゲートパラメーターのデータ型から、割り当てられた関数または `Sub`の対応するパラメーターのデータ型に存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="df212-107">A widening conversion must exist from the data type of each delegate parameter to the data type of the corresponding parameter of the assigned function or `Sub`.</span></span> <span data-ttu-id="df212-108">次の例では、デリゲート `Del1` に1つのパラメーター (`Integer`) があります。</span><span class="sxs-lookup"><span data-stu-id="df212-108">In the following example, the delegate `Del1` has one parameter, an `Integer`.</span></span> <span data-ttu-id="df212-109">割り当てられたラムダ式のパラメーター `m` には、`Long` や `Double`などの `Integer`からの拡大変換があるデータ型が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="df212-109">Parameter `m` in the assigned lambda expressions must have a data type for which there is a widening conversion from `Integer`, such as `Long` or `Double`.</span></span>  
  
     [!code-vb[VbVbalrRelaxedDelegates#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#1)]  
  
     [!code-vb[VbVbalrRelaxedDelegates#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#2)]  
  
     <span data-ttu-id="df212-110">縮小変換は、`Option Strict` が `Off`に設定されている場合にのみ許可されます。</span><span class="sxs-lookup"><span data-stu-id="df212-110">Narrowing conversions are permitted only when `Option Strict` is set to `Off`.</span></span>  
  
     [!code-vb[VbVbalrRelaxedDelegates#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module2.vb#8)]  
  
- <span data-ttu-id="df212-111">拡大変換は、割り当てられた関数の戻り値の型からの逆方向に存在するか、デリゲートの戻り値の型に `Sub` 必要があります。</span><span class="sxs-lookup"><span data-stu-id="df212-111">A widening conversion must exist in the opposite direction from the return type of the assigned function or `Sub` to the return type of the delegate.</span></span> <span data-ttu-id="df212-112">次の例では、割り当てられている各ラムダ式の本体は、`del1` の戻り値の型が `Integer`であるため、`Integer` に拡大変換されるデータ型に評価される必要があります。</span><span class="sxs-lookup"><span data-stu-id="df212-112">In the following examples, the body of each assigned lambda expression must evaluate to a data type that widens to `Integer` because the return type of `del1` is `Integer`.</span></span>  
  
     [!code-vb[VbVbalrRelaxedDelegates#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#3)]  
  
 <span data-ttu-id="df212-113">`Option Strict` が `Off`に設定されている場合、拡大制限は両方向に削除されます。</span><span class="sxs-lookup"><span data-stu-id="df212-113">If `Option Strict` is set to `Off`, the widening restriction is removed in both directions.</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module2.vb#4)]  
  
## <a name="omitting-parameter-specifications"></a><span data-ttu-id="df212-114">パラメーターの指定を省略する</span><span class="sxs-lookup"><span data-stu-id="df212-114">Omitting Parameter Specifications</span></span>  
 <span data-ttu-id="df212-115">緩やかなデリゲートでは、割り当てられたメソッドでパラメーターの指定を完全に省略することもできます。</span><span class="sxs-lookup"><span data-stu-id="df212-115">Relaxed delegates also allow you to completely omit parameter specifications in the assigned method:</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#5)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#6)]  
  
 <span data-ttu-id="df212-116">一部のパラメーターを指定したり、他のパラメーターを省略したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="df212-116">Note that you cannot specify some parameters and omit others.</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#15)]  
  
 <span data-ttu-id="df212-117">パラメーターを省略する機能は、複数の複雑なパラメーターが関係するイベントハンドラーを定義するなどの状況で役立ちます。</span><span class="sxs-lookup"><span data-stu-id="df212-117">The ability to omit parameters is helpful in a situation such as defining an event handler, where several complex parameters are involved.</span></span> <span data-ttu-id="df212-118">一部のイベントハンドラーへの引数は使用されません。</span><span class="sxs-lookup"><span data-stu-id="df212-118">The arguments to some event handlers are not used.</span></span> <span data-ttu-id="df212-119">代わりに、ハンドラーは、イベントが登録されているコントロールの状態に直接アクセスし、引数を無視します。</span><span class="sxs-lookup"><span data-stu-id="df212-119">Instead, the handler directly accesses the state of the control on which the event is registered, and ignores the arguments.</span></span> <span data-ttu-id="df212-120">厳密でないデリゲートを使用すると、あいまいさの結果がない場合に、このような宣言の引数を省略できます。</span><span class="sxs-lookup"><span data-stu-id="df212-120">Relaxed delegates allow you to omit the arguments in such declarations when no ambiguities result.</span></span> <span data-ttu-id="df212-121">次の例では、完全に指定されたメソッド `OnClick` を `RelaxedOnClick`として書き直すことができます。</span><span class="sxs-lookup"><span data-stu-id="df212-121">In the following example, the fully specified method `OnClick` can be rewritten as `RelaxedOnClick`.</span></span>  
  
```vb  
Sub OnClick(ByVal sender As Object, ByVal e As EventArgs) Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
  
Sub RelaxedOnClick() Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
```  
  
## <a name="addressof-examples"></a><span data-ttu-id="df212-122">AddressOf の例</span><span class="sxs-lookup"><span data-stu-id="df212-122">AddressOf Examples</span></span>  
 <span data-ttu-id="df212-123">前の例では、ラムダ式を使用して、型の関係を簡単に確認できます。</span><span class="sxs-lookup"><span data-stu-id="df212-123">Lambda expressions are used in the previous examples to make the type relationships easy to see.</span></span> <span data-ttu-id="df212-124">ただし、`AddressOf`、`Handles`、または `AddHandler`を使用するデリゲートの割り当てに対しても、同じリラクゼーションが許可されます。</span><span class="sxs-lookup"><span data-stu-id="df212-124">However, the same relaxations are permitted for delegate assignments that use `AddressOf`, `Handles`, or `AddHandler`.</span></span>  
  
 <span data-ttu-id="df212-125">次の例では、関数 `f1`、`f2`、`f3`、および `f4` をすべて `Del1`に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="df212-125">In the following example, functions `f1`, `f2`, `f3`, and `f4` can all be assigned to `Del1`.</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#1)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#7)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#9)]  
  
 <span data-ttu-id="df212-126">次の例は、`Option Strict` が `Off`に設定されている場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="df212-126">The following example is valid only when `Option Strict` is set to `Off`.</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module2.vb#14)]  
  
## <a name="dropping-function-returns"></a><span data-ttu-id="df212-127">関数の戻り値の削除</span><span class="sxs-lookup"><span data-stu-id="df212-127">Dropping Function Returns</span></span>  
 <span data-ttu-id="df212-128">厳密でないデリゲート変換を使用すると、関数を `Sub` デリゲートに割り当てて、関数の戻り値を効果的に無視できます。</span><span class="sxs-lookup"><span data-stu-id="df212-128">Relaxed delegate conversion enables you to assign a function to a `Sub` delegate, effectively ignoring the return value of the function.</span></span> <span data-ttu-id="df212-129">ただし、`Sub` を関数デリゲートに割り当てることはできません。</span><span class="sxs-lookup"><span data-stu-id="df212-129">However, you cannot assign a `Sub` to a function delegate.</span></span> <span data-ttu-id="df212-130">次の例では、関数 `doubler` のアドレスが `Sub` デリゲート `Del3`に割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="df212-130">In the following example, the address of function `doubler` is assigned to `Sub` delegate `Del3`.</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#10)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="df212-131">参照</span><span class="sxs-lookup"><span data-stu-id="df212-131">See also</span></span>

- [<span data-ttu-id="df212-132">ラムダ式</span><span class="sxs-lookup"><span data-stu-id="df212-132">Lambda Expressions</span></span>](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
- [<span data-ttu-id="df212-133">拡大変換と縮小変換</span><span class="sxs-lookup"><span data-stu-id="df212-133">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="df212-134">デリゲート</span><span class="sxs-lookup"><span data-stu-id="df212-134">Delegates</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- <span data-ttu-id="df212-135">方法 : [Visual Basic でプロシージャを別のプロシージャに渡す](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)</span><span class="sxs-lookup"><span data-stu-id="df212-135">[How to: Pass Procedures to Another Procedure in Visual Basic](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)</span></span>
- [<span data-ttu-id="df212-136">ローカル型の推論</span><span class="sxs-lookup"><span data-stu-id="df212-136">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="df212-137">Option Strict ステートメント</span><span class="sxs-lookup"><span data-stu-id="df212-137">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
