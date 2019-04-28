---
title: ICorDebugManagedCallback2::MDANotification メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.MDANotification
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::MDANotification
helpviewer_keywords:
- MDANotification method [.NET Framework debugging]
- ICorDebugManagedCallback2::MDANotification method [.NET Framework debugging]
ms.assetid: 93f79627-bd31-4f4f-b95d-46a032a52fe4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 425c606b1f340bbd49cfe3497d394d5ad0dd37a9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61763803"
---
# <a name="icordebugmanagedcallback2mdanotification-method"></a><span data-ttu-id="17759-102">ICorDebugManagedCallback2::MDANotification メソッド</span><span class="sxs-lookup"><span data-stu-id="17759-102">ICorDebugManagedCallback2::MDANotification Method</span></span>
<span data-ttu-id="17759-103">コードが実行されるには、デバッグ中のアプリケーションでマネージ デバッグ アシスタント (MDA) が発生した通知を提供します。</span><span class="sxs-lookup"><span data-stu-id="17759-103">Provides notification that code execution has encountered a managed debugging assistant (MDA) in the application that is being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17759-104">構文</span><span class="sxs-lookup"><span data-stu-id="17759-104">Syntax</span></span>  
  
```  
HRESULT MDANotification(  
    [in] ICorDebugController  *pController,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugMDA         *pMDA  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="17759-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="17759-105">Parameters</span></span>  
 `pController`  
 <span data-ttu-id="17759-106">[in]プロセスを公開する ICorDebugController インターフェイスまたは MDA が発生したアプリケーション ドメインへのポインター。</span><span class="sxs-lookup"><span data-stu-id="17759-106">[in] A pointer to an ICorDebugController interface that exposes the process or application domain in which the MDA occurred.</span></span>  
  
 <span data-ttu-id="17759-107">デバッガーは、コント ローラーは、プロセスまたはアプリケーション ドメインでは、かどうかについてどのような想定をしないでを決定するインターフェイスを常に照会できることですが。</span><span class="sxs-lookup"><span data-stu-id="17759-107">A debugger should not make any assumptions about whether the controller is a process or an application domain, although it can always query the interface to make a determination.</span></span>  
  
 `pThread`  
 <span data-ttu-id="17759-108">[in]デバッグ イベントが発生したマネージ スレッドを公開する ICorDebugThread インターフェイスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="17759-108">[in] A pointer to an ICorDebugThread interface that exposes the managed thread on which the debug event occurred.</span></span>  
  
 <span data-ttu-id="17759-109">MDA は、アンマネージで発生した場合のスレッドの値`pThread`は null になります。</span><span class="sxs-lookup"><span data-stu-id="17759-109">If the MDA occurred on an unmanaged thread, the value of `pThread` will be null.</span></span>  
  
 <span data-ttu-id="17759-110">MDA オブジェクト自体からは、オペレーティング システム (OS) のスレッド ID を取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="17759-110">You must get the operating system (OS) thread ID from the MDA object itself.</span></span>  
  
 `pMDA`  
 <span data-ttu-id="17759-111">[in]ポインター、 [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md) MDA 情報を公開するインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="17759-111">[in] A pointer to an [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md) interface that exposes the MDA information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="17759-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="17759-112">Remarks</span></span>  
 <span data-ttu-id="17759-113">MDA はヒューリスティック警告であり、呼び出し元を除く任意の明示的なデバッガー操作が必要としない[icordebugcontroller::continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md)がデバッグされているアプリケーションの実行を再開します。</span><span class="sxs-lookup"><span data-stu-id="17759-113">An MDA is a heuristic warning and does not require any explicit debugger action except for calling [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) to resume execution of the application that is being debugged.</span></span>  
  
 <span data-ttu-id="17759-114">Mda が起動され、特定の MDA 任意の時点でのデータは、共通言語ランタイム (CLR) を確認できます。</span><span class="sxs-lookup"><span data-stu-id="17759-114">The common language runtime (CLR) can determine which MDAs are fired and which data is in any given MDA at any point.</span></span> <span data-ttu-id="17759-115">そのため、デバッガーは特定の MDA パターンを必要とするすべての機能をビルドする必要があります。</span><span class="sxs-lookup"><span data-stu-id="17759-115">Therefore, debuggers should not build any functionality requiring specific MDA patterns.</span></span>  
  
 <span data-ttu-id="17759-116">Mda は、キューに MDA が発生した直後後に発生した可能性があります。</span><span class="sxs-lookup"><span data-stu-id="17759-116">MDAs may be queued and fired shortly after the MDA is encountered.</span></span> <span data-ttu-id="17759-117">これは、ランタイムがそれを見つけたときに MDA を発生させるのではなく、MDA を発生させるためのセーフ ポイントに到達するまで待機する必要がある場合に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="17759-117">This could happen if the runtime needs to wait until it reaches a safe point for firing the MDA, instead of firing the MDA when it encounters it.</span></span> <span data-ttu-id="17759-118">また、ランタイムは、Mda のキューに置かれたコールバック (「添付」イベントの操作に似ています) の 1 組の数で発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="17759-118">It also means that the runtime may fire a number of MDAs in a single set of queued callbacks (similar to an "attach" event operation).</span></span>  
  
 <span data-ttu-id="17759-119">デバッガーへの参照を解放する必要があります、`ICorDebugMDA`インスタンスから取得した直後に、`MDANotification`コールバック、MDA によって消費されるメモリのリサイクル、CLR を許可します。</span><span class="sxs-lookup"><span data-stu-id="17759-119">A debugger should release the reference to an `ICorDebugMDA` instance immediately after returning from the `MDANotification` callback, to allow the CLR to recycle the memory consumed by an MDA.</span></span> <span data-ttu-id="17759-120">インスタンスを解放すると、多数の Mda が発生している場合にパフォーマンスが向上する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="17759-120">Releasing the instance may improve performance if many MDAs are firing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="17759-121">必要条件</span><span class="sxs-lookup"><span data-stu-id="17759-121">Requirements</span></span>  
 <span data-ttu-id="17759-122">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="17759-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="17759-123">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="17759-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="17759-124">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="17759-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="17759-125">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="17759-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17759-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="17759-126">See also</span></span>

- [<span data-ttu-id="17759-127">マネージド デバッグ アシスタントによるエラーの診断</span><span class="sxs-lookup"><span data-stu-id="17759-127">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="17759-128">ICorDebugManagedCallback2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="17759-128">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="17759-129">ICorDebugManagedCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="17759-129">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
