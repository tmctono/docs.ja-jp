---
title: ICorDebugManagedCallback::CreateProcess メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.CreateProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::CreateProcess
helpviewer_keywords:
- ICorDebugManagedCallback::CreateProcess method [.NET Framework debugging]
- CreateProcess method, ICorDebugManagedCallback interface [.NET Framework debugging]
ms.assetid: 8e89d5ee-e4e3-4738-8302-0b7d1cf4846e
topic_type:
- apiref
ms.openlocfilehash: d773368c85fd42fd169109cf1c7e6635705ebb7e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73090224"
---
# <a name="icordebugmanagedcallbackcreateprocess-method"></a><span data-ttu-id="bee80-102">ICorDebugManagedCallback::CreateProcess メソッド</span><span class="sxs-lookup"><span data-stu-id="bee80-102">ICorDebugManagedCallback::CreateProcess Method</span></span>
<span data-ttu-id="bee80-103">プロセスが初めてアタッチまたは開始されたときにデバッガーに通知します。</span><span class="sxs-lookup"><span data-stu-id="bee80-103">Notifies the debugger when a process has been attached or started for the first time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bee80-104">構文</span><span class="sxs-lookup"><span data-stu-id="bee80-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateProcess (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bee80-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="bee80-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="bee80-106">からアタッチまたは開始されたプロセスを表す、のオブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="bee80-106">[in] A pointer to an ICorDebugProcess object that represents the process that has been attached or started.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bee80-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="bee80-107">Remarks</span></span>  
 <span data-ttu-id="bee80-108">このメソッドは、共通言語ランタイムが初期化されるまで呼び出されません。</span><span class="sxs-lookup"><span data-stu-id="bee80-108">This method is not called until the common language runtime is initialized.</span></span> <span data-ttu-id="bee80-109">ほとんどの[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)メソッドは、`CreateProcess` コールバックの前に CORDBG_E_NOTREADY を返します。</span><span class="sxs-lookup"><span data-stu-id="bee80-109">Most of the [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) methods will return CORDBG_E_NOTREADY before the `CreateProcess` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bee80-110">［要件］</span><span class="sxs-lookup"><span data-stu-id="bee80-110">Requirements</span></span>  
 <span data-ttu-id="bee80-111">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bee80-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bee80-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bee80-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bee80-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bee80-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bee80-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bee80-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bee80-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="bee80-115">See also</span></span>

- [<span data-ttu-id="bee80-116">ICorDebugManagedCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bee80-116">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
