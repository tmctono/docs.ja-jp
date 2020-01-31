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
ms.openlocfilehash: 0c3059697014cea33081f6cb81b9d93c7d028c2e
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777470"
---
# <a name="icordebugmanagedcallbackcreateprocess-method"></a><span data-ttu-id="6f16a-102">ICorDebugManagedCallback::CreateProcess メソッド</span><span class="sxs-lookup"><span data-stu-id="6f16a-102">ICorDebugManagedCallback::CreateProcess Method</span></span>
<span data-ttu-id="6f16a-103">プロセスが初めてアタッチまたは開始されたときにデバッガーに通知します。</span><span class="sxs-lookup"><span data-stu-id="6f16a-103">Notifies the debugger when a process has been attached or started for the first time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f16a-104">構文</span><span class="sxs-lookup"><span data-stu-id="6f16a-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateProcess (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6f16a-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6f16a-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="6f16a-106">からアタッチまたは開始されたプロセスを表す、のオブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="6f16a-106">[in] A pointer to an ICorDebugProcess object that represents the process that has been attached or started.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6f16a-107">コメント</span><span class="sxs-lookup"><span data-stu-id="6f16a-107">Remarks</span></span>  
 <span data-ttu-id="6f16a-108">このメソッドは、共通言語ランタイムが初期化されるまで呼び出されません。</span><span class="sxs-lookup"><span data-stu-id="6f16a-108">This method is not called until the common language runtime is initialized.</span></span> <span data-ttu-id="6f16a-109">ほとんどの[ICorDebug](icordebug-interface.md)メソッドは、`CreateProcess` コールバックの前に CORDBG_E_NOTREADY を返します。</span><span class="sxs-lookup"><span data-stu-id="6f16a-109">Most of the [ICorDebug](icordebug-interface.md) methods will return CORDBG_E_NOTREADY before the `CreateProcess` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f16a-110">要件</span><span class="sxs-lookup"><span data-stu-id="6f16a-110">Requirements</span></span>  
 <span data-ttu-id="6f16a-111">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6f16a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f16a-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6f16a-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6f16a-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6f16a-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6f16a-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6f16a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f16a-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="6f16a-115">See also</span></span>

- [<span data-ttu-id="6f16a-116">ICorDebugManagedCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6f16a-116">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
