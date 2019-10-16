---
title: Visual Studio での式ツリーのデバッグ (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 492cc28f-b7a2-4c47-b582-b3c437b8a5d5
ms.openlocfilehash: 51579c74ecbebbfb7da8bf20bef7592980ec437c
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72320356"
---
# <a name="debugging-expression-trees-in-visual-studio-visual-basic"></a><span data-ttu-id="910ae-102">Visual Studio での式ツリーのデバッグ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="910ae-102">Debugging Expression Trees in Visual Studio (Visual Basic)</span></span>
<span data-ttu-id="910ae-103">アプリケーションをデバッグするときに、式ツリーの構造および内容を分析できます。</span><span class="sxs-lookup"><span data-stu-id="910ae-103">You can analyze the structure and content of expression trees when you debug your applications.</span></span> <span data-ttu-id="910ae-104">式ツリーの構造の概要を簡単に取得するには、`DebugView` プロパティ使用できます。このプロパティでは、[特殊な構文を使って](debugview-syntax.md)式ツリーが表されます。</span><span class="sxs-lookup"><span data-stu-id="910ae-104">To get a quick overview of the expression tree structure, you can use the `DebugView` property, which represents expression trees [using a special syntax](debugview-syntax.md).</span></span> <span data-ttu-id="910ae-105">(`DebugView` はデバッグ モードでのみ使用できることに注意してください。)</span><span class="sxs-lookup"><span data-stu-id="910ae-105">(Note that `DebugView` is available only in debug mode.)</span></span>  

![式ツリーの DebugView のスクリーンショット。](media/debugging-expression-trees-in-visual-studio/debugview-visual-basic.png)

<span data-ttu-id="910ae-107">`DebugView` は文字列なので、[組み込まれているテキスト ビジュアライザー](https://docs.microsoft.com/visualstudio/debugger/view-strings-visualizer#open-a-string-visualizer)を使って、複数行で表示できます。**テキスト ビジュアライザー**を使うには、`DebugView` ラベルの隣にある虫眼鏡アイコンから選択します。</span><span class="sxs-lookup"><span data-stu-id="910ae-107">Since `DebugView` is a string, you can use the [built-in Text Visualizer](https://docs.microsoft.com/visualstudio/debugger/view-strings-visualizer#open-a-string-visualizer) to view it across multiple lines, by selecting **Text Visualizer** from the magnifying glass icon next to the `DebugView` label.</span></span>

 ![DebugView の結果に適用されるテキストビジュアライザーのスクリーンショット。](media/debugging-expression-trees-in-visual-studio/string-visualizer-vb.png)

<span data-ttu-id="910ae-109">または、式ツリー用の[カスタム ビジュアライザー](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data)をインストールして使うこともできます。例:</span><span class="sxs-lookup"><span data-stu-id="910ae-109">Alternatively, you can install and use [a custom visualizer](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data) for expression trees, such as:</span></span>

- <span data-ttu-id="910ae-110">[ReadableExpressions](https://github.com/agileobjects/ReadableExpressions) ([MIT ライセンス](https://github.com/agileobjects/ReadableExpressions/blob/master/LICENSE.md)、[Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=vs-publisher-1232914.ReadableExpressionsVisualizers) で使用可能): 式ツリーが C# コードとしてレンダリングされます。</span><span class="sxs-lookup"><span data-stu-id="910ae-110">[Readable Expressions](https://github.com/agileobjects/ReadableExpressions) ([MIT license](https://github.com/agileobjects/ReadableExpressions/blob/master/LICENSE.md), available at the [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=vs-publisher-1232914.ReadableExpressionsVisualizers)), renders the expression tree as C# code:</span></span>

  ![読み取り可能な式ビジュアライザーのスクリーンショット。](media/debugging-expression-trees-in-visual-studio/readable-expressions-visualizer.png)

- <span data-ttu-id="910ae-112">[式ツリービジュアライザー](https://github.com/zspitz/ExpressionToString#visual-studio-debugger-visualizer-for-expression-trees) ([MIT ライセンス](https://github.com/zspitz/ExpressionToString/blob/master/LICENSE)) は、式ツリー、そのプロパティ、および関連オブジェクトのグラフィカルビューを提供します。とは Visual Basic コードを使用して式ツリーを表示できます。</span><span class="sxs-lookup"><span data-stu-id="910ae-112">[Expression Tree Visualizer](https://github.com/zspitz/ExpressionToString#visual-studio-debugger-visualizer-for-expression-trees) ([MIT license](https://github.com/zspitz/ExpressionToString/blob/master/LICENSE)), provides a graphical view of the expression tree, its properties, and related objects; and can render the expression tree using Visual Basic code:</span></span>

  ![式の Tostring ビジュアライザーのスクリーンショット。](media/debugging-expression-trees-in-visual-studio/expression-to-string-visualizer-vb.png)

### <a name="to-open-a-visualizer-for-an-expression-tree"></a><span data-ttu-id="910ae-114">式ツリーのビジュアライザーを開くには</span><span class="sxs-lookup"><span data-stu-id="910ae-114">To open a visualizer for an expression tree</span></span>  
  
1. <span data-ttu-id="910ae-115">**[データヒント]** 、 **[ウォッチ]** ウィンドウ、 **[自動変数]** ウィンドウ、または **[ローカル]** ウィンドウで、式ツリーの横に表示されている虫眼鏡のアイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="910ae-115">Click the magnifying glass icon that appears next to the expression tree in **DataTips**, a **Watch** window, the **Autos** window, or the **Locals** window.</span></span>  
  
    <span data-ttu-id="910ae-116">使用可能なビジュアライザーの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="910ae-116">A list of available visualizers is displayed.:</span></span> 

    ![Visual Studio からビジュアライザーを開くユーザーのスクリーンショット。](media/debugging-expression-trees-in-visual-studio/expression-tree-visualizers-vb.png)

2. <span data-ttu-id="910ae-118">使用するビジュアライザーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="910ae-118">Click the visualizer you want to use.</span></span>  

## <a name="see-also"></a><span data-ttu-id="910ae-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="910ae-119">See also</span></span>

- [<span data-ttu-id="910ae-120">式ツリー (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="910ae-120">Expression Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md)
- [<span data-ttu-id="910ae-121">Visual Studio でのデバッグ</span><span class="sxs-lookup"><span data-stu-id="910ae-121">Debugging in Visual Studio</span></span>](/visualstudio/debugger/debugging-in-visual-studio)
- [<span data-ttu-id="910ae-122">カスタム ビジュアライザーを作成する</span><span class="sxs-lookup"><span data-stu-id="910ae-122">Create Custom Visualizers</span></span>](/visualstudio/debugger/create-custom-visualizers-of-data)
- [<span data-ttu-id="910ae-123">`DebugView` 構文</span><span class="sxs-lookup"><span data-stu-id="910ae-123">`DebugView` syntax</span></span>](debugview-syntax.md)
