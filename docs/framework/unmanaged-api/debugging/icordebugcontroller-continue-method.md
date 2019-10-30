---
title: ICorDebugController::Continue メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugController.Continue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::Continue
helpviewer_keywords:
- Continue method [.NET Framework debugging]
- ICorDebugController::Continue method [.NET Framework debugging]
ms.assetid: 8684cd06-ad3e-48ef-832e-15320e1f43a2
topic_type:
- apiref
ms.openlocfilehash: 14356a12c944ef93dba5e7b818d3ee5cf5adc607
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125418"
---
# <a name="icordebugcontrollercontinue-method"></a><span data-ttu-id="2b241-102">ICorDebugController::Continue メソッド</span><span class="sxs-lookup"><span data-stu-id="2b241-102">ICorDebugController::Continue Method</span></span>

<span data-ttu-id="2b241-103">[Stop メソッド](icordebugcontroller-stop-method.md)の呼び出し後に、マネージスレッドの実行を再開します。</span><span class="sxs-lookup"><span data-stu-id="2b241-103">Resumes execution of managed threads after a call to [Stop Method](icordebugcontroller-stop-method.md).</span></span>

## <a name="syntax"></a><span data-ttu-id="2b241-104">構文</span><span class="sxs-lookup"><span data-stu-id="2b241-104">Syntax</span></span>

```cpp
HRESULT Continue (
    [in] BOOL fIsOutOfBand
);
```

## <a name="parameters"></a><span data-ttu-id="2b241-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2b241-105">Parameters</span></span>

`fIsOutOfBand`  
<span data-ttu-id="2b241-106">から帯域外イベントから続行する場合は `true` に設定します。それ以外の場合は、を `false`に設定します。</span><span class="sxs-lookup"><span data-stu-id="2b241-106">[in] Set to `true` if continuing from an out-of-band event; otherwise, set to `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="2b241-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="2b241-107">Remarks</span></span>

<span data-ttu-id="2b241-108">`Continue` は、`ICorDebugController::Stop` メソッドの呼び出し後にプロセスを続行します。</span><span class="sxs-lookup"><span data-stu-id="2b241-108">`Continue` continues the process after a call to the `ICorDebugController::Stop` method.</span></span>

<span data-ttu-id="2b241-109">混合モードのデバッグを実行する場合は、アウトオブバンドイベントから続行する場合を除き、Win32 イベントスレッドで `Continue` を呼び出さないでください。</span><span class="sxs-lookup"><span data-stu-id="2b241-109">When doing mixed-mode debugging, do not call `Continue` on the Win32 event thread unless you are continuing from an out-of-band event.</span></span>

<span data-ttu-id="2b241-110">*帯域内イベント*は、マネージイベント、またはデバッガーがプロセスのマネージ状態との対話をサポートする通常のアンマネージイベントのいずれかです。</span><span class="sxs-lookup"><span data-stu-id="2b241-110">An *in-band event* is either a managed event or a normal unmanaged event during which the debugger supports interaction with the managed state of the process.</span></span> <span data-ttu-id="2b241-111">この場合、デバッガーは、`fOutOfBand` パラメーターが `false` に設定された状態で[ICorDebugUnmanagedCallback::D Eのイベント](icordebugunmanagedcallback-debugevent-method.md)コールバックを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="2b241-111">In this case, the debugger receives the [ICorDebugUnmanagedCallback::DebugEvent](icordebugunmanagedcallback-debugevent-method.md) callback with its `fOutOfBand` parameter set to `false`.</span></span>

<span data-ttu-id="2b241-112">*アウトオブバンドイベント*は、イベントによってプロセスが停止されている間に、プロセスのマネージ状態との相互作用が不可能なアンマネージイベントです。</span><span class="sxs-lookup"><span data-stu-id="2b241-112">An *out-of-band event* is an unmanaged event during which interaction with the managed state of the process is impossible while the process is stopped due to the event.</span></span> <span data-ttu-id="2b241-113">この場合、デバッガーは、`fOutOfBand` パラメーターが `true`に設定された `ICorDebugUnmanagedCallback::DebugEvent` コールバックを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="2b241-113">In this case, the debugger receives the `ICorDebugUnmanagedCallback::DebugEvent` callback with its `fOutOfBand` parameter set to `true`.</span></span>

## <a name="requirements"></a><span data-ttu-id="2b241-114">［要件］</span><span class="sxs-lookup"><span data-stu-id="2b241-114">Requirements</span></span>

<span data-ttu-id="2b241-115">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b241-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="2b241-116">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2b241-116">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="2b241-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2b241-117">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="2b241-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2b241-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
