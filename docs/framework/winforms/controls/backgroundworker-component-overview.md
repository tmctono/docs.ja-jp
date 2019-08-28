---
title: BackgroundWorker コンポーネントの概要
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- BackgroundWorker
helpviewer_keywords:
- BackgroundWorker component
- background tasks
- Asynchronous Pattern
- forms [Windows Forms], multithreading
- components [Windows Forms], asynchronous
- forms [Windows Forms], background operations
- threading [Windows Forms], background operations
- background operations
ms.assetid: 64e9b3ab-7443-4a77-ab17-b8b8c0cb3f62
ms.openlocfilehash: e91d74b7ca5515dd63ba17a9111cadf5090dae2a
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046103"
---
# <a name="backgroundworker-component-overview"></a><span data-ttu-id="26be9-102">BackgroundWorker コンポーネントの概要</span><span class="sxs-lookup"><span data-stu-id="26be9-102">BackgroundWorker Component Overview</span></span>
<span data-ttu-id="26be9-103">一般的な操作には、実行時間が長くかかるものが数多くあります。</span><span class="sxs-lookup"><span data-stu-id="26be9-103">There are many commonly performed operations that can take a long time to execute.</span></span> <span data-ttu-id="26be9-104">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="26be9-104">For example:</span></span>  
  
- <span data-ttu-id="26be9-105">イメージのダウンロード</span><span class="sxs-lookup"><span data-stu-id="26be9-105">Image downloads</span></span>  
  
- <span data-ttu-id="26be9-106">Web サービスの起動</span><span class="sxs-lookup"><span data-stu-id="26be9-106">Web service invocations</span></span>  
  
- <span data-ttu-id="26be9-107">ファイルのダウンロードとアップロード (ピアツーピア アプリケーションの場合を含む)</span><span class="sxs-lookup"><span data-stu-id="26be9-107">File downloads and uploads (including for peer-to-peer applications)</span></span>  
  
- <span data-ttu-id="26be9-108">ローカルでの複雑な計算</span><span class="sxs-lookup"><span data-stu-id="26be9-108">Complex local computations</span></span>  
  
- <span data-ttu-id="26be9-109">データベース トランザクション</span><span class="sxs-lookup"><span data-stu-id="26be9-109">Database transactions</span></span>  
  
