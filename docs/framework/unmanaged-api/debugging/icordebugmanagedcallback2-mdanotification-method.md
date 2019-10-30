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
ms.openlocfilehash: ab3819d5c33f090fda1ca9c3dccb5d08ab8f84cc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131460"
---
# <a name="icordebugmanagedcallback2mdanotification-method"></a><span data-ttu-id="5c356-102">ICorDebugManagedCallback2::MDANotification メソッド</span><span class="sxs-lookup"><span data-stu-id="5c356-102">ICorDebugManagedCallback2::MDANotification Method</span></span>
<span data-ttu-id="5c356-103">コード実行で、デバッグ中のアプリケーションでマネージデバッグアシスタント (MDA) が検出されたことを通知します。</span><span class="sxs-lookup"><span data-stu-id="5c356-103">Provides notification that code execution has encountered a managed debugging assistant (MDA) in the application that is being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c356-104">構文</span><span class="sxs-lookup"><span data-stu-id="5c356-104">Syntax</span></span>  
  
```cpp  
HRESULT MDANotification(  
    [in] ICorDebugController  *pController,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugMDA         *pMDA  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5c356-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5c356-105">Parameters</span></span>  
 `pController`  
 <span data-ttu-id="5c356-106">からMDA が発生したプロセスまたはアプリケーションドメインを公開する、表示コントローラーインターフェイスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="5c356-106">[in] A pointer to an ICorDebugController interface that exposes the process or application domain in which the MDA occurred.</span></span>  
  
 <span data-ttu-id="5c356-107">デバッガーでは、コントローラーがプロセスとアプリケーションドメインのどちらであるかについては想定しませんが、常にインターフェイスを照会して決定を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="5c356-107">A debugger should not make any assumptions about whether the controller is a process or an application domain, although it can always query the interface to make a determination.</span></span>  
  
 `pThread`  
 <span data-ttu-id="5c356-108">からデバッグイベントが発生したマネージスレッドを公開する、コードスレッドインターフェイスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="5c356-108">[in] A pointer to an ICorDebugThread interface that exposes the managed thread on which the debug event occurred.</span></span>  
  
 <span data-ttu-id="5c356-109">アンマネージスレッドで MDA が発生した場合、`pThread` の値は null になります。</span><span class="sxs-lookup"><span data-stu-id="5c356-109">If the MDA occurred on an unmanaged thread, the value of `pThread` will be null.</span></span>  
  
 <span data-ttu-id="5c356-110">MDA オブジェクト自体からオペレーティングシステム (OS) のスレッド ID を取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c356-110">You must get the operating system (OS) thread ID from the MDA object itself.</span></span>  
  
 `pMDA`  
 <span data-ttu-id="5c356-111">からMDA 情報を公開[する、ツールのインターフェイスへ](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)のポインター。</span><span class="sxs-lookup"><span data-stu-id="5c356-111">[in] A pointer to an [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md) interface that exposes the MDA information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5c356-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="5c356-112">Remarks</span></span>  
 <span data-ttu-id="5c356-113">MDA は、ヒューリスティック警告であり、[例外を明示的に呼び出す必要](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md)はありません。ただし、デバッグ中のアプリケーションの実行を再開する場合を除き、明示的なデバッガーアクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="5c356-113">An MDA is a heuristic warning and does not require any explicit debugger action except for calling [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) to resume execution of the application that is being debugged.</span></span>  
  
 <span data-ttu-id="5c356-114">共通言語ランタイム (CLR) は、どの Mda が発生したか、また任意の時点でどのデータが特定の MDA に存在するかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="5c356-114">The common language runtime (CLR) can determine which MDAs are fired and which data is in any given MDA at any point.</span></span> <span data-ttu-id="5c356-115">したがって、デバッガーでは、特定の MDA パターンを必要とする機能を構築しないでください。</span><span class="sxs-lookup"><span data-stu-id="5c356-115">Therefore, debuggers should not build any functionality requiring specific MDA patterns.</span></span>  
  
 <span data-ttu-id="5c356-116">Mda は、MDA が検出された直後にキューに入れられ、発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5c356-116">MDAs may be queued and fired shortly after the MDA is encountered.</span></span> <span data-ttu-id="5c356-117">これは、mda が発生したときに MDA を起動するのではなく、MDA を起動するためのセーフポイントに到達するまで、ランタイムが待機する必要がある場合に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5c356-117">This could happen if the runtime needs to wait until it reaches a safe point for firing the MDA, instead of firing the MDA when it encounters it.</span></span> <span data-ttu-id="5c356-118">また、ランタイムは、キューに置かれたコールバックの1つのセット ("attach" イベント操作に似ています) で多数の Mda を起動することもあります。</span><span class="sxs-lookup"><span data-stu-id="5c356-118">It also means that the runtime may fire a number of MDAs in a single set of queued callbacks (similar to an "attach" event operation).</span></span>  
  
 <span data-ttu-id="5c356-119">デバッガーは、`MDANotification` コールバックから戻った直後に `ICorDebugMDA` インスタンスへの参照を解放し、CLR が MDA によって消費されるメモリを再利用できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c356-119">A debugger should release the reference to an `ICorDebugMDA` instance immediately after returning from the `MDANotification` callback, to allow the CLR to recycle the memory consumed by an MDA.</span></span> <span data-ttu-id="5c356-120">多くの Mda が起動している場合、インスタンスを解放するとパフォーマンスが向上する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5c356-120">Releasing the instance may improve performance if many MDAs are firing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c356-121">［要件］</span><span class="sxs-lookup"><span data-stu-id="5c356-121">Requirements</span></span>  
 <span data-ttu-id="5c356-122">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c356-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c356-123">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5c356-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5c356-124">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5c356-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5c356-125">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c356-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c356-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="5c356-126">See also</span></span>

- [<span data-ttu-id="5c356-127">マネージド デバッグ アシスタントによるエラーの診断</span><span class="sxs-lookup"><span data-stu-id="5c356-127">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="5c356-128">ICorDebugManagedCallback2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5c356-128">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="5c356-129">ICorDebugManagedCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5c356-129">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
