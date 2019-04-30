---
title: '方法: バックグラウンド操作を使用するフォームを実装する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- threading [Windows Forms], forms
- BackgroundWorker component
- background tasks
- forms [Windows Forms], multithreading
- components [Windows Forms], asynchronous
- forms [Windows Forms], background operations
- background threads
- threading [Windows Forms], background operations
- background operations
ms.assetid: 9f483f93-1613-4be1-a021-b4934e9c78f3
ms.openlocfilehash: 98d51f9c6465186e77784aba080130110545f399
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61941188"
---
# <a name="how-to-implement-a-form-that-uses-a-background-operation"></a><span data-ttu-id="23545-102">方法: バックグラウンド操作を使用するフォームを実装する</span><span class="sxs-lookup"><span data-stu-id="23545-102">How to: Implement a Form That Uses a Background Operation</span></span>
<span data-ttu-id="23545-103">次のサンプル プログラムは、フィボナッチの数列を計算するフォームを作成します。</span><span class="sxs-lookup"><span data-stu-id="23545-103">The following example program creates a form that calculates Fibonacci numbers.</span></span> <span data-ttu-id="23545-104">計算では、ユーザー インターフェイス スレッドとは別にあるスレッドで実行されるので、ユーザー インターフェイスは引き続き、計算の進行に伴う遅延なしに実行されます。</span><span class="sxs-lookup"><span data-stu-id="23545-104">The calculation runs on a thread that is separate from the user interface thread, so the user interface continues to run without delays as the calculation proceeds.</span></span>  
  
 <span data-ttu-id="23545-105">Visual Studio では、このタスクに対する広範なサポートが用意されています。</span><span class="sxs-lookup"><span data-stu-id="23545-105">There is extensive support for this task in Visual Studio.</span></span>  
  
 <span data-ttu-id="23545-106">参照してください[チュートリアル。バック グラウンド操作を使用するフォームを実装する](walkthrough-implementing-a-form-that-uses-a-background-operation.md)します。</span><span class="sxs-lookup"><span data-stu-id="23545-106">Also see [Walkthrough: Implementing a Form That Uses a Background Operation](walkthrough-implementing-a-form-that-uses-a-background-operation.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="23545-107">例</span><span class="sxs-lookup"><span data-stu-id="23545-107">Example</span></span>  
 [!code-cpp[System.ComponentModel.BackgroundWorker#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#1)]
 [!code-csharp[System.ComponentModel.BackgroundWorker#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#1)]
 [!code-vb[System.ComponentModel.BackgroundWorker#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="23545-108">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="23545-108">Compiling the Code</span></span>  
 <span data-ttu-id="23545-109">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="23545-109">This example requires:</span></span>  
  
- <span data-ttu-id="23545-110">System、System.Drawing、および System.Windows.Forms の各アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="23545-110">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="23545-111">Visual Basic または Visual C# からこの例をビルドする方法については、[コマンド ラインからのビルド](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)、または[csc.exe を使用したコマンド ラインからのビルド](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="23545-111">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="23545-112">新しいプロジェクトにコードを貼り付けることによって、この例では、Visual Studio を構築することもできます。</span><span class="sxs-lookup"><span data-stu-id="23545-112">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="23545-113">信頼性の高いプログラミング</span><span class="sxs-lookup"><span data-stu-id="23545-113">Robust Programming</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="23545-114">どのような種類のマルチスレッドを使用している場合でも、非常に深刻で複雑なバグを引き起こしてしまう可能性があります。</span><span class="sxs-lookup"><span data-stu-id="23545-114">When using multithreading of any sort, you potentially expose yourself to very serious and complex bugs.</span></span> <span data-ttu-id="23545-115">マルチスレッドを使用するソリューションを実装する前に、「[マネージド スレッド処理の実施](../../../standard/threading/managed-threading-best-practices.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="23545-115">Consult the [Managed Threading Best Practices](../../../standard/threading/managed-threading-best-practices.md) before implementing any solution that uses multithreading.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23545-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="23545-116">See also</span></span>

- <xref:System.ComponentModel.BackgroundWorker>
- <xref:System.ComponentModel.DoWorkEventArgs>
- [<span data-ttu-id="23545-117">イベントベースの非同期パターンの概要</span><span class="sxs-lookup"><span data-stu-id="23545-117">Event-based Asynchronous Pattern Overview</span></span>](../../../standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
- [<span data-ttu-id="23545-118">マネージド スレッド処理の実施</span><span class="sxs-lookup"><span data-stu-id="23545-118">Managed Threading Best Practices</span></span>](../../../standard/threading/managed-threading-best-practices.md)
