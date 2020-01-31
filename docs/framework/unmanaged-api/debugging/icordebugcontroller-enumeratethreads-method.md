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
ms.openlocfilehash: 815dc63a2dedecc613506b0f98702f58d6e7bd04
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76783783"
---
# <a name="icordebugcontrollerenumeratethreads-method"></a><span data-ttu-id="67983-102">ICorDebugController::EnumerateThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="67983-102">ICorDebugController::EnumerateThreads Method</span></span>
<span data-ttu-id="67983-103">プロセス内のアクティブなマネージスレッドの列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="67983-103">Gets an enumerator for the active managed threads in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67983-104">構文</span><span class="sxs-lookup"><span data-stu-id="67983-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateThreads (  
    [out] ICorDebugThreadEnum **ppThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="67983-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="67983-105">Parameters</span></span>  
 `ppThreads`  
 <span data-ttu-id="67983-106">入出力プロセス内でアクティブになっているすべてのマネージスレッドの列挙子を表す "いい Threadenum" オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="67983-106">[out] A pointer to the address of an "ICorDebugThreadEnum" object that represents an enumerator for all managed threads that are active in the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="67983-107">コメント</span><span class="sxs-lookup"><span data-stu-id="67983-107">Remarks</span></span>  
 <span data-ttu-id="67983-108">スレッドがアクティブであると見なされるのは、"[CreateThread](icordebugmanagedcallback-createthread-method.md)" コールバックがディスパッチされてから、" [Managedcallback:: exitthread](icordebugmanagedcallback-exitthread-method.md) " コールバックがディスパッチされる前です。</span><span class="sxs-lookup"><span data-stu-id="67983-108">A thread is considered active after the [ICorDebugManagedCallback::CreateThread](icordebugmanagedcallback-createthread-method.md) callback has been dispatched and before the [ICorDebugManagedCallback::ExitThread](icordebugmanagedcallback-exitthread-method.md) callback has been dispatched.</span></span> <span data-ttu-id="67983-109">マネージスレッドは、必ずしもスタック上にマネージフレームを持つとは限りません。</span><span class="sxs-lookup"><span data-stu-id="67983-109">A managed thread may not necessarily have any managed frames on its stack.</span></span> <span data-ttu-id="67983-110">スレッドは、によっては、"、 [" という](icordebugmanagedcallback-createprocess-method.md)ように列挙できます。</span><span class="sxs-lookup"><span data-stu-id="67983-110">Threads can be enumerated even before the [ICorDebugManagedCallback::CreateProcess](icordebugmanagedcallback-createprocess-method.md) callback.</span></span> <span data-ttu-id="67983-111">列挙体は、自然に空になります。</span><span class="sxs-lookup"><span data-stu-id="67983-111">The enumeration will naturally be empty.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67983-112">要件</span><span class="sxs-lookup"><span data-stu-id="67983-112">Requirements</span></span>  
 <span data-ttu-id="67983-113">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="67983-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67983-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="67983-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="67983-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="67983-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="67983-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67983-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67983-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="67983-117">See also</span></span>
