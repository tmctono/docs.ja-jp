---
title: '方法: 分析のヒントに従ってインクを分析する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ink [WPF], analyzing
- analyzing ink [WPF]
- ink [WPF], AnalysisHintNode objects [WPF]
- AnalysisHintNode objects [WPF]
ms.assetid: d4421ed4-77f5-4640-829e-9f1de50b2ff2
ms.openlocfilehash: a4c38ddf52e9054fe9126df4b7e172548617b90d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61777001"
---
# <a name="how-to-analyze-ink-with-analysis-hints"></a><span data-ttu-id="b9f29-102">方法: 分析のヒントに従ってインクを分析する</span><span class="sxs-lookup"><span data-stu-id="b9f29-102">How to: Analyze Ink with Analysis Hints</span></span>
<span data-ttu-id="b9f29-103">[System.Windows.Ink.AnalysisHintNode](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms610344(v=vs.90))のヒントを提供します、 [System.Windows.Ink.InkAnalyzer](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms616754(v=vs.90))アタッチされます。</span><span class="sxs-lookup"><span data-stu-id="b9f29-103">An [System.Windows.Ink.AnalysisHintNode](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms610344(v=vs.90)) provides a hint for the [System.Windows.Ink.InkAnalyzer](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms616754(v=vs.90)) to which it is attached.</span></span>  <span data-ttu-id="b9f29-104">指定された領域に、ヒントが適用されます、 [System.Windows.Ink.ContextNode.Location%2A](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms594508(v=vs.90))のプロパティ、 [System.Windows.Ink.AnalysisHintNode](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms610344(v=vs.90))にインク アナライザーに余分なコンテキストを提供し、認識の精度を向上します。</span><span class="sxs-lookup"><span data-stu-id="b9f29-104">The hint applies to the area specified by the [System.Windows.Ink.ContextNode.Location%2A](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms594508(v=vs.90)) property of the [System.Windows.Ink.AnalysisHintNode](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms610344(v=vs.90)) and provides extra context to the ink analyzer to improve recognition accuracy.</span></span> <span data-ttu-id="b9f29-105">[System.Windows.Ink.InkAnalyzer](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms616754(v=vs.90))ヒントの領域内から取得したインクを分析するときに、このコンテキスト情報を適用します。</span><span class="sxs-lookup"><span data-stu-id="b9f29-105">The [System.Windows.Ink.InkAnalyzer](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms616754(v=vs.90)) applies this context information when analyzing ink obtained from within the hint's area.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b9f29-106">例</span><span class="sxs-lookup"><span data-stu-id="b9f29-106">Example</span></span>  
 <span data-ttu-id="b9f29-107">次の例では、複数を使用するアプリケーションは、 [System.Windows.Ink.AnalysisHintNode](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms610344(v=vs.90))インク入力を受け付けるフォーム上のオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="b9f29-107">The following example is an application that uses multiple [System.Windows.Ink.AnalysisHintNode](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms610344(v=vs.90)) objects on a form that accepts ink input.</span></span> <span data-ttu-id="b9f29-108">アプリケーションを使用して、 [System.Windows.Ink.AnalysisHintNode.Factoid%2A](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms594341(v=vs.90))プロパティをフォーム上の各エントリのコンテキスト情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="b9f29-108">The application uses the [System.Windows.Ink.AnalysisHintNode.Factoid%2A](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms594341(v=vs.90)) property to provide context information for each entry on the form.</span></span>  <span data-ttu-id="b9f29-109">アプリケーションでは、バック グラウンド分析を使用して、インクを分析し、すべてのインクの形式のインクを追加するユーザーを停止した後、5 秒をクリアします。</span><span class="sxs-lookup"><span data-stu-id="b9f29-109">The application uses background analysis to analyze the ink and clears the form of all ink five seconds after the user stops adding ink.</span></span>  
  
 [!code-xaml[HowToAnalyzeInk#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToAnalyzeInk/CSharp/FormAnalyzer.xaml#1)]  
  
 [!code-csharp[HowToAnalyzeInk#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToAnalyzeInk/CSharp/FormAnalyzer.xaml.cs#2)]
 [!code-vb[HowToAnalyzeInk#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToAnalyzeInk/VisualBasic/FormAnalyzer.xaml.vb#2)]
