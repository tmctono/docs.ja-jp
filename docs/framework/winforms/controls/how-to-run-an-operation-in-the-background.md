---
title: '方法: バックグラウンドで操作を実行する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- background tasks
- forms [Windows Forms], multithreading
- forms [Windows Forms], background operations
- background threads
- BackgroundWorker class [Windows Forms], examples
- threading [Windows Forms], background operations
- background operations
ms.assetid: 5b56e2aa-dc05-444f-930c-2d7b23f9ad5b
ms.openlocfilehash: 77f75a7eb1d7cc536df7110ef55727fbdf789f23
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2019
ms.locfileid: "65591604"
---
# <a name="how-to-run-an-operation-in-the-background"></a><span data-ttu-id="74eed-102">方法: バックグラウンドで操作を実行する</span><span class="sxs-lookup"><span data-stu-id="74eed-102">How to: Run an Operation in the Background</span></span>
<span data-ttu-id="74eed-103">完了に長い時間がかかる操作を実行しており、ユーザー インターフェイスで遅延が発生しないようにするには<xref:System.ComponentModel.BackgroundWorker> クラスを使用して別のスレッドで操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="74eed-103">If you have an operation that will take a long time to complete, and you do not want to cause delays in your user interface, you can use the <xref:System.ComponentModel.BackgroundWorker> class to run the operation on another thread.</span></span>  
  
 <span data-ttu-id="74eed-104">次のコード例は、バック グラウンドで時間のかかる操作を実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="74eed-104">The following code example shows how to run a time-consuming operation in the background.</span></span> <span data-ttu-id="74eed-105">フォームには、**[開始]** ボタンと **[キャンセル]** ボタンがあります。</span><span class="sxs-lookup"><span data-stu-id="74eed-105">The form has **Start** and **Cancel** buttons.</span></span> <span data-ttu-id="74eed-106">非同期操作を実行するには、**[開始]** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="74eed-106">Click the **Start** button to run an asynchronous operation.</span></span> <span data-ttu-id="74eed-107">実行中の非同期操作を停止するには、**[キャンセル]** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="74eed-107">Click the **Cancel** button to stop a running asynchronous operation.</span></span> <span data-ttu-id="74eed-108">各操作の結果は、<xref:System.Windows.Forms.MessageBox> に表示されます。</span><span class="sxs-lookup"><span data-stu-id="74eed-108">The outcome of each operation is displayed in a <xref:System.Windows.Forms.MessageBox>.</span></span>  
  
 <span data-ttu-id="74eed-109">Visual Studio では、このタスクに対する広範なサポートが用意されています。</span><span class="sxs-lookup"><span data-stu-id="74eed-109">There is extensive support for this task in Visual Studio.</span></span>  
  
 <span data-ttu-id="74eed-110">[チュートリアル: バック グラウンドで操作を実行する](walkthrough-running-an-operation-in-the-background.md)します。</span><span class="sxs-lookup"><span data-stu-id="74eed-110">Also see [Walkthrough: Running an Operation in the Background](walkthrough-running-an-operation-in-the-background.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="74eed-111">例</span><span class="sxs-lookup"><span data-stu-id="74eed-111">Example</span></span>  
 [!code-csharp[System.ComponentModel.BackgroundWorker.Example#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#1)]
 [!code-vb[System.ComponentModel.BackgroundWorker.Example#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="74eed-112">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="74eed-112">Compiling the Code</span></span>  
 <span data-ttu-id="74eed-113">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="74eed-113">This example requires:</span></span>  
  
- <span data-ttu-id="74eed-114">System、System.Drawing、および System.Windows.Forms の各アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="74eed-114">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74eed-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="74eed-115">See also</span></span>

- <xref:System.ComponentModel.BackgroundWorker>
- <xref:System.ComponentModel.DoWorkEventArgs>
- [<span data-ttu-id="74eed-116">方法: バックグラウンド操作を使用するフォームを実装する</span><span class="sxs-lookup"><span data-stu-id="74eed-116">How to: Implement a Form That Uses a Background Operation</span></span>](how-to-implement-a-form-that-uses-a-background-operation.md)
- [<span data-ttu-id="74eed-117">BackgroundWorker コンポーネント</span><span class="sxs-lookup"><span data-stu-id="74eed-117">BackgroundWorker Component</span></span>](backgroundworker-component.md)
