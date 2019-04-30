---
title: 厳密でないデリゲート変換 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- relaxed delegate conversion [Visual Basic]
- delegates [Visual Basic], relaxed conversion
- conversions [Visual Basic], relaxed delegate
ms.assetid: 64f371d0-5416-4f65-b23b-adcbf556e81c
ms.openlocfilehash: 57e863d9781721a997ae49e1a5c9d8f3562a1bd0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61973286"
---
# <a name="relaxed-delegate-conversion-visual-basic"></a><span data-ttu-id="ce8dd-102">厳密でないデリゲート変換 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ce8dd-102">Relaxed Delegate Conversion (Visual Basic)</span></span>
<span data-ttu-id="ce8dd-103">厳密でないデリゲート変換を使用すると、そのシグネチャが同一でない場合でも sub や関数をデリゲートやハンドラーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="ce8dd-103">Relaxed delegate conversion enables you to assign subs and functions to delegates or handlers even when their signatures are not identical.</span></span> <span data-ttu-id="ce8dd-104">そのため、デリゲートへのバインドは既にメソッドの呼び出しは許可されているバインディングで一貫性のあるになります。</span><span class="sxs-lookup"><span data-stu-id="ce8dd-104">Therefore, binding to delegates becomes consistent with the binding already allowed for method invocations.</span></span>  
  
## <a name="parameters-and-return-type"></a><span data-ttu-id="ce8dd-105">パラメーターと戻り値の型</span><span class="sxs-lookup"><span data-stu-id="ce8dd-105">Parameters and Return Type</span></span>  
 <span data-ttu-id="ce8dd-106">正確なシグネチャの一致の代わりに厳密でない変換が必要です、次の条件が満たされているときに`Option Strict`に設定されている`On`:</span><span class="sxs-lookup"><span data-stu-id="ce8dd-106">In place of exact signature match, relaxed conversion requires that the following conditions be met when `Option Strict` is set to `On`:</span></span>  
  
