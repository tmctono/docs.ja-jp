---
title: Visual Studio (Visual Basic) で式ツリーのデバッグ
ms.date: 07/20/2015
ms.assetid: 492cc28f-b7a2-4c47-b582-b3c437b8a5d5
ms.openlocfilehash: 7fc97d898c5956b5a569036e6e0fe1174714576d
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2019
ms.locfileid: "65879822"
---
# <a name="debugging-expression-trees-in-visual-studio-visual-basic"></a><span data-ttu-id="926e7-102">Visual Studio (Visual Basic) で式ツリーのデバッグ</span><span class="sxs-lookup"><span data-stu-id="926e7-102">Debugging Expression Trees in Visual Studio (Visual Basic)</span></span>
<span data-ttu-id="926e7-103">アプリケーションをデバッグするときに、式ツリーの構造および内容を分析できます。</span><span class="sxs-lookup"><span data-stu-id="926e7-103">You can analyze the structure and content of expression trees when you debug your applications.</span></span> <span data-ttu-id="926e7-104">式ツリーの構造体の簡単な概要を取得するには、使用することができます、`DebugView`プロパティを説明する特殊な構文を使用して式ツリーを表す[下](#debugview-syntax)します。</span><span class="sxs-lookup"><span data-stu-id="926e7-104">To get a quick overview of the expression tree structure, you can use the `DebugView` property, which represents expression trees using a special syntax described [below](#debugview-syntax).</span></span> <span data-ttu-id="926e7-105">(なお`DebugView`デバッグ モードでのみ使用できます)。</span><span class="sxs-lookup"><span data-stu-id="926e7-105">(Note that `DebugView` is available only in debug mode.)</span></span>  

![Visual Studio デバッガー内で式ツリーの DebugView](media/debugging-expression-trees-in-visual-studio/debugview_vb.png)

<span data-ttu-id="926e7-107">`DebugView`文字列で、使用することができます、[組み込みテキスト ビジュアライザー](https://docs.microsoft.com/visualstudio/debugger/view-strings-visualizer#open-a-string-visualizer)複数の行を選択して表示する**テキスト ビジュアライザー**隣にある虫眼鏡アイコンから、 `DebugView`ラベル。</span><span class="sxs-lookup"><span data-stu-id="926e7-107">Since `DebugView` is a string, you can use the [built-in Text Visualizer](https://docs.microsoft.com/visualstudio/debugger/view-strings-visualizer#open-a-string-visualizer) to view it across multiple lines, by selecting **Text Visualizer** from the magnifying glass icon next to the `DebugView` label.</span></span>

 !['DebugView' の結果に適用されるテキスト ビジュアライザー](media/debugging-expression-trees-in-visual-studio/string_visualizer_vb.png)

<span data-ttu-id="926e7-109">インストールして使用する代わりに、[カスタム ビジュアライザー](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data)式ツリー。</span><span class="sxs-lookup"><span data-stu-id="926e7-109">Alternatively, you can install and use [a custom visualizer](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data) for expression trees:</span></span>

* <span data-ttu-id="926e7-110">[読み取り可能な式](https://github.com/agileobjects/ReadableExpressions)([MIT ライセンス](https://github.com/agileobjects/ReadableExpressions/blob/master/LICENSE.md)で使用可能な[Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=vs-publisher-1232914.ReadableExpressionsVisualizers))、として式ツリーを表示します。C#コード。</span><span class="sxs-lookup"><span data-stu-id="926e7-110">[Readable Expressions](https://github.com/agileobjects/ReadableExpressions) ([MIT license](https://github.com/agileobjects/ReadableExpressions/blob/master/LICENSE.md), available at the [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=vs-publisher-1232914.ReadableExpressionsVisualizers)), renders the expression tree as C# code:</span></span>

  ![読み取り可能な式のビジュアライザー](media/debugging-expression-trees-in-visual-studio/readable_expressions_visualizer.png)

* <span data-ttu-id="926e7-112">[式ツリーのビジュアライザー](https://github.com/zspitz/ExpressionToString#visual-studio-debugger-visualizer-for-expression-trees) ([MIT ライセンス](https://github.com/zspitz/ExpressionToString/blob/master/LICENSE)) を式ツリー、そのプロパティ、および関連するオブジェクトのグラフィカル ビューを提供し、Visual Basic コードを使用して式ツリーを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="926e7-112">[Expression Tree Visualizer](https://github.com/zspitz/ExpressionToString#visual-studio-debugger-visualizer-for-expression-trees) ([MIT license](https://github.com/zspitz/ExpressionToString/blob/master/LICENSE)), provides a graphical view of the expression tree, its properties, and related objects; and can render the expression tree using Visual Basic code:</span></span>

  ![ExpressionToString ビジュアライザー](media/debugging-expression-trees-in-visual-studio/expression_to_string_visualizer_vb.png)

### <a name="to-open-a-visualizer-for-an-expression-tree"></a><span data-ttu-id="926e7-114">式ツリーのビジュアライザーを開くには</span><span class="sxs-lookup"><span data-stu-id="926e7-114">To open a visualizer for an expression tree</span></span>  
  
1. <span data-ttu-id="926e7-115">式ツリーの横に表示される、虫眼鏡アイコンをクリックします**データヒント**、**ウォッチ**ウィンドウで、 **[自動変数]** ウィンドウで、または **[ローカル]。** ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="926e7-115">Click the magnifying glass icon that appears next to the expression tree in **DataTips**, a **Watch** window, the **Autos** window, or the **Locals** window.</span></span>  
  
     <span data-ttu-id="926e7-116">使用可能なビジュアライザーの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="926e7-116">A list of available visualizers is displayed.:</span></span> 

      ![Visual Studio からビジュアライザーを開く](media/debugging-expression-trees-in-visual-studio/expression_tree_visualizers_vb.png)

2. <span data-ttu-id="926e7-118">使用するビジュアライザーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="926e7-118">Click the visualizer you want to use.</span></span>  

## <a name="debugview-syntax"></a><span data-ttu-id="926e7-119">`DebugView` 構文</span><span class="sxs-lookup"><span data-stu-id="926e7-119">`DebugView` syntax</span></span> 

<span data-ttu-id="926e7-120">それぞれの式の型は、以下のセクションで説明するように、ビジュアライザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="926e7-120">Each expression type is displayed in the visualizer as described in the following sections.</span></span>

## <a name="parameterexpressions"></a><span data-ttu-id="926e7-121">ParameterExpressions</span><span class="sxs-lookup"><span data-stu-id="926e7-121">ParameterExpressions</span></span>

<span data-ttu-id="926e7-122"><xref:System.Linq.Expressions.ParameterExpression> 変数名は、先頭に記号 "$" を付けて表示されます。</span><span class="sxs-lookup"><span data-stu-id="926e7-122"><xref:System.Linq.Expressions.ParameterExpression> variable names are displayed with a "$" symbol at the beginning.</span></span>

<span data-ttu-id="926e7-123">パラメーターに名前がない場合、`$var1` や `$var2` など、自動的に生成された名前が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="926e7-123">If a parameter does not have a name, it is assigned an automatically generated name, such as `$var1` or `$var2`.</span></span>

### <a name="examples"></a><span data-ttu-id="926e7-124">使用例</span><span class="sxs-lookup"><span data-stu-id="926e7-124">Examples</span></span>

- `Expression`

    ```vb
    Dim numParam As ParameterExpression =
    Expression.Parameter(GetType(Integer), "num")
    ```

    <span data-ttu-id="926e7-125">`DebugView` プロパティ</span><span class="sxs-lookup"><span data-stu-id="926e7-125">`DebugView` property</span></span>

    `$num`

- `Expression`

    ```vb
    Dim numParam As ParameterExpression =
    Expression.Parameter(GetType(Integer))
    ```

    <span data-ttu-id="926e7-126">`DebugView` プロパティ</span><span class="sxs-lookup"><span data-stu-id="926e7-126">`DebugView` property</span></span>

    `$var1`

## <a name="constantexpressions"></a><span data-ttu-id="926e7-127">ConstantExpressions</span><span class="sxs-lookup"><span data-stu-id="926e7-127">ConstantExpressions</span></span>
 <span data-ttu-id="926e7-128">整数値、文字列、および `null` を表す <xref:System.Linq.Expressions.ConstantExpression> オブジェクトの場合、定数の値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="926e7-128">For <xref:System.Linq.Expressions.ConstantExpression> objects that represent integer values, strings, and `null`, the value of the constant is displayed.</span></span>

### <a name="examples"></a><span data-ttu-id="926e7-129">使用例</span><span class="sxs-lookup"><span data-stu-id="926e7-129">Examples</span></span>

- `Expression`

    ```vb
    Dim num as Integer= 10
    Dim expr As ConstantExpression = Expression.Constant(num)
    ```

    <span data-ttu-id="926e7-130">`DebugView` プロパティ</span><span class="sxs-lookup"><span data-stu-id="926e7-130">`DebugView` property</span></span>

    <span data-ttu-id="926e7-131">10</span><span class="sxs-lookup"><span data-stu-id="926e7-131">10</span></span>

- `Expression`

    ```vb
    Dim num As Double = 10
    Dim expr As ConstantExpression = Expression.Constant(num)
    ```

    <span data-ttu-id="926e7-132">`DebugView` プロパティ</span><span class="sxs-lookup"><span data-stu-id="926e7-132">`DebugView` property</span></span>

    <span data-ttu-id="926e7-133">10D</span><span class="sxs-lookup"><span data-stu-id="926e7-133">10D</span></span>

## <a name="blockexpression"></a><span data-ttu-id="926e7-134">BlockExpression</span><span class="sxs-lookup"><span data-stu-id="926e7-134">BlockExpression</span></span>

<span data-ttu-id="926e7-135"><xref:System.Linq.Expressions.BlockExpression> オブジェクトの型が、ブロック内の最後の式の型と異なる場合、その型が `DebugInfo` プロパティに山かっこ (\< および >) で囲まれて表示されます。</span><span class="sxs-lookup"><span data-stu-id="926e7-135">If the type of a <xref:System.Linq.Expressions.BlockExpression> object differs from the type of the last expression in the block, the type is displayed in the `DebugInfo` property in angle brackets (\< and >).</span></span> <span data-ttu-id="926e7-136">それ以外の場合、<xref:System.Linq.Expressions.BlockExpression> オブジェクトの型は表示されません。</span><span class="sxs-lookup"><span data-stu-id="926e7-136">Otherwise, the type of the <xref:System.Linq.Expressions.BlockExpression> object is not displayed.</span></span>

### <a name="examples"></a><span data-ttu-id="926e7-137">使用例</span><span class="sxs-lookup"><span data-stu-id="926e7-137">Examples</span></span>

- `Expression`

    ```vb
    Dim block As BlockExpression = Expression.Block(Expression.Constant("test"))
    ```

    <span data-ttu-id="926e7-138">`DebugView` プロパティ</span><span class="sxs-lookup"><span data-stu-id="926e7-138">`DebugView` property</span></span>

    `.Block() {`

    `"test"`

    `}`

- `Expression`

    ```vb
    Dim block As BlockExpression =
    Expression.Block(GetType(Object), Expression.Constant("test"))
    ```

    <span data-ttu-id="926e7-139">`DebugView` プロパティ</span><span class="sxs-lookup"><span data-stu-id="926e7-139">`DebugView` property</span></span>

    `.Block<System.Object>() {`

    `"test"`

    `}`

## <a name="lambdaexpression"></a><span data-ttu-id="926e7-140">LambdaExpression</span><span class="sxs-lookup"><span data-stu-id="926e7-140">LambdaExpression</span></span>

<span data-ttu-id="926e7-141"><xref:System.Linq.Expressions.LambdaExpression> オブジェクトは、デリゲート型と共に表示されます。</span><span class="sxs-lookup"><span data-stu-id="926e7-141"><xref:System.Linq.Expressions.LambdaExpression> objects are displayed together with their delegate types.</span></span>

<span data-ttu-id="926e7-142">ラムダ式に名前がない場合、`#Lambda1` や `#Lambda2` など、自動的に生成された名前が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="926e7-142">If a lambda expression does not have a name, it is assigned an automatically generated name, such as `#Lambda1` or `#Lambda2`.</span></span>

### <a name="examples"></a><span data-ttu-id="926e7-143">使用例</span><span class="sxs-lookup"><span data-stu-id="926e7-143">Examples</span></span>

- `Expression`

    ```vb
    Dim lambda As LambdaExpression =
    Expression.Lambda(Of Func(Of Integer))(Expression.Constant(1))
    ```

    <span data-ttu-id="926e7-144">`DebugView` プロパティ</span><span class="sxs-lookup"><span data-stu-id="926e7-144">`DebugView` property</span></span>

    `.Lambda #Lambda1<System.Func'1[System.Int32]>() {`

    `1`

    `}`

- `Expression`

    ```vb
    Dim lambda As LambdaExpression =
    Expression.Lambda(Of Func(Of Integer))(Expression.Constant(1), "SampleLambda", Nothing)
    ```

    <span data-ttu-id="926e7-145">`DebugView` プロパティ</span><span class="sxs-lookup"><span data-stu-id="926e7-145">`DebugView` property</span></span>

    `.Lambda SampleLambda<System.Func'1[System.Int32]>() {`

    `1`

    `}`

## <a name="labelexpression"></a><span data-ttu-id="926e7-146">LabelExpression</span><span class="sxs-lookup"><span data-stu-id="926e7-146">LabelExpression</span></span>

<span data-ttu-id="926e7-147"><xref:System.Linq.Expressions.LabelExpression> オブジェクトの既定値を指定した場合、その値が <xref:System.Linq.Expressions.LabelTarget> オブジェクトの前に表示されます。</span><span class="sxs-lookup"><span data-stu-id="926e7-147">If you specify a default value for the <xref:System.Linq.Expressions.LabelExpression> object, this value is displayed before the <xref:System.Linq.Expressions.LabelTarget> object.</span></span>

<span data-ttu-id="926e7-148">`.Label` トークンは、ラベルの開始を示します。</span><span class="sxs-lookup"><span data-stu-id="926e7-148">The `.Label` token indicates the start of the label.</span></span> <span data-ttu-id="926e7-149">`.LabelTarget` トークンは、ジャンプ先のターゲットを示します。</span><span class="sxs-lookup"><span data-stu-id="926e7-149">The `.LabelTarget` token indicates the destination of the target to jump to.</span></span>

<span data-ttu-id="926e7-150">ラベルに名前がない場合、`#Label1` や `#Label2` など、自動的に生成された名前が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="926e7-150">If a label does not have a name, it is assigned an automatically generated name, such as `#Label1` or `#Label2`.</span></span>

### <a name="examples"></a><span data-ttu-id="926e7-151">使用例</span><span class="sxs-lookup"><span data-stu-id="926e7-151">Examples</span></span>

- `Expression`

    ```vb
    Dim target As LabelTarget = Expression.Label(GetType(Integer), "SampleLabel")
    Dim label1 As BlockExpression = Expression.Block(
    Expression.Goto(target, Expression.Constant(0)),
    Expression.Label(target, Expression.Constant(-1)))
    ```

    <span data-ttu-id="926e7-152">`DebugView` プロパティ</span><span class="sxs-lookup"><span data-stu-id="926e7-152">`DebugView` property</span></span>

    `.Block() {`

    `.Goto SampleLabel { 0 };`

    `.Label`

    `-1`

    `.LabelTarget SampleLabel:`

    `}`

- `Expression`

    ```vb
    Dim target As LabelTarget = Expression.Label()
    Dim block As BlockExpression = Expression.Block(
    Expression.Goto(target), Expression.Label(target))
    ```

    <span data-ttu-id="926e7-153">`DebugView` プロパティ</span><span class="sxs-lookup"><span data-stu-id="926e7-153">`DebugView` property</span></span>

    `.Block() {`

    `.Goto #Label1 { };`

    `.Label`

    `.LabelTarget #Label1:`

    `}`

## <a name="checked-operators"></a><span data-ttu-id="926e7-154">checked 演算子</span><span class="sxs-lookup"><span data-stu-id="926e7-154">Checked Operators</span></span>

<span data-ttu-id="926e7-155">checked 演算子は、演算子の前に "#" 記号が付く形式で表示されます。</span><span class="sxs-lookup"><span data-stu-id="926e7-155">Checked operators are displayed with the "#" symbol in front of the operator.</span></span> <span data-ttu-id="926e7-156">たとえば、checked 加算演算子は `#+` と表示されます。</span><span class="sxs-lookup"><span data-stu-id="926e7-156">For example, the checked addition operator is displayed as `#+`.</span></span>

### <a name="examples"></a><span data-ttu-id="926e7-157">使用例</span><span class="sxs-lookup"><span data-stu-id="926e7-157">Examples</span></span>

- `Expression`

    ```vb
    Dim expr As Expression = Expression.AddChecked(
    Expression.Constant(1), Expression.Constant(2))
    ```

    <span data-ttu-id="926e7-158">`DebugView` プロパティ</span><span class="sxs-lookup"><span data-stu-id="926e7-158">`DebugView` property</span></span>

    `1 #+ 2`

- `Expression`

    ```vb
    Dim expr As Expression = Expression.ConvertChecked(
    Expression.Constant(10.0), GetType(Integer))
    ```

    <span data-ttu-id="926e7-159">`DebugView` プロパティ</span><span class="sxs-lookup"><span data-stu-id="926e7-159">`DebugView` property</span></span>

    `#(System.Int32)10D`

## <a name="see-also"></a><span data-ttu-id="926e7-160">関連項目</span><span class="sxs-lookup"><span data-stu-id="926e7-160">See also</span></span>

- [<span data-ttu-id="926e7-161">式ツリー (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="926e7-161">Expression Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md)
- [<span data-ttu-id="926e7-162">Visual Studio でのデバッグ</span><span class="sxs-lookup"><span data-stu-id="926e7-162">Debugging in Visual Studio</span></span>](/visualstudio/debugger/debugging-in-visual-studio)
- [<span data-ttu-id="926e7-163">カスタム ビジュアライザーを作成する</span><span class="sxs-lookup"><span data-stu-id="926e7-163">Create Custom Visualizers</span></span>](/visualstudio/debugger/create-custom-visualizers-of-data)
