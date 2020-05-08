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
ms.openlocfilehash: 4d69f13d4716b43c815148ff0fe4aa087b57c6e5
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82892753"
---
# <a name="icordebugcontrollerenumeratethreads-method"></a><span data-ttu-id="52d39-102">ICorDebugController::EnumerateThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="52d39-102">ICorDebugController::EnumerateThreads Method</span></span>
<span data-ttu-id="52d39-103">プロセス内のアクティブなマネージスレッドの列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="52d39-103">Gets an enumerator for the active managed threads in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52d39-104">構文</span><span class="sxs-lookup"><span data-stu-id="52d39-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateThreads (  
    [out] ICorDebugThreadEnum **ppThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="52d39-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="52d39-105">Parameters</span></span>  
 `ppThreads`  
 <span data-ttu-id="52d39-106">入出力プロセス内でアクティブになっているすべてのマネージスレッドの列挙子を表す "いい Threadenum" オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="52d39-106">[out] A pointer to the address of an "ICorDebugThreadEnum" object that represents an enumerator for all managed threads that are active in the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="52d39-107">解説</span><span class="sxs-lookup"><span data-stu-id="52d39-107">Remarks</span></span>  
 <span data-ttu-id="52d39-108">スレッドがアクティブであると見なされるのは、"CreateThread" コールバックがディスパッチされてから、" [ICorDebugManagedCallback::CreateThread](icordebugmanagedcallback-createthread-method.md) [Managedcallback:: exitthread](icordebugmanagedcallback-exitthread-method.md) " コールバックがディスパッチされる前です。</span><span class="sxs-lookup"><span data-stu-id="52d39-108">A thread is considered active after the [ICorDebugManagedCallback::CreateThread](icordebugmanagedcallback-createthread-method.md) callback has been dispatched and before the [ICorDebugManagedCallback::ExitThread](icordebugmanagedcallback-exitthread-method.md) callback has been dispatched.</span></span> <span data-ttu-id="52d39-109">マネージスレッドは、必ずしもスタック上にマネージフレームを持つとは限りません。</span><span class="sxs-lookup"><span data-stu-id="52d39-109">A managed thread may not necessarily have any managed frames on its stack.</span></span> <span data-ttu-id="52d39-110">スレッドは、によっては、"、 [" という](icordebugmanagedcallback-createprocess-method.md)ように列挙できます。</span><span class="sxs-lookup"><span data-stu-id="52d39-110">Threads can be enumerated even before the [ICorDebugManagedCallback::CreateProcess](icordebugmanagedcallback-createprocess-method.md) callback.</span></span> <span data-ttu-id="52d39-111">列挙体は、自然に空になります。</span><span class="sxs-lookup"><span data-stu-id="52d39-111">The enumeration will naturally be empty.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52d39-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="52d39-112">Requirements</span></span>  
 <span data-ttu-id="52d39-113">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="52d39-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52d39-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="52d39-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="52d39-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="52d39-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="52d39-116">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="52d39-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52d39-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="52d39-117">See also</span></span>
