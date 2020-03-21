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
ms.openlocfilehash: 617b27923e96d9abc62ccbf158b076c6e45b20a8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175097"
---
# <a name="icorprofilercallback8-interface"></a><span data-ttu-id="af08f-102">ICorProfilerCallback8 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="af08f-102">ICorProfilerCallback8 Interface</span></span>
<span data-ttu-id="af08f-103">[.NET Framework 4.7 以降のバージョンでサポートされています]</span><span class="sxs-lookup"><span data-stu-id="af08f-103">[Supported in the .NET Framework 4.7 and later versions]</span></span>  

 <span data-ttu-id="af08f-104">動的メソッドの JIT コンパイルが開始および終了したことをプロファイラーに通知するために共通言語ランタイムによって使用されるコールバック メソッドを提供する[ICorProfilerCallback7](icorprofilercallback7-interface.md)のサブクラス。</span><span class="sxs-lookup"><span data-stu-id="af08f-104">A subclass of [ICorProfilerCallback7](icorprofilercallback7-interface.md) that provides callback methods used by the common language runtime to notify the profiler that JIT compilation of a dynamic method has started and finished.</span></span>
  
## <a name="methods"></a><span data-ttu-id="af08f-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="af08f-105">Methods</span></span>  
  
|<span data-ttu-id="af08f-106">Method</span><span class="sxs-lookup"><span data-stu-id="af08f-106">Method</span></span>|<span data-ttu-id="af08f-107">説明</span><span class="sxs-lookup"><span data-stu-id="af08f-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="af08f-108">DynamicMethodJITCompilationStarted メソッド</span><span class="sxs-lookup"><span data-stu-id="af08f-108">DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)|<span data-ttu-id="af08f-109">動的メソッドの JIT コンパイルが開始されたことをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="af08f-109">Notifies the profiler that JIT compilation of a dynamic method has started.</span></span>|  
|[<span data-ttu-id="af08f-110">DynamicMethodJITCompilationFinished メソッド</span><span class="sxs-lookup"><span data-stu-id="af08f-110">DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)|<span data-ttu-id="af08f-111">動的メソッドの JIT コンパイルが完了したことをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="af08f-111">Notifies the profiler that JIT compilation of a dynamic method has finished.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="af08f-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="af08f-112">Requirements</span></span>  
 <span data-ttu-id="af08f-113">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="af08f-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af08f-114">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="af08f-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
<span data-ttu-id="af08f-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="af08f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="af08f-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="af08f-116">See also</span></span>

- [<span data-ttu-id="af08f-117">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="af08f-117">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="af08f-118">ICorProfilerCallback9 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="af08f-118">ICorProfilerCallback9 Interface</span></span>](icorprofilercallback9-interface.md)
