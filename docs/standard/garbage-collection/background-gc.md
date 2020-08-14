---
title: バックグラウンド ガベージ コレクション
description: .NET のバックグラウンド ガベージ コレクションについて、およびワークステーションとサーバーのガベージ コレクションの違いについて説明します。
ms.date: 04/21/2020
helpviewer_keywords:
- garbage collection, background
- background garbage collection
ms.openlocfilehash: bf88c14b2aeed94a548b6116749fa8669576afe1
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2020
ms.locfileid: "87916998"
---
# <a name="background-garbage-collection"></a><span data-ttu-id="1ec45-103">バックグラウンド ガベージ コレクション</span><span class="sxs-lookup"><span data-stu-id="1ec45-103">Background garbage collection</span></span>

<span data-ttu-id="1ec45-104">バックグラウンド ガベージ コレクション (GC) では、ジェネレーション 2 のコレクションの実行中に、必要に応じて短期ジェネレーション (0 および 1) のコレクションが行われます。</span><span class="sxs-lookup"><span data-stu-id="1ec45-104">In background garbage collection (GC), ephemeral generations (0 and 1) are collected as needed while the collection of generation 2 is in progress.</span></span> <span data-ttu-id="1ec45-105">バックグラウンド ガベージ コレクションは、バックグラウンド GC かサーバー GC かによって 1 つまたは複数の専用スレッドで実行され、ジェネレーション 2 のコレクションにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="1ec45-105">Background garbage collection is performed on one or more dedicated threads, depending on whether it's background or server GC, and applies only to generation 2 collections.</span></span>

