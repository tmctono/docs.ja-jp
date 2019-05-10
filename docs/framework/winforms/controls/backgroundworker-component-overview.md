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
ms.openlocfilehash: da1d87464ef30fb549a2c201170e81c45cbdf6fc
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64587738"
---
# <a name="backgroundworker-component-overview"></a><span data-ttu-id="00320-102">BackgroundWorker コンポーネントの概要</span><span class="sxs-lookup"><span data-stu-id="00320-102">BackgroundWorker Component Overview</span></span>
<span data-ttu-id="00320-103">一般的な操作には、実行時間が長くかかるものが数多くあります。</span><span class="sxs-lookup"><span data-stu-id="00320-103">There are many commonly performed operations that can take a long time to execute.</span></span> <span data-ttu-id="00320-104">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="00320-104">For example:</span></span>  
  
- <span data-ttu-id="00320-105">イメージのダウンロード</span><span class="sxs-lookup"><span data-stu-id="00320-105">Image downloads</span></span>  
  
- <span data-ttu-id="00320-106">Web サービスの起動</span><span class="sxs-lookup"><span data-stu-id="00320-106">Web service invocations</span></span>  
  
- <span data-ttu-id="00320-107">ファイルのダウンロードとアップロード (ピアツーピア アプリケーションの場合を含む)</span><span class="sxs-lookup"><span data-stu-id="00320-107">File downloads and uploads (including for peer-to-peer applications)</span></span>  
  
- <span data-ttu-id="00320-108">ローカルでの複雑な計算</span><span class="sxs-lookup"><span data-stu-id="00320-108">Complex local computations</span></span>  
  
- <span data-ttu-id="00320-109">データベース トランザクション</span><span class="sxs-lookup"><span data-stu-id="00320-109">Database transactions</span></span>  
  
