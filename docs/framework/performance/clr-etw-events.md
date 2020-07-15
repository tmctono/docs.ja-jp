---
title: CLR ETW イベント
description: 共通言語ランタイム (CLR) event tracing for Windows (ETW) イベントに関する記事を参照してください。 イベントプロバイダーには、ランタイムプロバイダーとランダウンプロバイダーの2つがあります。
ms.date: 03/30/2017
helpviewer_keywords:
- CLR ETW events
- ETW, common language runtime
- ETW, CLR events
ms.assetid: ef2b31c3-7426-43e7-9924-92339b96556d
ms.openlocfilehash: 22a2f027462d67d5a933972a7420c5f0e38353e5
ms.sourcegitcommit: 0fa2b7b658bf137e813a7f4d09589d64c148ebf5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/14/2020
ms.locfileid: "86309834"
---
# <a name="clr-etw-events"></a><span data-ttu-id="d1783-104">CLR ETW イベント</span><span class="sxs-lookup"><span data-stu-id="d1783-104">CLR ETW Events</span></span>
<span data-ttu-id="d1783-105">このセクションのトピックでは、Windows イベント トレーシング (ETW) イベントについて説明します。</span><span class="sxs-lookup"><span data-stu-id="d1783-105">The topics in this section describe event tracing for Windows (ETW) events.</span></span> <span data-ttu-id="d1783-106">各イベントは、キーワードとレベルに関連付けられています。詳細については、「[CLR ETW のキーワードとレベル](clr-etw-keywords-and-levels.md)」トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1783-106">Each event has an associated keyword and level, which are described in the [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md) topic.</span></span> <span data-ttu-id="d1783-107">CLR には、イベントのプロバイダーが 2 つあります。</span><span class="sxs-lookup"><span data-stu-id="d1783-107">The CLR has two providers for the events:</span></span>  
  
- <span data-ttu-id="d1783-108">ランタイム プロバイダー。有効になっているキーワードに応じてイベントを発生させます (キーワードとはイベントのカテゴリです)。</span><span class="sxs-lookup"><span data-stu-id="d1783-108">The runtime provider, which raises events depending on which keywords (categories of events) are enabled.</span></span> <span data-ttu-id="d1783-109">CLR ランタイム プロバイダーの GUID は e13c0d23-ccbc-4e12-931b-d9cc2eee27e4 です。</span><span class="sxs-lookup"><span data-stu-id="d1783-109">The CLR runtime provider GUID is e13c0d23-ccbc-4e12-931b-d9cc2eee27e4.</span></span>  
  
