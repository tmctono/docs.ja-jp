---
title: ICorProfilerInfo4::InitializeCurrentThread メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4::InitializeCurrentThread
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::InitializeCurrentThread
helpviewer_keywords:
- ICorProfilerInfo4::InitializeCurrentThread method [.NET Framework profiling]
- InitializeCurrentThread method, ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: 18a3335c-8c75-476c-b6de-72c0bfedae5d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b9bb5a2629e435d76691d48feef6689191b66373
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69957899"
---
# <a name="icorprofilerinfo4initializecurrentthread-method"></a><span data-ttu-id="4f711-102">ICorProfilerInfo4::InitializeCurrentThread メソッド</span><span class="sxs-lookup"><span data-stu-id="4f711-102">ICorProfilerInfo4::InitializeCurrentThread Method</span></span>
<span data-ttu-id="4f711-103">デッドロックを回避できるように、同じスレッドで、後続のプロファイラー API 呼び出しの前に現在のスレッドを初期化します。</span><span class="sxs-lookup"><span data-stu-id="4f711-103">Initializes the current thread in advance of subsequent profiler API calls on the same thread, so that deadlock can be avoided.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f711-104">構文</span><span class="sxs-lookup"><span data-stu-id="4f711-104">Syntax</span></span>  
  
```cpp  
HRESULT InitializeCurrentThread ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="4f711-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="4f711-105">Remarks</span></span>  
 <span data-ttu-id="4f711-106">中断されたスレッド`InitializeCurrentThread`がある間は、profiler API を呼び出すスレッドでを呼び出すことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4f711-106">We recommend that you call `InitializeCurrentThread` on any thread that will call a profiler API while there are suspended threads.</span></span> <span data-ttu-id="4f711-107">このメソッドは、通常、 [ICorProfilerInfo2::D ostacksnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md)メソッドを呼び出して、ターゲットスレッドが中断されている間にスタックウォークを実行する独自のスレッドを作成する、サンプリングプロファイラーによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="4f711-107">This method is typically used by sampling profilers that create their own thread to call the [ICorProfilerInfo2::DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) method to perform stack walks while the target thread is suspended.</span></span> <span data-ttu-id="4f711-108">プロファイラーで`InitializeCurrentThread`は、最初にサンプリングスレッドを作成するときにを呼び出すことによって、他のスレッドがない場合に、CLR がの`DoStackSnapshot`最初の呼び出し時に実行するような、スレッドごとの遅延初期化を安全に行うことができます。状態.</span><span class="sxs-lookup"><span data-stu-id="4f711-108">By calling `InitializeCurrentThread` once when the profiler first creates the sampling thread, profilers can ensure that lazy per-thread initialization that the CLR would otherwise perform during the first call to `DoStackSnapshot` can now occur safely when no other threads are suspended.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4f711-109">`InitializeCurrentThread`は、ロックを受け取るタスクを完了するために事前に初期化し、デッドロックが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4f711-109">`InitializeCurrentThread` does the initialization in advance to finish tasks that take locks, and may deadlock.</span></span> <span data-ttu-id="4f711-110">中断`InitializeCurrentThread`されたスレッドが存在しない場合にのみ、を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="4f711-110">Call `InitializeCurrentThread` only when there are no suspended threads.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f711-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="4f711-111">Requirements</span></span>  
 <span data-ttu-id="4f711-112">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f711-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f711-113">**ヘッダー:** Corprof.idl、Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="4f711-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4f711-114">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="4f711-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4f711-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f711-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f711-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="4f711-116">See also</span></span>

- [<span data-ttu-id="4f711-117">ICorProfilerInfo4 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4f711-117">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
- [<span data-ttu-id="4f711-118">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="4f711-118">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="4f711-119">プロファイル</span><span class="sxs-lookup"><span data-stu-id="4f711-119">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
