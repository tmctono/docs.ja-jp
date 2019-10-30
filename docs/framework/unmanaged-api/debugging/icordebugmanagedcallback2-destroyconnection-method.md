---
title: ICorDebugManagedCallback2::DestroyConnection メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.DestroyConnection
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::DestroyConnection
helpviewer_keywords:
- DestroyConnection method [.NET Framework debugging]
- ICorDebugManagedCallback2::DestroyConnection method [.NET Framework debugging]
ms.assetid: cf7940e9-4558-4319-925c-09f6c98c8fcd
topic_type:
- apiref
ms.openlocfilehash: a64df9f821021547efd08045e9f67fee25173e5a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137436"
---
# <a name="icordebugmanagedcallback2destroyconnection-method"></a><span data-ttu-id="668e2-102">ICorDebugManagedCallback2::DestroyConnection メソッド</span><span class="sxs-lookup"><span data-stu-id="668e2-102">ICorDebugManagedCallback2::DestroyConnection Method</span></span>
<span data-ttu-id="668e2-103">指定された接続が終了したことをデバッガーに通知します。</span><span class="sxs-lookup"><span data-stu-id="668e2-103">Notifies the debugger that the specified connection has been terminated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="668e2-104">構文</span><span class="sxs-lookup"><span data-stu-id="668e2-104">Syntax</span></span>  
  
```cpp  
HRESULT DestroyConnection (  
    [in] ICorDebugProcess     *pProcess,  
    [in] CONNID               dwConnectionId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="668e2-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="668e2-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="668e2-106">から破棄された接続を含むプロセスを表す、のオブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="668e2-106">[in] A pointer to an ICorDebugProcess object that represents the process containing the connection that was destroyed.</span></span>  
  
 `dwConnectionId`  
 <span data-ttu-id="668e2-107">から破棄された接続の ID。</span><span class="sxs-lookup"><span data-stu-id="668e2-107">[in] The ID of the connection that was destroyed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="668e2-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="668e2-108">Remarks</span></span>  
 <span data-ttu-id="668e2-109">ホストが[ホスティング API](../../../../docs/framework/unmanaged-api/hosting/index.md)で[ICLRDebugManager:: endconnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md)を呼び出したときに、`DestroyConnection` コールバックが発生します。</span><span class="sxs-lookup"><span data-stu-id="668e2-109">A `DestroyConnection` callback will be fired when a host calls [ICLRDebugManager::EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md) in the [Hosting API](../../../../docs/framework/unmanaged-api/hosting/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="668e2-110">［要件］</span><span class="sxs-lookup"><span data-stu-id="668e2-110">Requirements</span></span>  
 <span data-ttu-id="668e2-111">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="668e2-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="668e2-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="668e2-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="668e2-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="668e2-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="668e2-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="668e2-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="668e2-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="668e2-115">See also</span></span>

- [<span data-ttu-id="668e2-116">ICorDebugManagedCallback2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="668e2-116">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="668e2-117">ICorDebugManagedCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="668e2-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
