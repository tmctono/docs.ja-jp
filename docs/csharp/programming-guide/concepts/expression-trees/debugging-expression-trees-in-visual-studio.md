---
title: 式ツリーのデバッグ (Visual Studio) (C#)
ms.date: 07/20/2015
ms.assetid: 1369fa25-0fbd-4b92-98d0-8df79c49c27a
ms.openlocfilehash: 4017e2c2592dc1d6067b428fc1d47f37775abf85
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2019
ms.locfileid: "65877148"
---
# <a name="debugging-expression-trees-in-visual-studio-c"></a><span data-ttu-id="b221a-102">式ツリーのデバッグ (Visual Studio) (C#)</span><span class="sxs-lookup"><span data-stu-id="b221a-102">Debugging Expression Trees in Visual Studio (C#)</span></span>
<span data-ttu-id="b221a-103">アプリケーションをデバッグするときに、式ツリーの構造および内容を分析できます。</span><span class="sxs-lookup"><span data-stu-id="b221a-103">You can analyze the structure and content of expression trees when you debug your applications.</span></span> <span data-ttu-id="b221a-104">式ツリーの構造の概要を簡単に取得するには、`DebugView` プロパティ使用できます。このプロパティでは、[後で説明](#debugview-syntax)する特殊な構文を使って式ツリーが表されます。</span><span class="sxs-lookup"><span data-stu-id="b221a-104">To get a quick overview of the expression tree structure, you can use the `DebugView` property, which represents expression trees using a special syntax described [below](#debugview-syntax).</span></span> <span data-ttu-id="b221a-105">(`DebugView` はデバッグ モードでのみ使用できることに注意してください。)</span><span class="sxs-lookup"><span data-stu-id="b221a-105">(Note that `DebugView` is available only in debug mode.)</span></span>  

![Visual Studio デバッガー内での式ツリーの DebugView](media/debugging-expression-trees-in-visual-studio/debugview.png)

<span data-ttu-id="b221a-107">`DebugView` は文字列なので、[組み込まれているテキスト ビジュアライザー](https://docs.microsoft.com/visualstudio/debugger/view-strings-visualizer#open-a-string-visualizer)を使って、複数行で表示できます。**テキスト ビジュアライザー**を使うには、`DebugView` ラベルの隣にある虫眼鏡アイコンから選択します。</span><span class="sxs-lookup"><span data-stu-id="b221a-107">Since `DebugView` is a string, you can use the [built-in Text Visualizer](https://docs.microsoft.com/visualstudio/debugger/view-strings-visualizer#open-a-string-visualizer) to view it across multiple lines, by selecting **Text Visualizer** from the magnifying glass icon next to the `DebugView` label.</span></span>

 !["DebugView" の結果に適用されたテキスト ビジュアライザー](media/debugging-expression-trees-in-visual-studio/string_visualizer.png)

<span data-ttu-id="b221a-109">または、式ツリー用の[カスタム ビジュアライザー](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data)をインストールして使うこともできます。</span><span class="sxs-lookup"><span data-stu-id="b221a-109">Alternatively, you can install and use [a custom visualizer](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data) for expression trees:</span></span>

* <span data-ttu-id="b221a-110">[ReadableExpressions](https://github.com/agileobjects/ReadableExpressions) ([MIT ライセンス](https://github.com/agileobjects/ReadableExpressions/blob/master/LICENSE.md)、[Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=vs-publisher-1232914.ReadableExpressionsVisualizers) で使用可能): 式ツリーが C# コードとしてレンダリングされます。</span><span class="sxs-lookup"><span data-stu-id="b221a-110">[Readable Expressions](https://github.com/agileobjects/ReadableExpressions) ([MIT license](https://github.com/agileobjects/ReadableExpressions/blob/master/LICENSE.md), available at the [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=vs-publisher-1232914.ReadableExpressionsVisualizers)), renders the expression tree as C# code:</span></span>

  ![ReadableExpressions ビジュアライザー](media/debugging-expression-trees-in-visual-studio/readable_expressions_visualizer.png)

* <span data-ttu-id="b221a-112">[Expression Tree Visualizer](https://github.com/zspitz/ExpressionToString#visual-studio-debugger-visualizer-for-expression-trees) ([MIT ライセンス](https://github.com/zspitz/ExpressionToString/blob/master/LICENSE)): 式ツリー、そのプロパティ、関連オブジェクトのグラフィカル ビューが提供されます。</span><span class="sxs-lookup"><span data-stu-id="b221a-112">[Expression Tree Visualizer](https://github.com/zspitz/ExpressionToString#visual-studio-debugger-visualizer-for-expression-trees) ([MIT license](https://github.com/zspitz/ExpressionToString/blob/master/LICENSE)), provides a graphical view of the expression tree, its properties, and related objects:</span></span>

  ![ExpressionToString ビジュアライザー](media/debugging-expression-trees-in-visual-studio/expression_to_string_visualizer.png)

### <a name="to-open-a-visualizer-for-an-expression-tree"></a><span data-ttu-id="b221a-114">式ツリーのビジュアライザーを開くには</span><span class="sxs-lookup"><span data-stu-id="b221a-114">To open a visualizer for an expression tree</span></span>  
  
1. <span data-ttu-id="b221a-115">**[データヒント]**、**[ウォッチ]** ウィンドウ、**[自動変数]** ウィンドウ、または **[ローカル]** ウィンドウで、式ツリーの横に表示されている虫眼鏡のアイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="b221a-115">Click the magnifying glass icon that appears next to the expression tree in **DataTips**, a **Watch** window, the **Autos** window, or the **Locals** window.</span></span>  
  
     <span data-ttu-id="b221a-116">使用可能なビジュアライザーの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b221a-116">A list of available visualizers is displayed.:</span></span> 

      ![Visual Studio からビジュアライザーを開く](media/debugging-expression-trees-in-visual-studio/expression_tree_visualizers.png)

2. <span data-ttu-id="b221a-118">使用するビジュアライザーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="b221a-118">Click the visualizer you want to use.</span></span>  

## <a name="debugview-syntax"></a><span data-ttu-id="b221a-119">`DebugView` の構文</span><span class="sxs-lookup"><span data-stu-id="b221a-119">`DebugView` syntax</span></span> 

<span data-ttu-id="b221a-120">それぞれの式の型は、以下のセクションで説明するように、`DebugView` プロパティによって表示されます。</span><span class="sxs-lookup"><span data-stu-id="b221a-120">Each expression type is displayed by the `DebugView` property as described in the following sections.</span></span>  
  
## <a name="parameterexpressions"></a><span data-ttu-id="b221a-121">ParameterExpressions</span><span class="sxs-lookup"><span data-stu-id="b221a-121">ParameterExpressions</span></span>  
 <span data-ttu-id="b221a-122"><xref:System.Linq.Expressions.ParameterExpression> 変数名は、先頭に記号 "$" を付けて表示されます。</span><span class="sxs-lookup"><span data-stu-id="b221a-122"><xref:System.Linq.Expressions.ParameterExpression> variable names are displayed with a "$" symbol at the beginning.</span></span>  
  
 <span data-ttu-id="b221a-123">パラメーターに名前がない場合、`$var1` や `$var2` など、自動的に生成された名前が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="b221a-123">If a parameter does not have a name, it is assigned an automatically generated name, such as `$var1` or `$var2`.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="b221a-124">使用例</span><span class="sxs-lookup"><span data-stu-id="b221a-124">Examples</span></span>  
  
|<span data-ttu-id="b221a-125">正規表現</span><span class="sxs-lookup"><span data-stu-id="b221a-125">Expression</span></span>|<span data-ttu-id="b221a-126">`DebugView` プロパティ</span><span class="sxs-lookup"><span data-stu-id="b221a-126">`DebugView` property</span></span>|  
|----------------|--------------------------|  
|`ParameterExpression numParam =  Expression.Parameter(typeof(int), "num");`|`$num`|  
|`ParameterExpression numParam =  Expression.Parameter(typeof(int));`|`$var1`|  
  
## <a name="constantexpressions"></a><span data-ttu-id="b221a-127">ConstantExpressions</span><span class="sxs-lookup"><span data-stu-id="b221a-127">ConstantExpressions</span></span>  
 <span data-ttu-id="b221a-128">整数値、文字列、および `null` を表す <xref:System.Linq.Expressions.ConstantExpression> オブジェクトの場合、定数の値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b221a-128">For <xref:System.Linq.Expressions.ConstantExpression> objects that represent integer values, strings, and `null`, the value of the constant is displayed.</span></span>  
  
 <span data-ttu-id="b221a-129">C# リテラルとしての標準のサフィックスを持つ数値型の場合、サフィックスが値に追加されます。</span><span class="sxs-lookup"><span data-stu-id="b221a-129">For numeric types that have standard suffixes as C# literals, the suffix is added to the value.</span></span> <span data-ttu-id="b221a-130">さまざまな数値型に関連するサフィックスを次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="b221a-130">The following table shows the suffixes associated with various numeric types.</span></span>  
  
|<span data-ttu-id="b221a-131">型</span><span class="sxs-lookup"><span data-stu-id="b221a-131">Type</span></span>|<span data-ttu-id="b221a-132">サフィックス</span><span class="sxs-lookup"><span data-stu-id="b221a-132">Suffix</span></span>|  
|----------|------------|  
|<xref:System.UInt32>|<span data-ttu-id="b221a-133">U</span><span class="sxs-lookup"><span data-stu-id="b221a-133">U</span></span>|  
|<xref:System.Int64>|<span data-ttu-id="b221a-134">L</span><span class="sxs-lookup"><span data-stu-id="b221a-134">L</span></span>|  
|<xref:System.UInt64>|<span data-ttu-id="b221a-135">UL</span><span class="sxs-lookup"><span data-stu-id="b221a-135">UL</span></span>|  
|<xref:System.Double>|<span data-ttu-id="b221a-136">D</span><span class="sxs-lookup"><span data-stu-id="b221a-136">D</span></span>|  
|<xref:System.Single>|<span data-ttu-id="b221a-137">F</span><span class="sxs-lookup"><span data-stu-id="b221a-137">F</span></span>|  
|<xref:System.Decimal>|<span data-ttu-id="b221a-138">M</span><span class="sxs-lookup"><span data-stu-id="b221a-138">M</span></span>|  
  
### <a name="examples"></a><span data-ttu-id="b221a-139">使用例</span><span class="sxs-lookup"><span data-stu-id="b221a-139">Examples</span></span>  
  
|<span data-ttu-id="b221a-140">正規表現</span><span class="sxs-lookup"><span data-stu-id="b221a-140">Expression</span></span>|<span data-ttu-id="b221a-141">`DebugView` プロパティ</span><span class="sxs-lookup"><span data-stu-id="b221a-141">`DebugView` property</span></span>|  
|----------------|--------------------------|  
|`int num = 10; ConstantExpression expr = Expression.Constant(num);`|<span data-ttu-id="b221a-142">10</span><span class="sxs-lookup"><span data-stu-id="b221a-142">10</span></span>|  
|`double num = 10; ConstantExpression expr = Expression.Constant(num);`|<span data-ttu-id="b221a-143">10D</span><span class="sxs-lookup"><span data-stu-id="b221a-143">10D</span></span>|  
  
## <a name="blockexpression"></a><span data-ttu-id="b221a-144">BlockExpression</span><span class="sxs-lookup"><span data-stu-id="b221a-144">BlockExpression</span></span>  
 <span data-ttu-id="b221a-145"><xref:System.Linq.Expressions.BlockExpression> オブジェクトの型が、ブロック内の最後の式の型と異なる場合、その型が `DebugInfo` プロパティに山かっこ (\< および >) で囲まれて表示されます。</span><span class="sxs-lookup"><span data-stu-id="b221a-145">If the type of a <xref:System.Linq.Expressions.BlockExpression> object differs from the type of the last expression in the block, the type is displayed in the `DebugInfo` property in angle brackets (\< and >).</span></span> <span data-ttu-id="b221a-146">それ以外の場合、<xref:System.Linq.Expressions.BlockExpression> オブジェクトの型は表示されません。</span><span class="sxs-lookup"><span data-stu-id="b221a-146">Otherwise, the type of the <xref:System.Linq.Expressions.BlockExpression> object is not displayed.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="b221a-147">使用例</span><span class="sxs-lookup"><span data-stu-id="b221a-147">Examples</span></span>  
  
|<span data-ttu-id="b221a-148">正規表現</span><span class="sxs-lookup"><span data-stu-id="b221a-148">Expression</span></span>|<span data-ttu-id="b221a-149">`DebugView` プロパティ</span><span class="sxs-lookup"><span data-stu-id="b221a-149">`DebugView` property</span></span>|  
|----------------|--------------------------|  
|`BlockExpression block = Expression.Block(Expression.Constant("test"));`|`.Block() {`<br /><br /> `"test"`<br /><br /> `}`|  
|`BlockExpression block =  Expression.Block(typeof(Object), Expression.Constant("test"));`|`.Block<System.Object>() {`<br /><br /> `"test"`<br /><br /> `}`|  
  
## <a name="lambdaexpression"></a><span data-ttu-id="b221a-150">LambdaExpression</span><span class="sxs-lookup"><span data-stu-id="b221a-150">LambdaExpression</span></span>  
 <span data-ttu-id="b221a-151"><xref:System.Linq.Expressions.LambdaExpression> オブジェクトは、デリゲート型と共に表示されます。</span><span class="sxs-lookup"><span data-stu-id="b221a-151"><xref:System.Linq.Expressions.LambdaExpression> objects are displayed together with their delegate types.</span></span>  
  
 <span data-ttu-id="b221a-152">ラムダ式に名前がない場合、`#Lambda1` や `#Lambda2` など、自動的に生成された名前が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="b221a-152">If a lambda expression does not have a name, it is assigned an automatically generated name, such as `#Lambda1` or `#Lambda2`.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="b221a-153">使用例</span><span class="sxs-lookup"><span data-stu-id="b221a-153">Examples</span></span>  
  
|<span data-ttu-id="b221a-154">正規表現</span><span class="sxs-lookup"><span data-stu-id="b221a-154">Expression</span></span>|<span data-ttu-id="b221a-155">`DebugView` プロパティ</span><span class="sxs-lookup"><span data-stu-id="b221a-155">`DebugView` property</span></span>|  
|----------------|--------------------------|  
|`LambdaExpression lambda =  Expression.Lambda<Func<int>>(Expression.Constant(1));`|`.Lambda #Lambda1<System.Func'1[System.Int32]>() {`<br /><br /> `1`<br /><br /> `}`|  
|`LambdaExpression lambda =  Expression.Lambda<Func<int>>(Expression.Constant(1), "SampleLambda", null);`|`.Lambda SampleLambda<System.Func'1[System.Int32]>() {`<br /><br /> `1`<br /><br /> `}`|  
  
## <a name="labelexpression"></a><span data-ttu-id="b221a-156">LabelExpression</span><span class="sxs-lookup"><span data-stu-id="b221a-156">LabelExpression</span></span>  
 <span data-ttu-id="b221a-157"><xref:System.Linq.Expressions.LabelExpression> オブジェクトの既定値を指定した場合、その値が <xref:System.Linq.Expressions.LabelTarget> オブジェクトの前に表示されます。</span><span class="sxs-lookup"><span data-stu-id="b221a-157">If you specify a default value for the <xref:System.Linq.Expressions.LabelExpression> object, this value is displayed before the <xref:System.Linq.Expressions.LabelTarget> object.</span></span>  
  
 <span data-ttu-id="b221a-158">`.Label` トークンは、ラベルの開始を示します。</span><span class="sxs-lookup"><span data-stu-id="b221a-158">The `.Label` token indicates the start of the label.</span></span> <span data-ttu-id="b221a-159">`.LabelTarget` トークンは、ジャンプ先のターゲットを示します。</span><span class="sxs-lookup"><span data-stu-id="b221a-159">The `.LabelTarget` token indicates the destination of the target to jump to.</span></span>  
  
 <span data-ttu-id="b221a-160">ラベルに名前がない場合、`#Label1` や `#Label2` など、自動的に生成された名前が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="b221a-160">If a label does not have a name, it is assigned an automatically generated name, such as `#Label1` or `#Label2`.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="b221a-161">使用例</span><span class="sxs-lookup"><span data-stu-id="b221a-161">Examples</span></span>  
  
|<span data-ttu-id="b221a-162">正規表現</span><span class="sxs-lookup"><span data-stu-id="b221a-162">Expression</span></span>|<span data-ttu-id="b221a-163">`DebugView` プロパティ</span><span class="sxs-lookup"><span data-stu-id="b221a-163">`DebugView` property</span></span>|  
|----------------|--------------------------|  
|`LabelTarget target = Expression.Label(typeof(int), "SampleLabel"); BlockExpression block = Expression.Block( Expression.Goto(target, Expression.Constant(0)), Expression.Label(target, Expression.Constant(-1)));`|`.Block() {`<br /><br /> `.Goto SampleLabel { 0 };`<br /><br /> `.Label`<br /><br /> `-1`<br /><br /> `.LabelTarget SampleLabel:`<br /><br /> `}`|  
|`LabelTarget target = Expression.Label(); BlockExpression block = Expression.Block( Expression.Goto(target5), Expression.Label(target5));`|`.Block() {`<br /><br /> `.Goto #Label1 { };`<br /><br /> `.Label`<br /><br /> `.LabelTarget #Label1:`<br /><br /> `}`|  
  
## <a name="checked-operators"></a><span data-ttu-id="b221a-164">checked 演算子</span><span class="sxs-lookup"><span data-stu-id="b221a-164">Checked Operators</span></span>  
 <span data-ttu-id="b221a-165">checked 演算子は、演算子の前に "#" 記号が付く形式で表示されます。</span><span class="sxs-lookup"><span data-stu-id="b221a-165">Checked operators are displayed with the "#" symbol in front of the operator.</span></span> <span data-ttu-id="b221a-166">たとえば、checked 加算演算子は `#+` と表示されます。</span><span class="sxs-lookup"><span data-stu-id="b221a-166">For example, the checked addition operator is displayed as `#+`.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="b221a-167">使用例</span><span class="sxs-lookup"><span data-stu-id="b221a-167">Examples</span></span>  
  
|<span data-ttu-id="b221a-168">正規表現</span><span class="sxs-lookup"><span data-stu-id="b221a-168">Expression</span></span>|<span data-ttu-id="b221a-169">`DebugView` プロパティ</span><span class="sxs-lookup"><span data-stu-id="b221a-169">`DebugView` property</span></span>|  
|----------------|--------------------------|  
|`Expression expr = Expression.AddChecked( Expression.Constant(1), Expression.Constant(2));`|`1 #+ 2`|  
|`Expression expr = Expression.ConvertChecked( Expression.Constant(10.0), typeof(int));`|`#(System.Int32)10D`|  
  
## <a name="see-also"></a><span data-ttu-id="b221a-170">関連項目</span><span class="sxs-lookup"><span data-stu-id="b221a-170">See also</span></span>

- [<span data-ttu-id="b221a-171">式ツリー (C#)</span><span class="sxs-lookup"><span data-stu-id="b221a-171">Expression Trees (C#)</span></span>](../../../../csharp/programming-guide/concepts/expression-trees/index.md)
- [<span data-ttu-id="b221a-172">Visual Studio でのデバッグ</span><span class="sxs-lookup"><span data-stu-id="b221a-172">Debugging in Visual Studio</span></span>](/visualstudio/debugger/debugging-in-visual-studio)
- [<span data-ttu-id="b221a-173">カスタム ビジュアライザーを作成する</span><span class="sxs-lookup"><span data-stu-id="b221a-173">Create Custom Visualizers</span></span>](/visualstudio/debugger/create-custom-visualizers-of-data)
