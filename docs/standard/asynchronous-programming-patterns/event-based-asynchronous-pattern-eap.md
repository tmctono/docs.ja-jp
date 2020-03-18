---
title: イベント ベースの非同期パターン (EAP)
ms.date: 07/23/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- asynchronous calls
- asynchronous programming, design patterns
- asynchronous programming
ms.assetid: c6baed9f-2a25-4728-9a9a-53b7b14840cf
ms.openlocfilehash: ee8c90d63478e444b7d25cb7cbb5c969963d7c63
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2020
ms.locfileid: "73130945"
---
# <a name="event-based-asynchronous-pattern-eap"></a><span data-ttu-id="21b43-102">イベント ベースの非同期パターン (EAP)</span><span class="sxs-lookup"><span data-stu-id="21b43-102">Event-based Asynchronous Pattern (EAP)</span></span>

<span data-ttu-id="21b43-103">非同期機能をクライアント コードに公開する方法は数多くあります。</span><span class="sxs-lookup"><span data-stu-id="21b43-103">There are a number of ways to expose asynchronous features to client code.</span></span> <span data-ttu-id="21b43-104">イベント ベースの非同期パターンは、クラスが非同期動作を示す 1 つの方法を規定します。</span><span class="sxs-lookup"><span data-stu-id="21b43-104">The Event-based Asynchronous Pattern prescribes one way for classes to present asynchronous behavior.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="21b43-105">.NET Framework 4 以降では、タスク並列ライブラリによって非同期/並列プログラミングの新しいモデルが提供されます。</span><span class="sxs-lookup"><span data-stu-id="21b43-105">Starting with the .NET Framework 4, the Task Parallel Library provides a new model for asynchronous and parallel programming.</span></span> <span data-ttu-id="21b43-106">詳細については、「[タスク並列ライブラリ (TPL)](../parallel-programming/task-parallel-library-tpl.md)」および「[タスク ベースの非同期パターン (TAP)](task-based-asynchronous-pattern-tap.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="21b43-106">For more information, see [Task Parallel Library (TPL)](../parallel-programming/task-parallel-library-tpl.md) and [Task-based Asynchronous Pattern (TAP)](task-based-asynchronous-pattern-tap.md).</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="21b43-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="21b43-107">In This Section</span></span>

 [<span data-ttu-id="21b43-108">イベントベースの非同期パターンの概要</span><span class="sxs-lookup"><span data-stu-id="21b43-108">Event-based Asynchronous Pattern Overview</span></span>](event-based-asynchronous-pattern-overview.md)  
 <span data-ttu-id="21b43-109">イベント ベースの非同期パターンによって、マルチスレッド デザイン固有の多くの複雑な問題を気にせずに、マルチスレッド アプリケーションの利点を活用できるしくみを説明します。</span><span class="sxs-lookup"><span data-stu-id="21b43-109">Describes how the Event-based Asynchronous Pattern makes available the advantages of multithreaded applications while hiding many of the complex issues inherent in multithreaded design.</span></span>  
  
 [<span data-ttu-id="21b43-110">イベントベースの非同期パターンの実装</span><span class="sxs-lookup"><span data-stu-id="21b43-110">Implementing the Event-based Asynchronous Pattern</span></span>](implementing-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="21b43-111">非同期機能を持つクラスをパッケージ化するための標準的な方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="21b43-111">Describes the standardized way to package a class that has asynchronous features.</span></span>  
  
 [<span data-ttu-id="21b43-112">イベントベースの非同期パターンを実装するための推奨される手順</span><span class="sxs-lookup"><span data-stu-id="21b43-112">Best Practices for Implementing the Event-based Asynchronous Pattern</span></span>](best-practices-for-implementing-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="21b43-113">イベント ベースの非同期パターンに従って非同期機能を公開するための要件について説明します。</span><span class="sxs-lookup"><span data-stu-id="21b43-113">Describes the requirements for exposing asynchronous features according to the Event-based Asynchronous Pattern.</span></span>  
  
 [<span data-ttu-id="21b43-114">イベントベースの非同期パターンをいつ実装するかの決定</span><span class="sxs-lookup"><span data-stu-id="21b43-114">Deciding When to Implement the Event-based Asynchronous Pattern</span></span>](deciding-when-to-implement-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="21b43-115">どのような場合に、<xref:System.IAsyncResult>非同期プログラミング モデル (APM)[ で表される ](asynchronous-programming-model-apm.md) パターンではなく、イベント ベースの非同期パターンの実装を選択するかを判断する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="21b43-115">Describes how to determine when you should choose to implement the Event-based Asynchronous Pattern instead of the <xref:System.IAsyncResult> pattern represented by the [Asynchronous Programming Model (APM)](asynchronous-programming-model-apm.md)</span></span>
  
 [<span data-ttu-id="21b43-116">方法: イベントベースの非同期パターンをサポートするコンポーネントを実装する</span><span class="sxs-lookup"><span data-stu-id="21b43-116">How to: Implement a Component That Supports the Event-based Asynchronous Pattern</span></span>](component-that-supports-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="21b43-117">イベント ベースの非同期パターンを実装するコンポーネントの作成方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="21b43-117">Describes how to create a component that implements the Event-based Asynchronous Pattern.</span></span> <span data-ttu-id="21b43-118">これは、<xref:System.ComponentModel?displayProperty=nameWithType> 名前空間のヘルパー クラスを使用して実装します。これにより、コンポーネントは任意のアプリケーション モデルで正常に動作します。</span><span class="sxs-lookup"><span data-stu-id="21b43-118">It is implemented using helper classes from the <xref:System.ComponentModel?displayProperty=nameWithType> namespace, which ensures that the component works correctly under any application model.</span></span>  

 [<span data-ttu-id="21b43-119">方法: イベントベースの非同期パターンのクライアントを実装する</span><span class="sxs-lookup"><span data-stu-id="21b43-119">How to: Implement a Client of the Event-based Asynchronous Pattern</span></span>](how-to-implement-a-client-of-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="21b43-120">イベント ベースの非同期パターンを実装するコンポーネントを使用するクライアントの作成方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="21b43-120">Describes how to create a client that uses a component that implements the Event-based Asynchronous Pattern.</span></span>
  
 [<span data-ttu-id="21b43-121">方法: イベントベースの非同期パターンをサポートするコンポーネントを使用する</span><span class="sxs-lookup"><span data-stu-id="21b43-121">How to: Use Components That Support the Event-based Asynchronous Pattern</span></span>](how-to-use-components-that-support-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="21b43-122">イベント ベースの非同期パターンをサポートするコンポーネントの使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="21b43-122">Describes how to use a component that supports the Event-based Asynchronous Pattern.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="21b43-123">リファレンス</span><span class="sxs-lookup"><span data-stu-id="21b43-123">Reference</span></span>

 <xref:System.ComponentModel.AsyncOperation>  
 <span data-ttu-id="21b43-124"><xref:System.ComponentModel.AsyncOperation> クラスについて説明し、すべてのメンバーへのリンクの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="21b43-124">Describes the <xref:System.ComponentModel.AsyncOperation> class and has links to all its members.</span></span>  
  
 <xref:System.ComponentModel.AsyncOperationManager>  
 <span data-ttu-id="21b43-125"><xref:System.ComponentModel.AsyncOperationManager> クラスについて説明し、すべてのメンバーへのリンクの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="21b43-125">Describes the <xref:System.ComponentModel.AsyncOperationManager> class and has links to all its members.</span></span>  
  
 <xref:System.ComponentModel.BackgroundWorker>  
 <span data-ttu-id="21b43-126"><xref:System.ComponentModel.BackgroundWorker> コンポーネントについて説明し、すべてのメンバーへのリンクの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="21b43-126">Describes the <xref:System.ComponentModel.BackgroundWorker> component and has links to all its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="21b43-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="21b43-127">Related Sections</span></span>

 [<span data-ttu-id="21b43-128">タスク並列ライブラリ (TPL)</span><span class="sxs-lookup"><span data-stu-id="21b43-128">Task Parallel Library (TPL)</span></span>](../parallel-programming/task-parallel-library-tpl.md)  
 <span data-ttu-id="21b43-129">非同期操作および並列操作のプログラミング モデルについて説明します。</span><span class="sxs-lookup"><span data-stu-id="21b43-129">Describes a programming model for asynchronous and parallel operations.</span></span>  
  
 [<span data-ttu-id="21b43-130">スレッド化</span><span class="sxs-lookup"><span data-stu-id="21b43-130">Threading</span></span>](../../../docs/standard/threading/index.md)  
 <span data-ttu-id="21b43-131">.NET のマルチスレッド機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="21b43-131">Describes multithreading features in .NET.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21b43-132">参照</span><span class="sxs-lookup"><span data-stu-id="21b43-132">See also</span></span>

- [<span data-ttu-id="21b43-133">マネージド スレッド処理の実施</span><span class="sxs-lookup"><span data-stu-id="21b43-133">Managed Threading Best Practices</span></span>](../threading/managed-threading-best-practices.md)
- [<span data-ttu-id="21b43-134">イベント</span><span class="sxs-lookup"><span data-stu-id="21b43-134">Events</span></span>](../events/index.md)
- [<span data-ttu-id="21b43-135">非同期プログラミングのデザイン パターン</span><span class="sxs-lookup"><span data-stu-id="21b43-135">Asynchronous Programming Design Patterns</span></span>](index.md)
