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
ms.openlocfilehash: abcbfaf803e930baaaf798986a585a7da5f9134d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780796"
---
# <a name="icorprofilerinfo4initializecurrentthread-method"></a><span data-ttu-id="87541-102">ICorProfilerInfo4::InitializeCurrentThread メソッド</span><span class="sxs-lookup"><span data-stu-id="87541-102">ICorProfilerInfo4::InitializeCurrentThread Method</span></span>
<span data-ttu-id="87541-103">後続のプロファイラー API は、デッドロックを回避するため、同じスレッドで呼び出しの前に、現在のスレッドを初期化します。</span><span class="sxs-lookup"><span data-stu-id="87541-103">Initializes the current thread in advance of subsequent profiler API calls on the same thread, so that deadlock can be avoided.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87541-104">構文</span><span class="sxs-lookup"><span data-stu-id="87541-104">Syntax</span></span>  
  
```cpp  
HRESULT InitializeCurrentThread ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="87541-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="87541-105">Remarks</span></span>  
 <span data-ttu-id="87541-106">呼び出すことをお勧めします。 `InitializeCurrentThread` API はありますが、プロファイラーを呼び出す任意のスレッドでスレッドが中断されます。</span><span class="sxs-lookup"><span data-stu-id="87541-106">We recommend that you call `InitializeCurrentThread` on any thread that will call a profiler API while there are suspended threads.</span></span> <span data-ttu-id="87541-107">このメソッドは通常を呼び出す独自のスレッドの作成サンプリング プロファイラーで使用、 [icorprofilerinfo 2::dostacksnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md)対象スレッドが中断されている間、スタックを実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="87541-107">This method is typically used by sampling profilers that create their own thread to call the [ICorProfilerInfo2::DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) method to perform stack walks while the target thread is suspended.</span></span> <span data-ttu-id="87541-108">呼び出して`InitializeCurrentThread`プロファイラーが CLR をそれ以外の場合、最初の呼び出し中に実行するスレッドごとの遅延初期化のことを確認できる場合、プロファイラーでは、まずサンプリング スレッドを作成した後`DoStackSnapshot`他のスレッドがない場合に安全に発生することができますようになりました中断されています。</span><span class="sxs-lookup"><span data-stu-id="87541-108">By calling `InitializeCurrentThread` once when the profiler first creates the sampling thread, profilers can ensure that lazy per-thread initialization that the CLR would otherwise perform during the first call to `DoStackSnapshot` can now occur safely when no other threads are suspended.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="87541-109">`InitializeCurrentThread` ロック、およびデッドロックが発生するタスクを完了するには、事前に初期化します。</span><span class="sxs-lookup"><span data-stu-id="87541-109">`InitializeCurrentThread` does the initialization in advance to finish tasks that take locks, and may deadlock.</span></span> <span data-ttu-id="87541-110">呼び出す`InitializeCurrentThread`中断されたスレッドがない場合にのみです。</span><span class="sxs-lookup"><span data-stu-id="87541-110">Call `InitializeCurrentThread` only when there are no suspended threads.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87541-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="87541-111">Requirements</span></span>  
 <span data-ttu-id="87541-112">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="87541-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87541-113">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="87541-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="87541-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="87541-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="87541-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="87541-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87541-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="87541-116">See also</span></span>

- [<span data-ttu-id="87541-117">ICorProfilerInfo4 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="87541-117">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
- [<span data-ttu-id="87541-118">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="87541-118">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="87541-119">プロファイル</span><span class="sxs-lookup"><span data-stu-id="87541-119">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
