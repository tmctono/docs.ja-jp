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
ms.openlocfilehash: c25a03ef5bbba18da31787c911f83a1348badd4b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791449"
---
# <a name="icordebugthread2interceptcurrentexception-method"></a><span data-ttu-id="34a84-102">ICorDebugThread2::InterceptCurrentException メソッド</span><span class="sxs-lookup"><span data-stu-id="34a84-102">ICorDebugThread2::InterceptCurrentException Method</span></span>
<span data-ttu-id="34a84-103">デバッガーがこのスレッドの現在の例外をインターセプトできるようにします。</span><span class="sxs-lookup"><span data-stu-id="34a84-103">Allows a debugger to intercept the current exception on this thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34a84-104">構文</span><span class="sxs-lookup"><span data-stu-id="34a84-104">Syntax</span></span>  
  
```cpp  
HRESULT InterceptCurrentException (  
    [in] ICorDebugFrame  *pFrame  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="34a84-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="34a84-105">Parameters</span></span>  
 `pFrame`  
 <span data-ttu-id="34a84-106">からアクティブなスタックフレームを表すテキストフレームへのポインター。</span><span class="sxs-lookup"><span data-stu-id="34a84-106">[in] A pointer to an ICorDebugFrame that represents the active stack frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="34a84-107">コメント</span><span class="sxs-lookup"><span data-stu-id="34a84-107">Remarks</span></span>  
 <span data-ttu-id="34a84-108">`InterceptCurrentException` メソッドは、例外コール[バック (](icordebugmanagedcallback-exception-method.md) [ICorDebugManagedCallback2:: exception](icordebugmanagedcallback2-exception-method.md)) と、それに関連付けられている:: [Continue](icordebugcontroller-continue-method.md)の間で呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="34a84-108">The `InterceptCurrentException` method can be called between an exception callback ([ICorDebugManagedCallback::Exception](icordebugmanagedcallback-exception-method.md) or [ICorDebugManagedCallback2::Exception](icordebugmanagedcallback2-exception-method.md)) and the associated call to [ICorDebugController::Continue](icordebugcontroller-continue-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34a84-109">要件</span><span class="sxs-lookup"><span data-stu-id="34a84-109">Requirements</span></span>  
 <span data-ttu-id="34a84-110">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="34a84-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34a84-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="34a84-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="34a84-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="34a84-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="34a84-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34a84-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
