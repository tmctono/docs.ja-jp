---
title: マネージド スレッド処理の基本
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- multiple threads
- threading [.NET Framework], multiple threads
- threading [.NET Framework], about threading
- managed threading
ms.assetid: b2944911-0e8f-427d-a8bb-077550618935
ms.openlocfilehash: 4d2a96619fd1c48c79b5590efdb52c307d29710c
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2020
ms.locfileid: "84291007"
---
# <a name="managed-threading-basics"></a><span data-ttu-id="f1202-102">マネージド スレッド処理の基本</span><span class="sxs-lookup"><span data-stu-id="f1202-102">Managed threading basics</span></span>

<span data-ttu-id="f1202-103">このセクションの最初の 5 つのトピックは、マネージド スレッド処理を使用するタイミングを判断するのに役立つように設計されており、また、いくつかの基本的な機能について説明するためのものです。</span><span class="sxs-lookup"><span data-stu-id="f1202-103">The first five topics of this section are designed to help you determine when to use managed threading and to explain some basic features.</span></span> <span data-ttu-id="f1202-104">その他の機能を提供するクラスについては、「[スレッド処理オブジェクトと機能](threading-objects-and-features.md)」と「[同期プリミティブの概要](overview-of-synchronization-primitives.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f1202-104">For information on classes that provide additional features, see [Threading Objects and Features](threading-objects-and-features.md) and [Overview of Synchronization Primitives](overview-of-synchronization-primitives.md).</span></span>  
  
 <span data-ttu-id="f1202-105">このセクションの残りのトピックには、マネージド スレッド処理と Windows オペレーティング システムとの相互作用など、高度なトピックが含まれます。</span><span class="sxs-lookup"><span data-stu-id="f1202-105">The rest of the topics in this section cover advanced topics, including the interaction of managed threading with the Windows operating system.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f1202-106">.NET Framework 4 では、タスク並列ライブラリと PLINQ によって、マルチスレッド プログラムでのタスクとデータの並列処理のための API が提供されます。</span><span class="sxs-lookup"><span data-stu-id="f1202-106">In the .NET Framework 4, the Task Parallel Library and PLINQ provide APIs for task and data parallelism in multi-threaded programs.</span></span> <span data-ttu-id="f1202-107">詳細については、「[並列プログラミング](../parallel-programming/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f1202-107">For more information, see [Parallel Programming](../parallel-programming/index.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f1202-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="f1202-108">In this section</span></span>

 [<span data-ttu-id="f1202-109">スレッドおよびスレッド処理</span><span class="sxs-lookup"><span data-stu-id="f1202-109">Threads and Threading</span></span>](threads-and-threading.md)  
 <span data-ttu-id="f1202-110">複数のスレッドの利点と欠点について説明し、スレッドを作成またはスレッド プール スレッドを使用する可能性のあるシナリオの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="f1202-110">Discusses the advantages and drawbacks of multiple threads, and outlines the scenarios in which you might create threads or use thread pool threads.</span></span>  
  
 [<span data-ttu-id="f1202-111">マネージド スレッドの例外</span><span class="sxs-lookup"><span data-stu-id="f1202-111">Exceptions in Managed Threads</span></span>](exceptions-in-managed-threads.md)  
 <span data-ttu-id="f1202-112">さまざまなバージョンの .NET Framework のスレッドでのハンドルされていない例外の動作、特に、アプリケーションの終了の原因となる状況について説明します。</span><span class="sxs-lookup"><span data-stu-id="f1202-112">Describes the behavior of unhandled exceptions in threads for different versions of the .NET Framework, in particular the situations in which they result in termination of the application.</span></span>  
  
 [<span data-ttu-id="f1202-113">マルチスレッド処理のためのデータの同期</span><span class="sxs-lookup"><span data-stu-id="f1202-113">Synchronizing Data for Multithreading</span></span>](synchronizing-data-for-multithreading.md)  
 <span data-ttu-id="f1202-114">複数のスレッドで使用されるクラスのデータを同期する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f1202-114">Describes strategies for synchronizing data in classes that will be used with multiple threads.</span></span>  
  
 [<span data-ttu-id="f1202-115">フォアグラウンド スレッドとバックグラウンド スレッド</span><span class="sxs-lookup"><span data-stu-id="f1202-115">Foreground and Background Threads</span></span>](foreground-and-background-threads.md)  
 <span data-ttu-id="f1202-116">フォアグラウンド スレッドとバック グラウンド スレッドの違いについて説明します。</span><span class="sxs-lookup"><span data-stu-id="f1202-116">Explains the differences between foreground and background threads.</span></span>  
  
 [<span data-ttu-id="f1202-117">Windows でのマネージド スレッド処理とアンマネージド スレッド処理</span><span class="sxs-lookup"><span data-stu-id="f1202-117">Managed and Unmanaged Threading in Windows</span></span>](managed-and-unmanaged-threading-in-windows.md)  
 <span data-ttu-id="f1202-118">マネージド スレッド処理とアンマネージド スレッド処理の関係について説明し、Windows のスレッド処理 API に相当するマネージド API をリストし、COM アパートメントとマネージド スレッドの相互作用について説明します。</span><span class="sxs-lookup"><span data-stu-id="f1202-118">Discusses the relationship between managed and unmanaged threading, lists managed equivalents for Windows threading APIs, and discusses the interaction of COM apartments and managed threads.</span></span>  
  
 [<span data-ttu-id="f1202-119">スレッド ローカル ストレージ: スレッド相対静的フィールドとデータ スロット</span><span class="sxs-lookup"><span data-stu-id="f1202-119">Thread Local Storage: Thread-Relative Static Fields and Data Slots</span></span>](thread-local-storage-thread-relative-static-fields-and-data-slots.md)  
 <span data-ttu-id="f1202-120">スレッド相対ストレージ メカニズムについて説明します。</span><span class="sxs-lookup"><span data-stu-id="f1202-120">Describes thread-relative storage mechanisms.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="f1202-121">リファレンス</span><span class="sxs-lookup"><span data-stu-id="f1202-121">Reference</span></span>

 <xref:System.Threading.Thread>  
 <span data-ttu-id="f1202-122">**Thread** クラスのリファレンス ドキュメントです。このクラスは、アンマネージド コードから作成されたか、マネージド アプリケーションで作成されたかにかかわらず、マネージド スレッドを表します。</span><span class="sxs-lookup"><span data-stu-id="f1202-122">Provides reference documentation for the **Thread** class, which represents a managed thread, whether it came from unmanaged code or was created in a managed application.</span></span>  
  
 <xref:System.ComponentModel.BackgroundWorker>  
 <span data-ttu-id="f1202-123">ユーザー インターフェイス オブジェクトと共にマルチスレッドを実装するための安全な方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="f1202-123">Provides a safe way to implement multithreading in conjunction with user-interface objects.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="f1202-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="f1202-124">Related sections</span></span>

 [<span data-ttu-id="f1202-125">同期プリミティブの概要</span><span class="sxs-lookup"><span data-stu-id="f1202-125">Overview of Synchronization Primitives</span></span>](overview-of-synchronization-primitives.md)  
 <span data-ttu-id="f1202-126">複数のスレッドのアクティビティを同期するために使用されるマネージド クラスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="f1202-126">Describes the managed classes used to synchronize the activities of multiple threads.</span></span>  
  
 [<span data-ttu-id="f1202-127">マネージド スレッド処理の実施</span><span class="sxs-lookup"><span data-stu-id="f1202-127">Managed Threading Best Practices</span></span>](managed-threading-best-practices.md)  
 <span data-ttu-id="f1202-128">マルチスレッドに関する一般的な問題と、問題を回避するための方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f1202-128">Describes common problems with multithreading and strategies for avoiding problems.</span></span>  
  
 [<span data-ttu-id="f1202-129">並列プログラミング</span><span class="sxs-lookup"><span data-stu-id="f1202-129">Parallel Programming</span></span>](../parallel-programming/index.md)  
 <span data-ttu-id="f1202-130">非同期およびマルチスレッドの .NET Framework アプリケーションを作成する作業を大幅に簡素化する、タスク並列ライブラリと PLINQ について説明します。</span><span class="sxs-lookup"><span data-stu-id="f1202-130">Describes the Task Parallel Library and PLINQ, which greatly simplify the work of creating asynchronous and multi-threaded .NET Framework applications.</span></span>
