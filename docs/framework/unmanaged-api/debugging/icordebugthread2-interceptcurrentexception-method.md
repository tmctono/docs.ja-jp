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
ms.openlocfilehash: 1f3cf3db5df610e57a957147f0ab79121679e00b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138700"
---
# <a name="icordebugthread2interceptcurrentexception-method"></a><span data-ttu-id="839b0-102">ICorDebugThread2::InterceptCurrentException メソッド</span><span class="sxs-lookup"><span data-stu-id="839b0-102">ICorDebugThread2::InterceptCurrentException Method</span></span>
<span data-ttu-id="839b0-103">デバッガーがこのスレッドの現在の例外をインターセプトできるようにします。</span><span class="sxs-lookup"><span data-stu-id="839b0-103">Allows a debugger to intercept the current exception on this thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="839b0-104">構文</span><span class="sxs-lookup"><span data-stu-id="839b0-104">Syntax</span></span>  
  
```cpp  
HRESULT InterceptCurrentException (  
    [in] ICorDebugFrame  *pFrame  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="839b0-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="839b0-105">Parameters</span></span>  
 `pFrame`  
 <span data-ttu-id="839b0-106">からアクティブなスタックフレームを表すテキストフレームへのポインター。</span><span class="sxs-lookup"><span data-stu-id="839b0-106">[in] A pointer to an ICorDebugFrame that represents the active stack frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="839b0-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="839b0-107">Remarks</span></span>  
 <span data-ttu-id="839b0-108">`InterceptCurrentException` メソッドは、例外コール[バック (](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exception-method.md) [ICorDebugManagedCallback2:: exception](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-exception-method.md)) と、それに関連付けられている:: [Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md)の間で呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="839b0-108">The `InterceptCurrentException` method can be called between an exception callback ([ICorDebugManagedCallback::Exception](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exception-method.md) or [ICorDebugManagedCallback2::Exception](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-exception-method.md)) and the associated call to [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="839b0-109">［要件］</span><span class="sxs-lookup"><span data-stu-id="839b0-109">Requirements</span></span>  
 <span data-ttu-id="839b0-110">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="839b0-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="839b0-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="839b0-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="839b0-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="839b0-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="839b0-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="839b0-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