- <span data-ttu-id="d1783-110">ランダウン プロバイダー。特殊な用途があります。</span><span class="sxs-lookup"><span data-stu-id="d1783-110">The rundown provider, which has special-purpose uses.</span></span> <span data-ttu-id="d1783-111">CLR ランダウン プロバイダーの GUID は a669021c-c450-4609-a035-5af59af4df18 です。</span><span class="sxs-lookup"><span data-stu-id="d1783-111">The CLR rundown provider GUID is a669021c-c450-4609-a035-5af59af4df18.</span></span>  
  
 <span data-ttu-id="d1783-112">プロバイダーの詳細については、「[CLR ETW Providers](clr-etw-providers.md)」(CLR ETW プロバイダー) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1783-112">For more information about the providers, see [CLR ETW Providers](clr-etw-providers.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d1783-113">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="d1783-113">In This Section</span></span>  
 [<span data-ttu-id="d1783-114">ランタイム情報イベント</span><span class="sxs-lookup"><span data-stu-id="d1783-114">Runtime Information Events</span></span>](runtime-information-etw-events.md)  
 <span data-ttu-id="d1783-115">SKU、バージョン番号、アクティブ化の方法、起動時に使用されたコマンド ライン パラメーター、GUID (該当する場合) などのランタイムに関する情報をキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="d1783-115">Captures information about the runtime, including the SKU, version number, the manner in which the runtime was activated, the command-line parameters it was started with, the GUID (if applicable), and other relevant information.</span></span>  
  
 [<span data-ttu-id="d1783-116">Exception Thrown_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="d1783-116">Exception Thrown_V1 Event</span></span>](exception-thrown-v1-etw-event.md)  
 <span data-ttu-id="d1783-117">スローされる例外に関する情報をキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="d1783-117">Captures information about exceptions that are thrown.</span></span>  
  
 [<span data-ttu-id="d1783-118">競合イベント</span><span class="sxs-lookup"><span data-stu-id="d1783-118">Contention Events</span></span>](contention-etw-events.md)  
 <span data-ttu-id="d1783-119">ランタイムが使用するモニター ロックまたはネイティブ ロックの競合に関する情報をキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="d1783-119">Captures information about contention for monitor locks or native locks that the runtime uses.</span></span>  
  
 [<span data-ttu-id="d1783-120">スレッド プール イベント</span><span class="sxs-lookup"><span data-stu-id="d1783-120">Thread Pool Events</span></span>](thread-pool-etw-events.md)  
 <span data-ttu-id="d1783-121">ワーカー スレッド プールと I/O スレッド プールに関する情報をキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="d1783-121">Captures information about worker thread pools and I/O thread pools.</span></span>  
  
 [<span data-ttu-id="d1783-122">ローダー イベント</span><span class="sxs-lookup"><span data-stu-id="d1783-122">Loader Events</span></span>](loader-etw-events.md)  
 <span data-ttu-id="d1783-123">アプリケーションのドメイン、アセンブリ、およびモジュールのロードとアンロードに関連する情報をキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="d1783-123">Captures information about loading and unloading application domains, assemblies, and modules.</span></span>  
  
 [<span data-ttu-id="d1783-124">メソッド イベント</span><span class="sxs-lookup"><span data-stu-id="d1783-124">Method Events</span></span>](method-etw-events.md)  
 <span data-ttu-id="d1783-125">CLR メソッド シンボルの解決に関する情報をキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="d1783-125">Captures information about CLR methods for symbol resolution.</span></span>  
  
 [<span data-ttu-id="d1783-126">ガベージ コレクション イベント</span><span class="sxs-lookup"><span data-stu-id="d1783-126">Garbage Collection Events</span></span>](garbage-collection-etw-events.md)  
 <span data-ttu-id="d1783-127">診断とデバッグに役立つガベージ コレクションに関する情報をキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="d1783-127">Captures information pertaining to garbage collection, to help in diagnostics and debugging.</span></span>  
  
 [<span data-ttu-id="d1783-128">JIT トレース イベント</span><span class="sxs-lookup"><span data-stu-id="d1783-128">JIT Tracing Events</span></span>](jit-tracing-etw-events.md)  
 <span data-ttu-id="d1783-129">Just-In-Time (JIT) インライン展開と末尾呼び出しに関する情報をキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="d1783-129">Captures information about just-in-time (JIT) inlining and tail calls.</span></span>  
  
 [<span data-ttu-id="d1783-130">相互運用イベント</span><span class="sxs-lookup"><span data-stu-id="d1783-130">Interop Events</span></span>](interop-etw-events.md)  
 <span data-ttu-id="d1783-131">Microsoft intermediate language (MSIL) のスタブ生成とキャッシュに関する情報をキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="d1783-131">Captures information about Microsoft intermediate language (MSIL) stub generation and caching.</span></span>  
  
 [<span data-ttu-id="d1783-132">ARM のイベント</span><span class="sxs-lookup"><span data-stu-id="d1783-132">ARM Events</span></span>](application-domain-resource-monitoring-arm-etw-events.md)  
 <span data-ttu-id="d1783-133">アプリケーション ドメインの状態に関する詳細な診断情報をキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="d1783-133">Captures detailed diagnostic information about the state of an application domain.</span></span>  
  
 [<span data-ttu-id="d1783-134">セキュリティイベント</span><span class="sxs-lookup"><span data-stu-id="d1783-134">Security Events</span></span>](security-etw-events.md)  
 <span data-ttu-id="d1783-135">厳密な名前と Authenticode の検証に関する情報をキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="d1783-135">Captures information about strong name and Authenticode verification.</span></span>  
  
 [<span data-ttu-id="d1783-136">スタック イベント</span><span class="sxs-lookup"><span data-stu-id="d1783-136">Stack Event</span></span>](stack-etw-event.md)  
 <span data-ttu-id="d1783-137">イベントが発生した後に、他のイベントでスタック トレースの生成に使用された情報をキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="d1783-137">Captures information that is used with other events to generate stack traces after an event is raised.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1783-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="d1783-138">See also</span></span>

- [<span data-ttu-id="d1783-139">ETW によりデバッグおよびパフォーマンス調整を改善する</span><span class="sxs-lookup"><span data-stu-id="d1783-139">Improve Debugging And Performance Tuning With ETW</span></span>](https://docs.microsoft.com/archive/msdn-magazine/2007/april/event-tracing-improve-debugging-and-performance-tuning-with-etw)
- [<span data-ttu-id="d1783-140">.NET Framework のログ記録の制御</span><span class="sxs-lookup"><span data-stu-id="d1783-140">Controlling .NET Framework Logging</span></span>](controlling-logging.md)
- [<span data-ttu-id="d1783-141">CLR ETW プロバイダー</span><span class="sxs-lookup"><span data-stu-id="d1783-141">CLR ETW Providers</span></span>](clr-etw-providers.md)
- [<span data-ttu-id="d1783-142">CLR ETW キーワードおよびレベル</span><span class="sxs-lookup"><span data-stu-id="d1783-142">CLR ETW Keywords and Levels</span></span>](clr-etw-keywords-and-levels.md)
- [<span data-ttu-id="d1783-143">共通言語ランタイムの ETW イベント</span><span class="sxs-lookup"><span data-stu-id="d1783-143">ETW Events in the Common Language Runtime</span></span>](etw-events-in-the-common-language-runtime.md)
