---
title: ICorProfilerCallback8 インターフェイス
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 4516c8f9673052b521c1f0f594978236fef1e0ec
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136452"
---
# <a name="icorprofilercallback8-interface"></a><span data-ttu-id="bb10a-102">ICorProfilerCallback8 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bb10a-102">ICorProfilerCallback8 Interface</span></span>
<span data-ttu-id="bb10a-103">[.NET Framework 4.7 以降のバージョンでサポートされています]</span><span class="sxs-lookup"><span data-stu-id="bb10a-103">[Supported in the .NET Framework 4.7 and later versions]</span></span>  

 <span data-ttu-id="bb10a-104">動的メソッドの JIT コンパイルが開始および終了したことをプロファイラーに通知するために、共通言語ランタイムによって使用されるコールバックメソッドを提供する[ICorProfilerCallback7](icorprofilercallback7-interface.md)のサブクラスです。</span><span class="sxs-lookup"><span data-stu-id="bb10a-104">A subclass of [ICorProfilerCallback7](icorprofilercallback7-interface.md) that provides callback methods used by the common language runtime to notify the profiler that JIT compilation of a dynamic method has started and finished.</span></span> 
  
## <a name="methods"></a><span data-ttu-id="bb10a-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="bb10a-105">Methods</span></span>  
  
|<span data-ttu-id="bb10a-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="bb10a-106">Method</span></span>|<span data-ttu-id="bb10a-107">説明</span><span class="sxs-lookup"><span data-stu-id="bb10a-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bb10a-108">DynamicMethodJITCompilationStarted メソッド</span><span class="sxs-lookup"><span data-stu-id="bb10a-108">DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)|<span data-ttu-id="bb10a-109">動的メソッドの JIT コンパイルが開始されたことをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="bb10a-109">Notifies the profiler that JIT compilation of a dynamic method has started.</span></span>|  
|[<span data-ttu-id="bb10a-110">DynamicMethodJITCompilationFinished メソッド</span><span class="sxs-lookup"><span data-stu-id="bb10a-110">DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)|<span data-ttu-id="bb10a-111">動的メソッドの JIT コンパイルが終了したことをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="bb10a-111">Notifies the profiler that JIT compilation of a dynamic method has finished.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bb10a-112">［要件］</span><span class="sxs-lookup"><span data-stu-id="bb10a-112">Requirements</span></span>  
 <span data-ttu-id="bb10a-113">**:** 「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb10a-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb10a-114">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bb10a-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
<span data-ttu-id="bb10a-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="bb10a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="bb10a-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="bb10a-116">See also</span></span>

- [<span data-ttu-id="bb10a-117">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="bb10a-117">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="bb10a-118">ICorProfilerCallback9 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bb10a-118">ICorProfilerCallback9 Interface</span></span>](icorprofilercallback9-interface.md)
