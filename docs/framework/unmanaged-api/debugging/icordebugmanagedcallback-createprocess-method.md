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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eda214200ca4c3837ad89ed14887ef6b09af7d30
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59160369"
---
# <a name="icordebugmanagedcallbackcreateprocess-method"></a><span data-ttu-id="eae13-102">ICorDebugManagedCallback::CreateProcess メソッド</span><span class="sxs-lookup"><span data-stu-id="eae13-102">ICorDebugManagedCallback::CreateProcess Method</span></span>
<span data-ttu-id="eae13-103">プロセスにアタッチまたは最初に起動された場合に、デバッガーに通知します。</span><span class="sxs-lookup"><span data-stu-id="eae13-103">Notifies the debugger when a process has been attached or started for the first time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eae13-104">構文</span><span class="sxs-lookup"><span data-stu-id="eae13-104">Syntax</span></span>  
  
```  
HRESULT CreateProcess (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eae13-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="eae13-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="eae13-106">[in]ICorDebugProcess を表すオブジェクトをアタッチまたは開始されたプロセスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="eae13-106">[in] A pointer to an ICorDebugProcess object that represents the process that has been attached or started.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eae13-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="eae13-107">Remarks</span></span>  
 <span data-ttu-id="eae13-108">共通言語ランタイムが初期化されるまで、このメソッドは呼び出されません。</span><span class="sxs-lookup"><span data-stu-id="eae13-108">This method is not called until the common language runtime is initialized.</span></span> <span data-ttu-id="eae13-109">ほとんどの[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)メソッドでは、前に CORDBG_E_NOTREADY を返します、`CreateProcess`コールバック。</span><span class="sxs-lookup"><span data-stu-id="eae13-109">Most of the [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) methods will return CORDBG_E_NOTREADY before the `CreateProcess` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eae13-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="eae13-110">Requirements</span></span>  
 <span data-ttu-id="eae13-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="eae13-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eae13-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="eae13-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="eae13-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eae13-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="eae13-114">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="eae13-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="eae13-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="eae13-115">See also</span></span>

- [<span data-ttu-id="eae13-116">ICorDebugManagedCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="eae13-116">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
