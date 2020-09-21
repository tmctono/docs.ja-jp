---
title: 式ツリーのデバッグ (Visual Studio) (C#)
description: Visual Studio の DebugView プロパティについて説明します。 このプロパティを使用して式ツリーの構造と内容を分析する方法について確認します。
ms.date: 07/20/2015
ms.assetid: 1369fa25-0fbd-4b92-98d0-8df79c49c27a
ms.openlocfilehash: fab378149fb14ccf6a66434c933aa24a8c9c6119
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90555615"
---
# <a name="debugging-expression-trees-in-visual-studio-c"></a><span data-ttu-id="f1911-104">式ツリーのデバッグ (Visual Studio) (C#)</span><span class="sxs-lookup"><span data-stu-id="f1911-104">Debugging Expression Trees in Visual Studio (C#)</span></span>
<span data-ttu-id="f1911-105">アプリケーションをデバッグするときに、式ツリーの構造および内容を分析できます。</span><span class="sxs-lookup"><span data-stu-id="f1911-105">You can analyze the structure and content of expression trees when you debug your applications.</span></span> <span data-ttu-id="f1911-106">式ツリーの構造の概要を簡単に取得するには、`DebugView` プロパティ使用できます。このプロパティでは、[特殊な構文を使って](debugview-syntax.md)式ツリーが表されます。</span><span class="sxs-lookup"><span data-stu-id="f1911-106">To get a quick overview of the expression tree structure, you can use the `DebugView` property, which represents expression trees [using a special syntax](debugview-syntax.md).</span></span> <span data-ttu-id="f1911-107">(`DebugView` はデバッグ モードでのみ使用できることに注意してください。)</span><span class="sxs-lookup"><span data-stu-id="f1911-107">(Note that `DebugView` is available only in debug mode.)</span></span>  

![VS デバッガー内の式ツリーの DebugView のスクリーンショット。](media/debugging-expression-trees-in-visual-studio/debugview-expression-tree.png)

<span data-ttu-id="f1911-109">`DebugView` は文字列なので、[組み込まれているテキスト ビジュアライザー](/visualstudio/debugger/view-strings-visualizer#open-a-string-visualizer)を使って、複数行で表示できます。**テキスト ビジュアライザー**を使うには、`DebugView` ラベルの隣にある虫眼鏡アイコンから選択します。</span><span class="sxs-lookup"><span data-stu-id="f1911-109">Since `DebugView` is a string, you can use the [built-in Text Visualizer](/visualstudio/debugger/view-strings-visualizer#open-a-string-visualizer) to view it across multiple lines, by selecting **Text Visualizer** from the magnifying glass icon next to the `DebugView` label.</span></span>

 ![DebugView の結果に適用されるテキスト ビジュアライザーのスクリーンショット。](media/debugging-expression-trees-in-visual-studio/string-visualizer-debugview.png)

<span data-ttu-id="f1911-111">または、式ツリー用の[カスタム ビジュアライザー](/visualstudio/debugger/create-custom-visualizers-of-data)をインストールして使うこともできます。例:</span><span class="sxs-lookup"><span data-stu-id="f1911-111">Alternatively, you can install and use [a custom visualizer](/visualstudio/debugger/create-custom-visualizers-of-data) for expression trees, such as:</span></span>

- <span data-ttu-id="f1911-112">[ReadableExpressions](https://github.com/agileobjects/ReadableExpressions) ([MIT ライセンス](https://github.com/agileobjects/ReadableExpressions/blob/master/LICENSE.md)、[Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=vs-publisher-1232914.ReadableExpressionsVisualizers) で使用可能): 式ツリーがテーマを設定できる C# コードとしてレンダリングされます。さまざまなレンダリング オプションがあります。</span><span class="sxs-lookup"><span data-stu-id="f1911-112">[Readable Expressions](https://github.com/agileobjects/ReadableExpressions) ([MIT license](https://github.com/agileobjects/ReadableExpressions/blob/master/LICENSE.md), available at the [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=vs-publisher-1232914.ReadableExpressionsVisualizers)), renders the expression tree as themeable C# code, with various rendering options:</span></span>

  ![Readable Expressions Visualizer のスクリーンショット。](media/debugging-expression-trees-in-visual-studio/readable-expressions-visualizer.png)

- <span data-ttu-id="f1911-114">[Expression Tree Visualizer](https://github.com/zspitz/ExpressionTreeVisualizer/blob/master/README.md) ([MIT ライセンス](https://github.com/zspitz/ExpressionTreeVisualizer/blob/master/LICENSE)) では、式ツリーとその個々のノードのツリー ビューが提供されます。</span><span class="sxs-lookup"><span data-stu-id="f1911-114">[Expression Tree Visualizer](https://github.com/zspitz/ExpressionTreeVisualizer/blob/master/README.md) ([MIT license](https://github.com/zspitz/ExpressionTreeVisualizer/blob/master/LICENSE)) provides a tree view of the expression tree and its individual nodes:</span></span>

  ![Expression Tree Visualizer のスクリーンショット。](media/debugging-expression-trees-in-visual-studio/expression-tree-visualizer.png)

### <a name="to-open-a-visualizer-for-an-expression-tree"></a><span data-ttu-id="f1911-116">式ツリーのビジュアライザーを開くには</span><span class="sxs-lookup"><span data-stu-id="f1911-116">To open a visualizer for an expression tree</span></span>  
  
1. <span data-ttu-id="f1911-117">**[データヒント]** 、 **[ウォッチ]** ウィンドウ、 **[自動変数]** ウィンドウ、または **[ローカル]** ウィンドウで、式ツリーの横に表示されている虫眼鏡のアイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f1911-117">Click the magnifying glass icon that appears next to the expression tree in **DataTips**, a **Watch** window, the **Autos** window, or the **Locals** window.</span></span>  

    <span data-ttu-id="f1911-118">使用可能なビジュアライザーの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f1911-118">A list of available visualizers is displayed.:</span></span>

    ![Visual Studio からビジュアライザーを開く方法を示すスクリーンショット。](media/debugging-expression-trees-in-visual-studio/expression-tree-visualizers.png)

2. <span data-ttu-id="f1911-120">使用するビジュアライザーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f1911-120">Click the visualizer you want to use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1911-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="f1911-121">See also</span></span>

- [<span data-ttu-id="f1911-122">式ツリー (C#)</span><span class="sxs-lookup"><span data-stu-id="f1911-122">Expression Trees (C#)</span></span>](./index.md)
- [<span data-ttu-id="f1911-123">Visual Studio でのデバッグ</span><span class="sxs-lookup"><span data-stu-id="f1911-123">Debugging in Visual Studio</span></span>](/visualstudio/debugger/debugger-feature-tour)
- [<span data-ttu-id="f1911-124">カスタム ビジュアライザーを作成する</span><span class="sxs-lookup"><span data-stu-id="f1911-124">Create Custom Visualizers</span></span>](/visualstudio/debugger/create-custom-visualizers-of-data)
- [<span data-ttu-id="f1911-125">`DebugView` 構文</span><span class="sxs-lookup"><span data-stu-id="f1911-125">`DebugView` syntax</span></span>](debugview-syntax.md)