<span data-ttu-id="1ec45-106">バックグラウンド ガベージ コレクションは既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="1ec45-106">Background garbage collection is enabled by default.</span></span> <span data-ttu-id="1ec45-107">これは、.NET Framework アプリの [gcConcurrent](../../framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) 構成設定または .NET Core と .NET 5 以降のアプリの [System.GC.Concurrent](../../core/run-time-config/garbage-collector.md#background-gc) 設定で有効または無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="1ec45-107">It can be enabled or disabled with the [gcConcurrent](../../framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) configuration setting in .NET Framework apps or the [System.GC.Concurrent](../../core/run-time-config/garbage-collector.md#background-gc) setting in .NET Core and .NET 5 and later apps.</span></span>

> [!NOTE]
> <span data-ttu-id="1ec45-108">[バックグラウンド ガベージ コレクション](#concurrent-garbage-collection)は同時実行ガベージ コレクションに取って代わり、.NET Framework 4 以降で利用できます。</span><span class="sxs-lookup"><span data-stu-id="1ec45-108">Background garbage collection replaces [concurrent garbage collection](#concurrent-garbage-collection) and is available in .NET Framework 4 and later versions.</span></span> <span data-ttu-id="1ec45-109">.NET Framework 4 では、"*ワークステーション*" ガベージ コレクションのみでサポートされます。</span><span class="sxs-lookup"><span data-stu-id="1ec45-109">In .NET Framework 4, it's supported only for *workstation* garbage collection.</span></span> <span data-ttu-id="1ec45-110">.NET Framework 4.5 以降では、バックグラウンド ガベージ コレクションは、"*ワークステーション*" と "*サーバー*" の両方のガベージ コレクションで使用できます。</span><span class="sxs-lookup"><span data-stu-id="1ec45-110">Starting with .NET Framework 4.5, background garbage collection is available for both *workstation* and *server* garbage collection.</span></span>

<span data-ttu-id="1ec45-111">バックグラウンド ガベージ コレクションの実行中に行われる短期ジェネレーションに対するコレクションのことを、"*フォアグラウンド*" ガベージ コレクションと呼びます。</span><span class="sxs-lookup"><span data-stu-id="1ec45-111">A collection on ephemeral generations during background garbage collection is known as *foreground* garbage collection.</span></span> <span data-ttu-id="1ec45-112">フォアグラウンド ガベージ コレクションが発生すると、マネージド スレッドはすべて中断されます。</span><span class="sxs-lookup"><span data-stu-id="1ec45-112">When foreground garbage collections occur, all managed threads are suspended.</span></span>

<span data-ttu-id="1ec45-113">バックグラウンド ガベージ コレクションの実行中にジェネレーション 0 に十分なオブジェクトが割り当てられていれば、CLR はジェネレーション 0 またはジェネレーション 1 のフォアグラウンド ガベージ コレクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="1ec45-113">When background garbage collection is in progress and you've allocated enough objects in generation 0, the CLR performs a generation 0 or generation 1 foreground garbage collection.</span></span> <span data-ttu-id="1ec45-114">バックグラウンド ガベージ コレクションの専用スレッドは、フォアグラウンド ガベージ コレクションの要求がないかどうかをセーフ ポイントで頻繁に確認します。</span><span class="sxs-lookup"><span data-stu-id="1ec45-114">The dedicated background garbage collection thread checks at frequent safe points to determine whether there is a request for foreground garbage collection.</span></span> <span data-ttu-id="1ec45-115">要求があると、バックグラウンド コレクションを中断して、フォアグラウンド ガベージ コレクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="1ec45-115">If there is, the background collection suspends itself so that foreground garbage collection can occur.</span></span> <span data-ttu-id="1ec45-116">フォアグラウンド ガベージ コレクションが完了すると、バックグラウンド ガベージ コレクションの専用スレッドとユーザー スレッドが再開されます。</span><span class="sxs-lookup"><span data-stu-id="1ec45-116">After the foreground garbage collection is completed, the dedicated background garbage collection threads and user threads resume.</span></span>

<span data-ttu-id="1ec45-117">バックグラウンド ガベージ コレクションでは、バックグラウンド ガベージ コレクションの実行中に短期ガベージ コレクションが発生する可能性があるため、同時実行ガベージ コレクションによる割り当ての制限が解除されます。</span><span class="sxs-lookup"><span data-stu-id="1ec45-117">Background garbage collection removes allocation restrictions imposed by concurrent garbage collection, because ephemeral garbage collections can occur during background garbage collection.</span></span> <span data-ttu-id="1ec45-118">バックグラウンド ガベージ コレクションでは、短期ジェネレーションの使用されなくなったオブジェクトを削除できます。</span><span class="sxs-lookup"><span data-stu-id="1ec45-118">Background garbage collection can remove dead objects in ephemeral generations.</span></span> <span data-ttu-id="1ec45-119">ジェネレーション 1 ガベージ コレクション中に必要になった場合、ヒープを拡張することもできます。</span><span class="sxs-lookup"><span data-stu-id="1ec45-119">It can also expand the heap if needed during a generation 1 garbage collection.</span></span>

## <a name="background-workstation-vs-server-gc"></a><span data-ttu-id="1ec45-120">バックグラウンドのワークステーションとサーバーの GC</span><span class="sxs-lookup"><span data-stu-id="1ec45-120">Background workstation vs. server GC</span></span>

<span data-ttu-id="1ec45-121">.NET Framework 4.5 以降では、バックグラウンド ガベージ コレクションは、サーバー GC で使用できます。</span><span class="sxs-lookup"><span data-stu-id="1ec45-121">Starting with .NET Framework 4.5, background garbage collection is available for server GC.</span></span> <span data-ttu-id="1ec45-122">バックグラウンド GC は、サーバー ガベージ コレクションの既定のモードです。</span><span class="sxs-lookup"><span data-stu-id="1ec45-122">Background GC is the default mode for server garbage collection.</span></span>

<span data-ttu-id="1ec45-123">サーバーのバックグラウンド ガベージ コレクションは、ワークステーションのバックグラウンド ガベージ コレクションと同様に機能しますが、いくつかの違いがあります。</span><span class="sxs-lookup"><span data-stu-id="1ec45-123">Background server garbage collection functions similarly to background workstation garbage collection, but there are a few differences:</span></span>

- <span data-ttu-id="1ec45-124">ワークステーションのバックグラウンド ガベージ コレクションでは専用のバックグラウンド ガベージ コレクション スレッドを 1 つ使用します。これに対して、サーバーのバックグラウンド ガベージ コレクションでは複数のスレッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="1ec45-124">Background workstation garbage collection uses one dedicated background garbage collection thread, whereas background server garbage collection uses multiple threads.</span></span> <span data-ttu-id="1ec45-125">通常、論理プロセッサごとに専用のスレッドが使用されます。</span><span class="sxs-lookup"><span data-stu-id="1ec45-125">Typically, there's a dedicated thread for each logical processor.</span></span>

- <span data-ttu-id="1ec45-126">ワークステーションのバックグラウンド ガベージ コレクション スレッドとは異なり、サーバーのバックグラウンド GC スレッドはタイムアウトになりません。</span><span class="sxs-lookup"><span data-stu-id="1ec45-126">Unlike the workstation background garbage collection thread, the background server GC threads do not time out.</span></span>

<span data-ttu-id="1ec45-127">次の図は、別々の専用スレッドで実行される "*ワークステーション*" のバックグラウンド ガベージ コレクションを示しています。</span><span class="sxs-lookup"><span data-stu-id="1ec45-127">The following illustration shows background *workstation* garbage collection performed on a separate, dedicated thread:</span></span>

![バックグラウンド ワークステーション ガベージ コレクション](media/fundamentals/background-workstation-garbage-collection.png)

<span data-ttu-id="1ec45-129">次の図は、別々の専用スレッドで実行される "*サーバー*" のバックグラウンド ガベージ コレクションを示しています。</span><span class="sxs-lookup"><span data-stu-id="1ec45-129">The following illustration shows background *server* garbage collection performed on separate, dedicated threads:</span></span>

![バックグラウンド サーバー ガベージ コレクション](media/fundamentals/background-server-garbage-collection.png)

## <a name="concurrent-garbage-collection"></a><span data-ttu-id="1ec45-131">同時実行ガベージ コレクション</span><span class="sxs-lookup"><span data-stu-id="1ec45-131">Concurrent garbage collection</span></span>

> [!TIP]
> <span data-ttu-id="1ec45-132">このセクションは次に適用されます。</span><span class="sxs-lookup"><span data-stu-id="1ec45-132">This section applies to:</span></span>
>
> - <span data-ttu-id="1ec45-133">ワークステーション ガベージ コレクションの .NET Framework 3.5 以前</span><span class="sxs-lookup"><span data-stu-id="1ec45-133">.NET Framework 3.5 and earlier for workstation garbage collection</span></span>
> - <span data-ttu-id="1ec45-134">サーバー ガベージ コレクションの .NET Framework 4 以前</span><span class="sxs-lookup"><span data-stu-id="1ec45-134">.NET Framework 4 and earlier for server garbage collection</span></span>
>
> <span data-ttu-id="1ec45-135">後のバージョンでは、バックグラウンド ガベージ コレクションが同時実行ガベージに取って代わります。</span><span class="sxs-lookup"><span data-stu-id="1ec45-135">Concurrent garbage is replaced by background garbage collection in later versions.</span></span>

<span data-ttu-id="1ec45-136">ワークステーションまたはサーバーのガベージ コレクションでは、[同時実行ガベージ コレクションを有効にする](../../framework/configure-apps/file-schema/runtime/gcconcurrent-element.md)ことで、複数のスレッドを同時に実行できます。同時実行ガベージ コレクションでは、コレクションの実行中は、ほとんどの場合、ガベージ コレクションの処理を行う専用のスレッドが使用されます。</span><span class="sxs-lookup"><span data-stu-id="1ec45-136">In workstation or server garbage collection, you can [enable concurrent garbage collection](../../framework/configure-apps/file-schema/runtime/gcconcurrent-element.md), which enables threads to run concurrently with a dedicated thread that performs the garbage collection for most of the duration of the collection.</span></span> <span data-ttu-id="1ec45-137">このオプションは、ジェネレーション 2 のガベージ コレクションにのみ影響します。ジェネレーション 0 と 1 の処理はすぐに終了するため、常に非同時実行で行われます。</span><span class="sxs-lookup"><span data-stu-id="1ec45-137">This option affects only garbage collections in generation 2; generations 0 and 1 are always non-concurrent because they finish fast.</span></span>

<span data-ttu-id="1ec45-138">同時実行ガベージ コレクションでは、コレクションの一時停止を最小限にすることで、インタラクティブ アプリケーションの応答性を高めることができます。</span><span class="sxs-lookup"><span data-stu-id="1ec45-138">Concurrent garbage collection enables interactive applications to be more responsive by minimizing pauses for a collection.</span></span> <span data-ttu-id="1ec45-139">マネージド スレッドは、同時実行ガベージ コレクションのスレッドが実行されている間も、ほぼ常に処理を続けることができます。</span><span class="sxs-lookup"><span data-stu-id="1ec45-139">Managed threads can continue to run most of the time while the concurrent garbage collection thread is running.</span></span> <span data-ttu-id="1ec45-140">このデザインでは、ガベージ コレクションを実行している間は一時停止が短くなります。</span><span class="sxs-lookup"><span data-stu-id="1ec45-140">This design results in shorter pauses while a garbage collection is occurring.</span></span>

<span data-ttu-id="1ec45-141">同時実行ガベージ コレクションは、専用のスレッドで実行されます。</span><span class="sxs-lookup"><span data-stu-id="1ec45-141">Concurrent garbage collection is performed on a dedicated thread.</span></span> <span data-ttu-id="1ec45-142">既定では、CLR は、シングルプロセッサとマルチプロセッサの両方のコンピューターで、同時実行ガベージ コレクションを有効にして、ワークステーションのガベージ コレクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="1ec45-142">By default, the CLR runs workstation garbage collection with concurrent garbage collection enabled on both single-processor and multi-processor computers.</span></span>

<span data-ttu-id="1ec45-143">次の図は、別々の専用のスレッドで実行される同時実行ガベージ コレクションを示しています。</span><span class="sxs-lookup"><span data-stu-id="1ec45-143">The following illustration shows concurrent garbage collection performed on a separate dedicated thread.</span></span>

![同時実行ガベージ コレクションのスレッド](media/gc-concurrent.png)

## <a name="see-also"></a><span data-ttu-id="1ec45-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="1ec45-145">See also</span></span>

- [<span data-ttu-id="1ec45-146">ワークステーションとサーバーのガベージ コレクション</span><span class="sxs-lookup"><span data-stu-id="1ec45-146">Workstation and server garbage collection</span></span>](workstation-server-gc.md)
- [<span data-ttu-id="1ec45-147">ガベージ コレクションの実行時構成オプション</span><span class="sxs-lookup"><span data-stu-id="1ec45-147">Run-time configuration options for garbage collection</span></span>](../../core/run-time-config/garbage-collector.md)
