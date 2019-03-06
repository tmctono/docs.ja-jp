---
title: ICorDebugThread2::InterceptCurrentException メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugThread2.InterceptCurrentException
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread2::InterceptCurrentException
helpviewer_keywords:
- InterceptCurrentException method [.NET Framework debugging]
- ICorDebugThread2::InterceptCurrentException method [.NET Framework debugging]
ms.assetid: 536d2357-1b97-49e0-a10c-c860aed74e6e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 01b883a5c6dd0cff119ff09747d32c607ac7ec60
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57500994"
---
# <a name="icordebugthread2interceptcurrentexception-method"></a><span data-ttu-id="dce1a-102">ICorDebugThread2::InterceptCurrentException メソッド</span><span class="sxs-lookup"><span data-stu-id="dce1a-102">ICorDebugThread2::InterceptCurrentException Method</span></span>
<span data-ttu-id="dce1a-103">このスレッドで現在の例外をインターセプトするデバッガーを使用します。</span><span class="sxs-lookup"><span data-stu-id="dce1a-103">Allows a debugger to intercept the current exception on this thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dce1a-104">構文</span><span class="sxs-lookup"><span data-stu-id="dce1a-104">Syntax</span></span>  
  
```  
HRESULT InterceptCurrentException (  
    [in] ICorDebugFrame  *pFrame  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dce1a-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="dce1a-105">Parameters</span></span>  
 `pFrame`  
 <span data-ttu-id="dce1a-106">[in]アクティブなスタック フレームを表す、ICorDebugFrame へのポインター。</span><span class="sxs-lookup"><span data-stu-id="dce1a-106">[in] A pointer to an ICorDebugFrame that represents the active stack frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dce1a-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="dce1a-107">Remarks</span></span>  
 <span data-ttu-id="dce1a-108">`InterceptCurrentException`例外コールバックを間メソッドを呼び出すことができます ([icordebugmanagedcallback::exception](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exception-method.md)または[icordebugmanagedcallback 2::exception](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-exception-method.md)) と関連付けられている呼び出し[Icordebugcontroller::continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="dce1a-108">The `InterceptCurrentException` method can be called between an exception callback ([ICorDebugManagedCallback::Exception](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exception-method.md) or [ICorDebugManagedCallback2::Exception](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-exception-method.md)) and the associated call to [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dce1a-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="dce1a-109">Requirements</span></span>  
 <span data-ttu-id="dce1a-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dce1a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dce1a-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dce1a-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dce1a-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dce1a-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dce1a-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dce1a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
