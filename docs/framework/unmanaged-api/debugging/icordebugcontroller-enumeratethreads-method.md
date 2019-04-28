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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 17ba15553d2e7dcd2090870eaab54b4c680631f1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61749346"
---
# <a name="icordebugcontrollerenumeratethreads-method"></a><span data-ttu-id="25157-102">ICorDebugController::EnumerateThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="25157-102">ICorDebugController::EnumerateThreads Method</span></span>
<span data-ttu-id="25157-103">プロセスのアクティブなマネージ スレッドの列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="25157-103">Gets an enumerator for the active managed threads in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25157-104">構文</span><span class="sxs-lookup"><span data-stu-id="25157-104">Syntax</span></span>  
  
```  
HRESULT EnumerateThreads (  
    [out] ICorDebugThreadEnum **ppThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="25157-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="25157-105">Parameters</span></span>  
 `ppThreads`  
 <span data-ttu-id="25157-106">[out]プロセスでアクティブになっているすべてのマネージ スレッドの列挙子を表す"ICorDebugThreadEnum"オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="25157-106">[out] A pointer to the address of an "ICorDebugThreadEnum" object that represents an enumerator for all managed threads that are active in the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="25157-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="25157-107">Remarks</span></span>  
 <span data-ttu-id="25157-108">スレッドの後にアクティブと見なされます、 [icordebugmanagedcallback::createthread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md)コールバックがディスパッチされたとする前に、 [icordebugmanagedcallback::exitthread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitthread-method.md)コールバックがディスパッチされました.</span><span class="sxs-lookup"><span data-stu-id="25157-108">A thread is considered active after the [ICorDebugManagedCallback::CreateThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md) callback has been dispatched and before the [ICorDebugManagedCallback::ExitThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitthread-method.md) callback has been dispatched.</span></span> <span data-ttu-id="25157-109">マネージ スレッドとは限りませんがない任意のマネージ フレーム、スタックにします。</span><span class="sxs-lookup"><span data-stu-id="25157-109">A managed thread may not necessarily have any managed frames on its stack.</span></span> <span data-ttu-id="25157-110">前であってもに、スレッドを列挙することができます、 [icordebugmanagedcallback::createprocess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md)コールバック。</span><span class="sxs-lookup"><span data-stu-id="25157-110">Threads can be enumerated even before the [ICorDebugManagedCallback::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) callback.</span></span> <span data-ttu-id="25157-111">列挙体は空になります。</span><span class="sxs-lookup"><span data-stu-id="25157-111">The enumeration will naturally be empty.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="25157-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="25157-112">Requirements</span></span>  
 <span data-ttu-id="25157-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="25157-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="25157-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="25157-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="25157-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="25157-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="25157-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="25157-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25157-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="25157-117">See also</span></span>
