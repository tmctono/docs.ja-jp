---
title: ICorProfilerCallback::ThreadAssignedToOSThread メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ThreadAssignedToOSThread
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ThreadAssignedToOSThread
helpviewer_keywords:
- ThreadAssignedToOSThread method [.NET Framework profiling]
- ICorProfilerCallback::ThreadAssignedToOSThread method [.NET Framework profiling]
ms.assetid: f9671e5a-7b14-4f5b-8404-58136422c8b2
topic_type:
- apiref
ms.openlocfilehash: 182a82300183046ccb4a93a79af0dd8f23848c20
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503177"
---
# <a name="icorprofilercallbackthreadassignedtoosthread-method"></a><span data-ttu-id="b9ed0-102">ICorProfilerCallback::ThreadAssignedToOSThread メソッド</span><span class="sxs-lookup"><span data-stu-id="b9ed0-102">ICorProfilerCallback::ThreadAssignedToOSThread Method</span></span>
<span data-ttu-id="b9ed0-103">特定のオペレーティングシステムスレッドを使用してマネージスレッドが実装されていることをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="b9ed0-103">Notifies the profiler that a managed thread is being implemented using a particular operating system thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9ed0-104">構文</span><span class="sxs-lookup"><span data-stu-id="b9ed0-104">Syntax</span></span>  
  
```cpp  
HRESULT ThreadAssignedToOSThread(  
    [in] ThreadID managedThreadId,  
    [in] DWORD    osThreadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b9ed0-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b9ed0-105">Parameters</span></span>  
 `managedThreadId`  
 <span data-ttu-id="b9ed0-106">からマネージスレッドの識別子。</span><span class="sxs-lookup"><span data-stu-id="b9ed0-106">[in] The identifier of the managed thread.</span></span>  
  
 `osThreadId`  
 <span data-ttu-id="b9ed0-107">からオペレーティングシステムスレッドの識別子。</span><span class="sxs-lookup"><span data-stu-id="b9ed0-107">[in] The identifier of the operating system thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b9ed0-108">解説</span><span class="sxs-lookup"><span data-stu-id="b9ed0-108">Remarks</span></span>  
 <span data-ttu-id="b9ed0-109">コールバックが存在するので、 `ThreadAssignedToOSThread` プロファイラーは、オペレーティングシステムスレッドのファイバー全体でマネージスレッドに対して正確なマッピングを維持できます。</span><span class="sxs-lookup"><span data-stu-id="b9ed0-109">The `ThreadAssignedToOSThread` callback exists so that the profiler can maintain an accurate mapping across fibers of operating system threads to managed threads.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9ed0-110">要件</span><span class="sxs-lookup"><span data-stu-id="b9ed0-110">Requirements</span></span>  
 <span data-ttu-id="b9ed0-111">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b9ed0-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9ed0-112">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b9ed0-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b9ed0-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b9ed0-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b9ed0-114">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9ed0-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9ed0-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="b9ed0-115">See also</span></span>

- [<span data-ttu-id="b9ed0-116">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b9ed0-116">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
