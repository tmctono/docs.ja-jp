---
title: 式ツリーのデバッグ (Visual Studio) (C#)
description: Visual Studio の DebugView プロパティについて説明します。 このプロパティを使用して式ツリーの構造と内容を分析する方法について確認します。
ms.date: 07/20/2015
ms.assetid: 1369fa25-0fbd-4b92-98d0-8df79c49c27a
ms.openlocfilehash: 5d62a5e6fa5ce537a1ea8b316e7322eb976200c0
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2020
ms.locfileid: "87105644"
---
# <a name="debugging-expression-trees-in-visual-studio-c"></a>式ツリーのデバッグ (Visual Studio) (C#)
アプリケーションをデバッグするときに、式ツリーの構造および内容を分析できます。 式ツリーの構造の概要を簡単に取得するには、`DebugView` プロパティ使用できます。このプロパティでは、[特殊な構文を使って](debugview-syntax.md)式ツリーが表されます。 (`DebugView` はデバッグ モードでのみ使用できることに注意してください。)  

![VS デバッガー内の式ツリーの DebugView のスクリーンショット。](media/debugging-expression-trees-in-visual-studio/debugview-expression-tree.png)

`DebugView` は文字列なので、[組み込まれているテキスト ビジュアライザー](https://docs.microsoft.com/visualstudio/debugger/view-strings-visualizer#open-a-string-visualizer)を使って、複数行で表示できます。**テキスト ビジュアライザー**を使うには、`DebugView` ラベルの隣にある虫眼鏡アイコンから選択します。

 ![DebugView の結果に適用されるテキスト ビジュアライザーのスクリーンショット。](media/debugging-expression-trees-in-visual-studio/string-visualizer-debugview.png)

または、式ツリー用の[カスタム ビジュアライザー](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data)をインストールして使うこともできます。例:

- [ReadableExpressions](https://github.com/agileobjects/ReadableExpressions) ([MIT ライセンス](https://github.com/agileobjects/ReadableExpressions/blob/master/LICENSE.md)、[Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=vs-publisher-1232914.ReadableExpressionsVisualizers) で使用可能): 式ツリーがテーマを設定できる C# コードとしてレンダリングされます。さまざまなレンダリング オプションがあります。

  ![Readable Expressions Visualizer のスクリーンショット。](media/debugging-expression-trees-in-visual-studio/readable-expressions-visualizer.png)

- [Expression Tree Visualizer](https://github.com/zspitz/ExpressionTreeVisualizer/blob/master/README.md) ([MIT ライセンス](https://github.com/zspitz/ExpressionTreeVisualizer/blob/master/LICENSE)) では、式ツリーとその個々のノードのツリー ビューが提供されます。

  ![Expression Tree Visualizer のスクリーンショット。](media/debugging-expression-trees-in-visual-studio/expression-tree-visualizer.png)

### <a name="to-open-a-visualizer-for-an-expression-tree"></a>式ツリーのビジュアライザーを開くには  
  
1. **[データヒント]** 、 **[ウォッチ]** ウィンドウ、 **[自動変数]** ウィンドウ、または **[ローカル]** ウィンドウで、式ツリーの横に表示されている虫眼鏡のアイコンをクリックします。  

    使用可能なビジュアライザーの一覧が表示されます。

    ![Visual Studio からビジュアライザーを開く方法を示すスクリーンショット。](media/debugging-expression-trees-in-visual-studio/expression-tree-visualizers.png)

2. 使用するビジュアライザーをクリックします。  
  
## <a name="see-also"></a>関連項目

- [式ツリー (C#)](./index.md)
- [Visual Studio でのデバッグ](/visualstudio/debugger/debugger-feature-tour)
- [カスタム ビジュアライザーを作成する](/visualstudio/debugger/create-custom-visualizers-of-data)
- [`DebugView` 構文](debugview-syntax.md)
