---
title: ICorDebugController::Stop メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugController.Stop
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::Stop
helpviewer_keywords:
- Stop method, ICorDebugController interface [.NET Framework debugging]
- ICorDebugController::Stop method [.NET Framework debugging]
ms.assetid: c34e79be-a7fb-479e-8dec-d126a4c330e5
topic_type:
- apiref
ms.openlocfilehash: c8c6b40f7a9c63a577140209eed65436040addcb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125384"
---
# <a name="icordebugcontrollerstop-method"></a><span data-ttu-id="c43ff-102">ICorDebugController::Stop メソッド</span><span class="sxs-lookup"><span data-stu-id="c43ff-102">ICorDebugController::Stop Method</span></span>
<span data-ttu-id="c43ff-103">プロセスでマネージコードを実行しているすべてのスレッドで協調停止を実行します。</span><span class="sxs-lookup"><span data-stu-id="c43ff-103">Performs a cooperative stop on all threads that are running managed code in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c43ff-104">構文</span><span class="sxs-lookup"><span data-stu-id="c43ff-104">Syntax</span></span>  
  
```cpp  
HRESULT Stop (  
    [in] DWORD dwTimeoutIgnored  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c43ff-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c43ff-105">Parameters</span></span>  
 `dwTimeoutIgnored`  
 <span data-ttu-id="c43ff-106">使用しません。</span><span class="sxs-lookup"><span data-stu-id="c43ff-106">Not used.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c43ff-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="c43ff-107">Remarks</span></span>  
 <span data-ttu-id="c43ff-108">`Stop` は、プロセスでマネージコードを実行しているすべてのスレッドで協調停止を実行します。</span><span class="sxs-lookup"><span data-stu-id="c43ff-108">`Stop` performs a cooperative stop on all threads running managed code in the process.</span></span> <span data-ttu-id="c43ff-109">マネージ専用のデバッグセッションでは、アンマネージスレッドは引き続き実行できます (ただし、マネージコードを呼び出そうとするとブロックされます)。</span><span class="sxs-lookup"><span data-stu-id="c43ff-109">During a managed-only debugging session, unmanaged threads may continue to run (but will be blocked when trying to call managed code).</span></span> <span data-ttu-id="c43ff-110">相互運用機能デバッグセッションでは、アンマネージスレッドも停止します。</span><span class="sxs-lookup"><span data-stu-id="c43ff-110">During an interop debugging session, unmanaged threads will also be stopped.</span></span> <span data-ttu-id="c43ff-111">現在、`dwTimeoutIgnored` の値は無視され、無限 (-1) として扱われます。</span><span class="sxs-lookup"><span data-stu-id="c43ff-111">The `dwTimeoutIgnored` value is currently ignored and treated as INFINITE (-1).</span></span> <span data-ttu-id="c43ff-112">デッドロックが原因で協調停止が失敗した場合、すべてのスレッドが中断され、E_TIMEOUT が返されます。</span><span class="sxs-lookup"><span data-stu-id="c43ff-112">If the cooperative stop fails due to a deadlock, all threads are suspended and E_TIMEOUT is returned.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c43ff-113">`Stop` は、デバッグ API で唯一の同期メソッドです。</span><span class="sxs-lookup"><span data-stu-id="c43ff-113">`Stop` is the only synchronous method in the debugging API.</span></span> <span data-ttu-id="c43ff-114">`Stop` が S_OK を返した場合、プロセスは停止されます。</span><span class="sxs-lookup"><span data-stu-id="c43ff-114">When `Stop` returns S_OK, the process is stopped.</span></span> <span data-ttu-id="c43ff-115">リスナーに停止を通知するためのコールバックが付与されていません。</span><span class="sxs-lookup"><span data-stu-id="c43ff-115">No callback is given to notify listeners of the stop.</span></span> <span data-ttu-id="c43ff-116">デバッガーは、このプロセスを再開できるようにするために、を[実行](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md)する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c43ff-116">The debugger must call [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) to allow the process to resume.</span></span>  
  
 <span data-ttu-id="c43ff-117">デバッガーは停止カウンターを保持します。</span><span class="sxs-lookup"><span data-stu-id="c43ff-117">The debugger maintains a stop counter.</span></span> <span data-ttu-id="c43ff-118">カウンターが0になると、コントローラーが再開されます。</span><span class="sxs-lookup"><span data-stu-id="c43ff-118">When the counter goes to zero, the controller is resumed.</span></span> <span data-ttu-id="c43ff-119">`Stop` またはディスパッチされた各コールバックの各呼び出しは、カウンターをインクリメントします。</span><span class="sxs-lookup"><span data-stu-id="c43ff-119">Each call to `Stop` or each dispatched callback increments the counter.</span></span> <span data-ttu-id="c43ff-120">`ICorDebugController::Continue` を呼び出すたびに、カウンターがデクリメントされます。</span><span class="sxs-lookup"><span data-stu-id="c43ff-120">Each call to `ICorDebugController::Continue` decrements the counter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c43ff-121">［要件］</span><span class="sxs-lookup"><span data-stu-id="c43ff-121">Requirements</span></span>  
 <span data-ttu-id="c43ff-122">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c43ff-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c43ff-123">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c43ff-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c43ff-124">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c43ff-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c43ff-125">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c43ff-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c43ff-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="c43ff-126">See also</span></span>