- <span data-ttu-id="26be9-110">ローカル ディスク アクセス (前提としてメモリ アクセスに比べて低速です)</span><span class="sxs-lookup"><span data-stu-id="26be9-110">Local disk access, given its slow speed relative to memory access</span></span>  
  
 <span data-ttu-id="26be9-111">これらの操作を実行すると、ユーザーインターフェイスが実行中にブロックされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="26be9-111">Operations like these can cause your user interface to block while they are running.</span></span> <span data-ttu-id="26be9-112">応答性に優れた UI を必要としながらも、このような操作との関連で長時間の遅延に直面する場合は、<xref:System.ComponentModel.BackgroundWorker> コンポーネントが便利なソリューションになります。</span><span class="sxs-lookup"><span data-stu-id="26be9-112">When you want a responsive UI and you are faced with long delays associated with such operations, the <xref:System.ComponentModel.BackgroundWorker> component provides a convenient solution.</span></span>  
  
 <span data-ttu-id="26be9-113"><xref:System.ComponentModel.BackgroundWorker> コンポーネントを使用すると、時間のかかる操作を、アプリケーションのメイン UI スレッドとは別のスレッドで非同期的に ("バックグラウンドで") 実行できます。</span><span class="sxs-lookup"><span data-stu-id="26be9-113">The <xref:System.ComponentModel.BackgroundWorker> component gives you the ability to execute time-consuming operations asynchronously ("in the background"), on a thread different from your application's main UI thread.</span></span> <span data-ttu-id="26be9-114"><xref:System.ComponentModel.BackgroundWorker> を使用するには、バックグラウンドで実行する、時間のかかるワーカー メソッドをこのコンポーネントに通知して、<xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> メソッドを呼び出すだけです。</span><span class="sxs-lookup"><span data-stu-id="26be9-114">To use a <xref:System.ComponentModel.BackgroundWorker>, you simply tell it what time-consuming worker method to execute in the background, and then you call the <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> method.</span></span> <span data-ttu-id="26be9-115">呼び出し元スレッドが正常に動作し続けると共に、ワーカー メソッドも非同期的に動作します。</span><span class="sxs-lookup"><span data-stu-id="26be9-115">Your calling thread continues to run normally while the worker method runs asynchronously.</span></span> <span data-ttu-id="26be9-116">このメソッドが終了すると、<xref:System.ComponentModel.BackgroundWorker> は、<xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> イベントを起動して、呼び出し元スレッドに警告します。このイベントには、オプションで操作の結果を含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="26be9-116">When the method is finished, the <xref:System.ComponentModel.BackgroundWorker> alerts the calling thread by firing the <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> event, which optionally contains the results of the operation.</span></span>  
  
 <span data-ttu-id="26be9-117">コンポーネントは、コンポーネント タブの **ツールボックス** から使用できます。 <xref:System.ComponentModel.BackgroundWorker><xref:System.ComponentModel.BackgroundWorker> をフォームに追加するには、<xref:System.ComponentModel.BackgroundWorker> コンポーネントをフォームにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="26be9-117">The <xref:System.ComponentModel.BackgroundWorker> component is available from the **Toolbox**, in the **Components** tab. To add a <xref:System.ComponentModel.BackgroundWorker> to your form, drag the <xref:System.ComponentModel.BackgroundWorker> component onto your form.</span></span> <span data-ttu-id="26be9-118">コンポーネントトレイに表示され、プロパティが **[プロパティ]** ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="26be9-118">It appears in the component tray, and its properties appear in the **Properties** window.</span></span>  
  
 <span data-ttu-id="26be9-119">非同期操作を開始するには、<xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="26be9-119">To start your asynchronous operation, use the <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> method.</span></span> <span data-ttu-id="26be9-120"><xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> は、オプションの `object` パラメーターを受け取り、このパラメーターを使用してワーカー メソッドに引数を渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="26be9-120"><xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> takes an optional `object` parameter, which can be used to pass arguments to your worker method.</span></span> <span data-ttu-id="26be9-121"><xref:System.ComponentModel.BackgroundWorker> クラスは、<xref:System.ComponentModel.BackgroundWorker.DoWork> イベントを公開します。このイベントには、<xref:System.ComponentModel.BackgroundWorker.DoWork> イベント ハンドラー経由でワーカー スレッドをアタッチします。</span><span class="sxs-lookup"><span data-stu-id="26be9-121">The <xref:System.ComponentModel.BackgroundWorker> class exposes the <xref:System.ComponentModel.BackgroundWorker.DoWork> event, to which your worker thread is attached through a <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler.</span></span>  
  
 <span data-ttu-id="26be9-122"><xref:System.ComponentModel.BackgroundWorker.DoWork> イベント ハンドラーは、<xref:System.ComponentModel.DoWorkEventArgs> プロパティを持つ <xref:System.ComponentModel.DoWorkEventArgs.Argument%2A> パラメーターを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="26be9-122">The <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler takes a <xref:System.ComponentModel.DoWorkEventArgs> parameter, which has an <xref:System.ComponentModel.DoWorkEventArgs.Argument%2A> property.</span></span> <span data-ttu-id="26be9-123">このプロパティは、<xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> からパラメーターを受け取り、<xref:System.ComponentModel.BackgroundWorker.DoWork> イベント ハンドラーで呼び出されるワーカー メソッドに渡されます。</span><span class="sxs-lookup"><span data-stu-id="26be9-123">This property receives the parameter from <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> and can be passed to your worker method, which will be called in the <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler.</span></span> <span data-ttu-id="26be9-124">次の例は、`ComputeFibonacci` というワーカー メソッドの結果を代入する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="26be9-124">The following example shows how to assign a result from a worker method called `ComputeFibonacci`.</span></span> <span data-ttu-id="26be9-125">これは大規模な例に含まれています。 [詳細については、「」を参照してください。バックグラウンド操作](how-to-implement-a-form-that-uses-a-background-operation.md)を使用するフォームを実装します。</span><span class="sxs-lookup"><span data-stu-id="26be9-125">It is part of a larger example, which you can find at [How to: Implement a Form That Uses a Background Operation](how-to-implement-a-form-that-uses-a-background-operation.md).</span></span>  
  
 [!code-cpp[System.ComponentModel.BackgroundWorker#5](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#5)]
 [!code-csharp[System.ComponentModel.BackgroundWorker#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#5)]
 [!code-vb[System.ComponentModel.BackgroundWorker#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#5)]  
  
 <span data-ttu-id="26be9-126">イベントハンドラーの使用方法の詳細については、「[イベント](../../../standard/events/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="26be9-126">For more information on using event handlers, see [Events](../../../standard/events/index.md).</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="26be9-127">どのような種類のマルチスレッドを使用している場合でも、非常に深刻で複雑なバグを引き起こしてしまう可能性があります。</span><span class="sxs-lookup"><span data-stu-id="26be9-127">When using multithreading of any sort, you potentially expose yourself to very serious and complex bugs.</span></span> <span data-ttu-id="26be9-128">マルチスレッドを使用するソリューションを実装する前に、「[マネージド スレッド処理の実施](../../../standard/threading/managed-threading-best-practices.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="26be9-128">Consult the [Managed Threading Best Practices](../../../standard/threading/managed-threading-best-practices.md) before implementing any solution that uses multithreading.</span></span>  
  
 <span data-ttu-id="26be9-129">クラスの<xref:System.ComponentModel.BackgroundWorker>使用方法の詳細について[は、「方法:バックグラウンドで操作を実行する](how-to-run-an-operation-in-the-background.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="26be9-129">For more information on using the <xref:System.ComponentModel.BackgroundWorker> class, see [How to: Run an Operation in the Background](how-to-run-an-operation-in-the-background.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26be9-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="26be9-130">See also</span></span>

- [<span data-ttu-id="26be9-131">マネージド スレッド処理</span><span class="sxs-lookup"><span data-stu-id="26be9-131">Managed Threading</span></span>](../../../standard/threading/index.md)
- [<span data-ttu-id="26be9-132">イベントベースの非同期パターンの概要</span><span class="sxs-lookup"><span data-stu-id="26be9-132">Event-based Asynchronous Pattern Overview</span></span>](../../../standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
- [<span data-ttu-id="26be9-133">方法: バックグラウンド操作を使用するフォームを実装する</span><span class="sxs-lookup"><span data-stu-id="26be9-133">How to: Implement a Form That Uses a Background Operation</span></span>](how-to-implement-a-form-that-uses-a-background-operation.md)
