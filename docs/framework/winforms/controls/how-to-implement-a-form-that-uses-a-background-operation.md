---
title: '方法: バックグラウンド操作を使用するフォームを実装する'
description: バックグラウンド操作を使用する Windows フォームを実装する方法について説明します。これにより、別の操作が進行している間に1つの操作を継続して実行できます。
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
ms.openlocfilehash: 23bf4bc02fbf998d92dfce6d84e4e337cbefe7d9
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174524"
---
# <a name="how-to-implement-a-form-that-uses-a-background-operation"></a><span data-ttu-id="be886-103">方法: バックグラウンド操作を使用するフォームを実装する</span><span class="sxs-lookup"><span data-stu-id="be886-103">How to: Implement a Form That Uses a Background Operation</span></span>
<span data-ttu-id="be886-104">次のサンプル プログラムは、フィボナッチの数列を計算するフォームを作成します。</span><span class="sxs-lookup"><span data-stu-id="be886-104">The following example program creates a form that calculates Fibonacci numbers.</span></span> <span data-ttu-id="be886-105">計算では、ユーザー インターフェイス スレッドとは別にあるスレッドで実行されるので、ユーザー インターフェイスは引き続き、計算の進行に伴う遅延なしに実行されます。</span><span class="sxs-lookup"><span data-stu-id="be886-105">The calculation runs on a thread that is separate from the user interface thread, so the user interface continues to run without delays as the calculation proceeds.</span></span>  
  
 <span data-ttu-id="be886-106">Visual Studio では、このタスクに対する広範なサポートが用意されています。</span><span class="sxs-lookup"><span data-stu-id="be886-106">There is extensive support for this task in Visual Studio.</span></span>  
  
 <span data-ttu-id="be886-107">「[チュートリアル: バックグラウンド操作を使用するフォームの実装](walkthrough-implementing-a-form-that-uses-a-background-operation.md)」も参照してください。</span><span class="sxs-lookup"><span data-stu-id="be886-107">Also see [Walkthrough: Implementing a Form That Uses a Background Operation](walkthrough-implementing-a-form-that-uses-a-background-operation.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="be886-108">例</span><span class="sxs-lookup"><span data-stu-id="be886-108">Example</span></span>  
 [!code-cpp[System.ComponentModel.BackgroundWorker#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#1)]
 [!code-csharp[System.ComponentModel.BackgroundWorker#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#1)]
 [!code-vb[System.ComponentModel.BackgroundWorker#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="be886-109">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="be886-109">Compiling the Code</span></span>  
 <span data-ttu-id="be886-110">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="be886-110">This example requires:</span></span>  
  
- <span data-ttu-id="be886-111">System、System.Drawing、および System.Windows.Forms の各アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="be886-111">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="be886-112">信頼性の高いプログラミング</span><span class="sxs-lookup"><span data-stu-id="be886-112">Robust Programming</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="be886-113">どのような種類のマルチスレッドを使用している場合でも、非常に深刻で複雑なバグを引き起こしてしまう可能性があります。</span><span class="sxs-lookup"><span data-stu-id="be886-113">When using multithreading of any sort, you potentially expose yourself to very serious and complex bugs.</span></span> <span data-ttu-id="be886-114">マルチスレッドを使用するソリューションを実装する前に、「[マネージド スレッド処理の実施](../../../standard/threading/managed-threading-best-practices.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="be886-114">Consult the [Managed Threading Best Practices](../../../standard/threading/managed-threading-best-practices.md) before implementing any solution that uses multithreading.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be886-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="be886-115">See also</span></span>

- <xref:System.ComponentModel.BackgroundWorker>
- <xref:System.ComponentModel.DoWorkEventArgs>
- [<span data-ttu-id="be886-116">イベントベースの非同期パターンの概要</span><span class="sxs-lookup"><span data-stu-id="be886-116">Event-based Asynchronous Pattern Overview</span></span>](../../../standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
- [<span data-ttu-id="be886-117">マネージド スレッド処理の実施</span><span class="sxs-lookup"><span data-stu-id="be886-117">Managed Threading Best Practices</span></span>](../../../standard/threading/managed-threading-best-practices.md)
