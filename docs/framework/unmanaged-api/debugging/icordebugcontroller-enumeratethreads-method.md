---
title: ICorDebugController::EnumerateThreads メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugController.EnumerateThreads
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::EnumerateThreads
helpviewer_keywords:
- ICorDebugController::EnumerateThreads method [.NET Framework debugging]
- EnumerateThreads method [.NET Framework debugging]
ms.assetid: 73f536f6-4668-4a4a-b3e4-ac7df862d5be
topic_type:
- apiref
ms.openlocfilehash: 291f6c05171b5e507afaa70537aafdc9002a506e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125409"
---
# <a name="icordebugcontrollerenumeratethreads-method"></a><span data-ttu-id="b2dd9-102">ICorDebugController::EnumerateThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="b2dd9-102">ICorDebugController::EnumerateThreads Method</span></span>
<span data-ttu-id="b2dd9-103">プロセス内のアクティブなマネージスレッドの列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="b2dd9-103">Gets an enumerator for the active managed threads in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2dd9-104">構文</span><span class="sxs-lookup"><span data-stu-id="b2dd9-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateThreads (  
    [out] ICorDebugThreadEnum **ppThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b2dd9-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b2dd9-105">Parameters</span></span>  
 `ppThreads`  
 <span data-ttu-id="b2dd9-106">入出力プロセス内でアクティブになっているすべてのマネージスレッドの列挙子を表す "いい Threadenum" オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="b2dd9-106">[out] A pointer to the address of an "ICorDebugThreadEnum" object that represents an enumerator for all managed threads that are active in the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b2dd9-107">コメント</span><span class="sxs-lookup"><span data-stu-id="b2dd9-107">Remarks</span></span>  
 <span data-ttu-id="b2dd9-108">スレッドがアクティブであると見なされるのは、["CreateThread"](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md) コールバックがディスパッチされてから、"  [Managedcallback:: exitthread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitthread-method.md) " コールバックがディスパッチされる前です。</span><span class="sxs-lookup"><span data-stu-id="b2dd9-108">A thread is considered active after the [ICorDebugManagedCallback::CreateThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md) callback has been dispatched and before the [ICorDebugManagedCallback::ExitThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitthread-method.md) callback has been dispatched.</span></span> <span data-ttu-id="b2dd9-109">マネージスレッドは、必ずしもスタック上にマネージフレームを持つとは限りません。</span><span class="sxs-lookup"><span data-stu-id="b2dd9-109">A managed thread may not necessarily have any managed frames on its stack.</span></span> <span data-ttu-id="b2dd9-110">スレッドは、によっては、"、 [" という](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md)ように列挙できます。</span><span class="sxs-lookup"><span data-stu-id="b2dd9-110">Threads can be enumerated even before the [ICorDebugManagedCallback::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) callback.</span></span> <span data-ttu-id="b2dd9-111">列挙体は、自然に空になります。</span><span class="sxs-lookup"><span data-stu-id="b2dd9-111">The enumeration will naturally be empty.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2dd9-112">要件</span><span class="sxs-lookup"><span data-stu-id="b2dd9-112">Requirements</span></span>  
 <span data-ttu-id="b2dd9-113">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2dd9-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2dd9-114">**ヘッダー:** CorDebug .idl、CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="b2dd9-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b2dd9-115">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="b2dd9-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b2dd9-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2dd9-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2dd9-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="b2dd9-117">See also</span></span>
