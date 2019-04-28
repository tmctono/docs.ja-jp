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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7eacffe5769bc77ab626f6adbc99db1137da565f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61749671"
---
# <a name="icordebugcontrollercontinue-method"></a><span data-ttu-id="21373-102">ICorDebugController::Continue メソッド</span><span class="sxs-lookup"><span data-stu-id="21373-102">ICorDebugController::Continue Method</span></span>
<span data-ttu-id="21373-103">呼び出しの後にマネージ スレッドの実行を再開[Stop メソッド](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="21373-103">Resumes execution of managed threads after a call to [Stop Method](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21373-104">構文</span><span class="sxs-lookup"><span data-stu-id="21373-104">Syntax</span></span>  
  
```  
HRESULT Continue (  
    [in] BOOL fIsOutOfBand  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="21373-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="21373-105">Parameters</span></span>  
 `fIsOutOfBand`  
 <span data-ttu-id="21373-106">[in]設定`true`帯域外のイベントを引き続き使用する場合がそれに設定`false`します。</span><span class="sxs-lookup"><span data-stu-id="21373-106">[in] Set to `true` if continuing from an out-of-band event; otherwise, set to `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="21373-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="21373-107">Remarks</span></span>  
 <span data-ttu-id="21373-108">`Continue` 呼び出しの後に、プロセスを続行、`ICorDebugController::Stop`メソッド。</span><span class="sxs-lookup"><span data-stu-id="21373-108">`Continue` continues the process after a call to the `ICorDebugController::Stop` method.</span></span>  
  
 <span data-ttu-id="21373-109">混合モードのデバッグを行うときに呼び出さない`Continue`帯域外のイベントから続行する場合を除き、Win32 のイベントがスレッドします。</span><span class="sxs-lookup"><span data-stu-id="21373-109">When doing mixed-mode debugging, do not call `Continue` on the Win32 event thread unless you are continuing from an out-of-band event.</span></span>  
  
 <span data-ttu-id="21373-110">*帯域内イベント*マネージ イベントまたはデバッガーがプロセスの状態の管理との対話をサポートする通常の非管理対象イベントのいずれかです。</span><span class="sxs-lookup"><span data-stu-id="21373-110">An *in-band event* is either a managed event or a normal unmanaged event during which the debugger supports interaction with the managed state of the process.</span></span> <span data-ttu-id="21373-111">この場合、デバッガーを受け取る、 [icordebugunmanagedcallback::debugevent](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-debugevent-method.md)のコールバックをその`fOutOfBand`パラメーターに設定`false`します。</span><span class="sxs-lookup"><span data-stu-id="21373-111">In this case, the debugger receives the [ICorDebugUnmanagedCallback::DebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-debugevent-method.md) callback with its `fOutOfBand` parameter set to `false`.</span></span>  
  
 <span data-ttu-id="21373-112">*帯域外のイベント*はプロセスの状態の管理との対話にできなくなること、イベントのため、プロセスの停止中に非管理対象のイベントです。</span><span class="sxs-lookup"><span data-stu-id="21373-112">An *out-of-band event* is an unmanaged event during which interaction with the managed state of the process is impossible while the process is stopped due to the event.</span></span> <span data-ttu-id="21373-113">この場合、デバッガーを受け取る、`ICorDebugUnmanagedCallback::DebugEvent`のコールバックをその`fOutOfBand`パラメーターに設定`true`します。</span><span class="sxs-lookup"><span data-stu-id="21373-113">In this case, the debugger receives the `ICorDebugUnmanagedCallback::DebugEvent` callback with its `fOutOfBand` parameter set to `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="21373-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="21373-114">Requirements</span></span>  
 <span data-ttu-id="21373-115">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="21373-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21373-116">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="21373-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="21373-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="21373-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="21373-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="21373-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21373-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="21373-119">See also</span></span>
