---
title: ICorDebugManagedCallback::StepComplete メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.StepComplete
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::StepComplete
helpviewer_keywords:
- StepComplete method [.NET Framework debugging]
- ICorDebugManagedCallback::StepComplete method [.NET Framework debugging]
ms.assetid: 5e1f2c47-81df-4530-826d-96489cd68719
topic_type:
- apiref
ms.openlocfilehash: e5d828b8252b47c2edddbe14713208ae8bc2d19d
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777165"
---
# <a name="icordebugmanagedcallbackstepcomplete-method"></a><span data-ttu-id="00e32-102">ICorDebugManagedCallback::StepComplete メソッド</span><span class="sxs-lookup"><span data-stu-id="00e32-102">ICorDebugManagedCallback::StepComplete Method</span></span>
<span data-ttu-id="00e32-103">ステップが完了したことをデバッガーに通知します。</span><span class="sxs-lookup"><span data-stu-id="00e32-103">Notifies the debugger that a step has completed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00e32-104">構文</span><span class="sxs-lookup"><span data-stu-id="00e32-104">Syntax</span></span>  
  
```cpp  
HRESULT StepComplete (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] ICorDebugStepper    *pStepper,  
    [in] CorDebugStepReason   reason  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="00e32-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="00e32-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="00e32-106">からステップが完了したスレッドを含むアプリケーションドメインを表す、のオブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="00e32-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the thread in which the step has completed.</span></span>  
  
 `pThread`  
 <span data-ttu-id="00e32-107">からステップが完了したスレッドを表す、のスレッドオブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="00e32-107">[in] A pointer to an ICorDebugThread object that represents the thread in which the step has completed.</span></span>  
  
 `pStepper`  
 <span data-ttu-id="00e32-108">からコード実行のステップを表す ICorDebugStepper オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="00e32-108">[in] A pointer to an ICorDebugStepper object that represents the step in code execution.</span></span>  
  
 `reason`  
 <span data-ttu-id="00e32-109">から個々のステップの結果を示す CorDebugStepReason 列挙値。</span><span class="sxs-lookup"><span data-stu-id="00e32-109">[in] A value of the CorDebugStepReason enumeration that indicates the outcome of an individual step.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="00e32-110">コメント</span><span class="sxs-lookup"><span data-stu-id="00e32-110">Remarks</span></span>  
 <span data-ttu-id="00e32-111">デバッグが終了しない限り、必要に応じてステップを続行するためにステッパを使用できます。</span><span class="sxs-lookup"><span data-stu-id="00e32-111">The stepper may be used to continue stepping if desired, unless the debugging is terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="00e32-112">要件</span><span class="sxs-lookup"><span data-stu-id="00e32-112">Requirements</span></span>  
 <span data-ttu-id="00e32-113">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="00e32-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00e32-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="00e32-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="00e32-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="00e32-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="00e32-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00e32-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00e32-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="00e32-117">See also</span></span>

- [<span data-ttu-id="00e32-118">ICorDebugManagedCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="00e32-118">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