- <span data-ttu-id="ce8dd-107">各デリゲート パラメーターのデータ型から割り当てられている関数の対応するパラメーターのデータ型への拡大変換が存在する必要がありますまたは`Sub`します。</span><span class="sxs-lookup"><span data-stu-id="ce8dd-107">A widening conversion must exist from the data type of each delegate parameter to the data type of the corresponding parameter of the assigned function or `Sub`.</span></span> <span data-ttu-id="ce8dd-108">次の例では、デリゲート`Del1`1 つのパラメーター、`Integer`します。</span><span class="sxs-lookup"><span data-stu-id="ce8dd-108">In the following example, the delegate `Del1` has one parameter, an `Integer`.</span></span> <span data-ttu-id="ce8dd-109">パラメーター`m`式で割り当てられたラムダから拡大変換がある対象のデータ型である必要があります`Integer`など`Long`または`Double`します。</span><span class="sxs-lookup"><span data-stu-id="ce8dd-109">Parameter `m` in the assigned lambda expressions must have a data type for which there is a widening conversion from `Integer`, such as `Long` or `Double`.</span></span>  
  
     [!code-vb[VbVbalrRelaxedDelegates#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#1)]  
  
     [!code-vb[VbVbalrRelaxedDelegates#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#2)]  
  
     <span data-ttu-id="ce8dd-110">縮小変換が許可される場合にのみ`Option Strict`に設定されている`Off`します。</span><span class="sxs-lookup"><span data-stu-id="ce8dd-110">Narrowing conversions are permitted only when `Option Strict` is set to `Off`.</span></span>  
  
     [!code-vb[VbVbalrRelaxedDelegates#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module2.vb#8)]  
  
- <span data-ttu-id="ce8dd-111">割り当て済みの関数の戻り値の型から反対方向に拡大変換が存在する必要がありますまたは`Sub`デリゲートの戻り値の型にします。</span><span class="sxs-lookup"><span data-stu-id="ce8dd-111">A widening conversion must exist in the opposite direction from the return type of the assigned function or `Sub` to the return type of the delegate.</span></span> <span data-ttu-id="ce8dd-112">次の例については、各割り当てられているラムダ式の本体に拡大変換をデータ型に評価する必要があります`Integer`戻り値の型のため、`del1`は`Integer`します。</span><span class="sxs-lookup"><span data-stu-id="ce8dd-112">In the following examples, the body of each assigned lambda expression must evaluate to a data type that widens to `Integer` because the return type of `del1` is `Integer`.</span></span>  
  
     [!code-vb[VbVbalrRelaxedDelegates#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#3)]  
  
 <span data-ttu-id="ce8dd-113">場合`Option Strict`に設定されている`Off`制限の拡大が双方向で削除します。</span><span class="sxs-lookup"><span data-stu-id="ce8dd-113">If `Option Strict` is set to `Off`, the widening restriction is removed in both directions.</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module2.vb#4)]  
  
## <a name="omitting-parameter-specifications"></a><span data-ttu-id="ce8dd-114">パラメーターの指定を省略します。</span><span class="sxs-lookup"><span data-stu-id="ce8dd-114">Omitting Parameter Specifications</span></span>  
 <span data-ttu-id="ce8dd-115">厳密でないデリゲートでは、割り当てられているメソッドのパラメーターの仕様を完全に省略することもできます。</span><span class="sxs-lookup"><span data-stu-id="ce8dd-115">Relaxed delegates also allow you to completely omit parameter specifications in the assigned method:</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#5)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#6)]  
  
 <span data-ttu-id="ce8dd-116">いくつかのパラメーターを指定して他のユーザーを省略できませんに注意してください。</span><span class="sxs-lookup"><span data-stu-id="ce8dd-116">Note that you cannot specify some parameters and omit others.</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#15)]  
  
 <span data-ttu-id="ce8dd-117">パラメーターを省略する機能は、いくつかの複雑なパラメーターが含まれて、イベント ハンドラーを定義するような状況で役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ce8dd-117">The ability to omit parameters is helpful in a situation such as defining an event handler, where several complex parameters are involved.</span></span> <span data-ttu-id="ce8dd-118">いくつかのイベント ハンドラーの引数は使用されません。</span><span class="sxs-lookup"><span data-stu-id="ce8dd-118">The arguments to some event handlers are not used.</span></span> <span data-ttu-id="ce8dd-119">代わりに、ハンドラーによって、コントロールをイベントが登録されているし、引数を無視の状態が直接アクセスします。</span><span class="sxs-lookup"><span data-stu-id="ce8dd-119">Instead, the handler directly accesses the state of the control on which the event is registered, and ignores the arguments.</span></span> <span data-ttu-id="ce8dd-120">厳密でないデリゲートを使用すると、ときにあいまいさの結果はありません、このような宣言の引数を省略できます。</span><span class="sxs-lookup"><span data-stu-id="ce8dd-120">Relaxed delegates allow you to omit the arguments in such declarations when no ambiguities result.</span></span> <span data-ttu-id="ce8dd-121">次の例では、完全に指定されたメソッドで`OnClick`として書き直す`RelaxedOnClick`します。</span><span class="sxs-lookup"><span data-stu-id="ce8dd-121">In the following example, the fully specified method `OnClick` can be rewritten as `RelaxedOnClick`.</span></span>  
  
```vb  
Sub OnClick(ByVal sender As Object, ByVal e As EventArgs) Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
  
Sub RelaxedOnClick() Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
```  
  
## <a name="addressof-examples"></a><span data-ttu-id="ce8dd-122">AddressOf 例</span><span class="sxs-lookup"><span data-stu-id="ce8dd-122">AddressOf Examples</span></span>  
 <span data-ttu-id="ce8dd-123">ラムダ式は、型の関係を簡単に参照してください、前の例で使用されます。</span><span class="sxs-lookup"><span data-stu-id="ce8dd-123">Lambda expressions are used in the previous examples to make the type relationships easy to see.</span></span> <span data-ttu-id="ce8dd-124">ただし、同じリラクゼーションを使用するデリゲートの割り当ての許可`AddressOf`、 `Handles`、または`AddHandler`します。</span><span class="sxs-lookup"><span data-stu-id="ce8dd-124">However, the same relaxations are permitted for delegate assignments that use `AddressOf`, `Handles`, or `AddHandler`.</span></span>  
  
 <span data-ttu-id="ce8dd-125">次の例では、機能`f1`、 `f2`、 `f3`、および`f4`すべてに代入できる`Del1`します。</span><span class="sxs-lookup"><span data-stu-id="ce8dd-125">In the following example, functions `f1`, `f2`, `f3`, and `f4` can all be assigned to `Del1`.</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#1)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#7)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#9)]  
  
 <span data-ttu-id="ce8dd-126">次の例は有効な場合にのみ`Option Strict`に設定されている`Off`します。</span><span class="sxs-lookup"><span data-stu-id="ce8dd-126">The following example is valid only when `Option Strict` is set to `Off`.</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module2.vb#14)]  
  
## <a name="dropping-function-returns"></a><span data-ttu-id="ce8dd-127">関数の戻り値を削除します。</span><span class="sxs-lookup"><span data-stu-id="ce8dd-127">Dropping Function Returns</span></span>  
 <span data-ttu-id="ce8dd-128">厳密でないデリゲート変換は、機能を割り当てることができます、`Sub`デリゲート、事実上、関数の戻り値を無視します。</span><span class="sxs-lookup"><span data-stu-id="ce8dd-128">Relaxed delegate conversion enables you to assign a function to a `Sub` delegate, effectively ignoring the return value of the function.</span></span> <span data-ttu-id="ce8dd-129">ただし、割り当てることはできません、`Sub`を関数デリゲート。</span><span class="sxs-lookup"><span data-stu-id="ce8dd-129">However, you cannot assign a `Sub` to a function delegate.</span></span> <span data-ttu-id="ce8dd-130">次の例では、関数のアドレスで`doubler`に割り当てられている`Sub`委任`Del3`します。</span><span class="sxs-lookup"><span data-stu-id="ce8dd-130">In the following example, the address of function `doubler` is assigned to `Sub` delegate `Del3`.</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#10)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="ce8dd-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="ce8dd-131">See also</span></span>

- [<span data-ttu-id="ce8dd-132">ラムダ式</span><span class="sxs-lookup"><span data-stu-id="ce8dd-132">Lambda Expressions</span></span>](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
- [<span data-ttu-id="ce8dd-133">拡大変換と縮小変換</span><span class="sxs-lookup"><span data-stu-id="ce8dd-133">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="ce8dd-134">デリゲート</span><span class="sxs-lookup"><span data-stu-id="ce8dd-134">Delegates</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="ce8dd-135">方法: Visual Basic での別のプロシージャに渡す</span><span class="sxs-lookup"><span data-stu-id="ce8dd-135">How to: Pass Procedures to Another Procedure in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)
- [<span data-ttu-id="ce8dd-136">ローカル型の推論</span><span class="sxs-lookup"><span data-stu-id="ce8dd-136">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="ce8dd-137">Option Strict ステートメント</span><span class="sxs-lookup"><span data-stu-id="ce8dd-137">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