- <span data-ttu-id="00320-110">ローカル ディスク アクセス (前提としてメモリ アクセスに比べて低速です)</span><span class="sxs-lookup"><span data-stu-id="00320-110">Local disk access, given its slow speed relative to memory access</span></span>  
  
 <span data-ttu-id="00320-111">以上のような操作の実行時には、ユーザー インターフェイスがハングアップすることがあります。</span><span class="sxs-lookup"><span data-stu-id="00320-111">Operations like these can cause your user interface to hang while they are running.</span></span> <span data-ttu-id="00320-112">応答性に優れた UI を必要としながらも、このような操作との関連で長時間の遅延に直面する場合は、<xref:System.ComponentModel.BackgroundWorker> コンポーネントが便利なソリューションになります。</span><span class="sxs-lookup"><span data-stu-id="00320-112">When you want a responsive UI and you are faced with long delays associated with such operations, the <xref:System.ComponentModel.BackgroundWorker> component provides a convenient solution.</span></span>  
  
 <span data-ttu-id="00320-113"><xref:System.ComponentModel.BackgroundWorker> コンポーネントを使用すると、時間のかかる操作を、アプリケーションのメイン UI スレッドとは別のスレッドで非同期的に ("バックグラウンドで") 実行できます。</span><span class="sxs-lookup"><span data-stu-id="00320-113">The <xref:System.ComponentModel.BackgroundWorker> component gives you the ability to execute time-consuming operations asynchronously ("in the background"), on a thread different from your application's main UI thread.</span></span> <span data-ttu-id="00320-114"><xref:System.ComponentModel.BackgroundWorker> を使用するには、バックグラウンドで実行する、時間のかかるワーカー メソッドをこのコンポーネントに通知して、<xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> メソッドを呼び出すだけです。</span><span class="sxs-lookup"><span data-stu-id="00320-114">To use a <xref:System.ComponentModel.BackgroundWorker>, you simply tell it what time-consuming worker method to execute in the background, and then you call the <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> method.</span></span> <span data-ttu-id="00320-115">呼び出し元スレッドが正常に動作し続けると共に、ワーカー メソッドも非同期的に動作します。</span><span class="sxs-lookup"><span data-stu-id="00320-115">Your calling thread continues to run normally while the worker method runs asynchronously.</span></span> <span data-ttu-id="00320-116">このメソッドが終了すると、<xref:System.ComponentModel.BackgroundWorker> は、<xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> イベントを起動して、呼び出し元スレッドに警告します。このイベントには、オプションで操作の結果を含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="00320-116">When the method is finished, the <xref:System.ComponentModel.BackgroundWorker> alerts the calling thread by firing the <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> event, which optionally contains the results of the operation.</span></span>  
  
 <span data-ttu-id="00320-117"><xref:System.ComponentModel.BackgroundWorker>コンポーネントは、**ツールボックス**の**コンポーネント**タブ。<xref:System.ComponentModel.BackgroundWorker> をフォームに追加するには、<xref:System.ComponentModel.BackgroundWorker> コンポーネントをフォームにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="00320-117">The <xref:System.ComponentModel.BackgroundWorker> component is available from the **Toolbox**, in the **Components** tab. To add a <xref:System.ComponentModel.BackgroundWorker> to your form, drag the <xref:System.ComponentModel.BackgroundWorker> component onto your form.</span></span> <span data-ttu-id="00320-118">コンポーネント トレイに表示され、そのプロパティに表示、**プロパティ**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="00320-118">It appears in the component tray, and its properties appear in the **Properties** window.</span></span>  
  
 <span data-ttu-id="00320-119">非同期操作を開始するには、<xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="00320-119">To start your asynchronous operation, use the <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> method.</span></span> <span data-ttu-id="00320-120"><xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> は、オプションの `object` パラメーターを受け取り、このパラメーターを使用してワーカー メソッドに引数を渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="00320-120"><xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> takes an optional `object` parameter, which can be used to pass arguments to your worker method.</span></span> <span data-ttu-id="00320-121"><xref:System.ComponentModel.BackgroundWorker> クラスは、<xref:System.ComponentModel.BackgroundWorker.DoWork> イベントを公開します。このイベントには、<xref:System.ComponentModel.BackgroundWorker.DoWork> イベント ハンドラー経由でワーカー スレッドをアタッチします。</span><span class="sxs-lookup"><span data-stu-id="00320-121">The <xref:System.ComponentModel.BackgroundWorker> class exposes the <xref:System.ComponentModel.BackgroundWorker.DoWork> event, to which your worker thread is attached through a <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler.</span></span>  
  
 <span data-ttu-id="00320-122"><xref:System.ComponentModel.BackgroundWorker.DoWork> イベント ハンドラーは、<xref:System.ComponentModel.DoWorkEventArgs> プロパティを持つ <xref:System.ComponentModel.DoWorkEventArgs.Argument%2A> パラメーターを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="00320-122">The <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler takes a <xref:System.ComponentModel.DoWorkEventArgs> parameter, which has an <xref:System.ComponentModel.DoWorkEventArgs.Argument%2A> property.</span></span> <span data-ttu-id="00320-123">このプロパティは、<xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> からパラメーターを受け取り、<xref:System.ComponentModel.BackgroundWorker.DoWork> イベント ハンドラーで呼び出されるワーカー メソッドに渡されます。</span><span class="sxs-lookup"><span data-stu-id="00320-123">This property receives the parameter from <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> and can be passed to your worker method, which will be called in the <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler.</span></span> <span data-ttu-id="00320-124">次の例は、`ComputeFibonacci` というワーカー メソッドの結果を代入する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="00320-124">The following example shows how to assign a result from a worker method called `ComputeFibonacci`.</span></span> <span data-ttu-id="00320-125">大規模な使用例を参照しての一部である[方法。バック グラウンド操作を使用してフォームを実装する](how-to-implement-a-form-that-uses-a-background-operation.md)します。</span><span class="sxs-lookup"><span data-stu-id="00320-125">It is part of a larger example, which you can find at [How to: Implement a Form That Uses a Background Operation](how-to-implement-a-form-that-uses-a-background-operation.md).</span></span>  
  
 [!code-cpp[System.ComponentModel.BackgroundWorker#5](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#5)]
 [!code-csharp[System.ComponentModel.BackgroundWorker#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#5)]
 [!code-vb[System.ComponentModel.BackgroundWorker#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#5)]  
  
 <span data-ttu-id="00320-126">イベント ハンドラーの使用に関する詳細については、次を参照してください。[イベント](../../../standard/events/index.md)します。</span><span class="sxs-lookup"><span data-stu-id="00320-126">For more information on using event handlers, see [Events](../../../standard/events/index.md).</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="00320-127">どのような種類のマルチスレッドを使用している場合でも、非常に深刻で複雑なバグを引き起こしてしまう可能性があります。</span><span class="sxs-lookup"><span data-stu-id="00320-127">When using multithreading of any sort, you potentially expose yourself to very serious and complex bugs.</span></span> <span data-ttu-id="00320-128">マルチスレッドを使用するソリューションを実装する前に、「[マネージド スレッド処理の実施](../../../standard/threading/managed-threading-best-practices.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="00320-128">Consult the [Managed Threading Best Practices](../../../standard/threading/managed-threading-best-practices.md) before implementing any solution that uses multithreading.</span></span>  
  
 <span data-ttu-id="00320-129">使用しての詳細については、<xref:System.ComponentModel.BackgroundWorker>クラスを参照してください[方法。バックグラウンドで操作を実行する](how-to-run-an-operation-in-the-background.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="00320-129">For more information on using the <xref:System.ComponentModel.BackgroundWorker> class, see [How to: Run an Operation in the Background](how-to-run-an-operation-in-the-background.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00320-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="00320-130">See also</span></span>

- [<span data-ttu-id="00320-131">マネージド スレッド処理</span><span class="sxs-lookup"><span data-stu-id="00320-131">Managed Threading</span></span>](../../../standard/threading/index.md)
- [<span data-ttu-id="00320-132">イベントベースの非同期パターンの概要</span><span class="sxs-lookup"><span data-stu-id="00320-132">Event-based Asynchronous Pattern Overview</span></span>](../../../standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
- [<span data-ttu-id="00320-133">方法: バックグラウンド操作を使用するフォームを実装する</span><span class="sxs-lookup"><span data-stu-id="00320-133">How to: Implement a Form That Uses a Background Operation</span></span>](how-to-implement-a-form-that-uses-a-background-operation.md)
