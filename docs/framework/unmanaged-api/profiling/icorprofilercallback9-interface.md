---
title: ICorProfilerCallback9 インターフェイス
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback9
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e1711def5e2aa41fd63912361ef8250ad160fb88
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61991992"
---
# <a name="icorprofilercallback9-interface"></a><span data-ttu-id="ae32c-102">ICorProfilerCallback9 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ae32c-102">ICorProfilerCallback9 Interface</span></span>
<span data-ttu-id="ae32c-103">[.NET Framework 4.7.2 以降のバージョンでサポートされます]</span><span class="sxs-lookup"><span data-stu-id="ae32c-103">[Supported in the .NET Framework 4.7.2 and later versions]</span></span>  

 <span data-ttu-id="ae32c-104">サブクラス[ICorProfilerCallback8](icorprofilercallback8-interface.md)に動的メソッドがガベージ コレクションされ、その後にアンロードされたことをプロファイラーに通知する、共通言語ランタイムによって使用されるコールバック メソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="ae32c-104">A subclass of [ICorProfilerCallback8](icorprofilercallback8-interface.md) that provides a callback method used by the common language runtime to notify the profiler that a dynamic method has been garbage collected and subsequently unloaded.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ae32c-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="ae32c-105">Methods</span></span>  
  
|<span data-ttu-id="ae32c-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="ae32c-106">Method</span></span>|<span data-ttu-id="ae32c-107">説明</span><span class="sxs-lookup"><span data-stu-id="ae32c-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ae32c-108">DynamicMethodUnloaded メソッド</span><span class="sxs-lookup"><span data-stu-id="ae32c-108">DynamicMethodUnloaded Method</span></span>](ICorProfilerCallback9-dynamicmethodunloaded-method.md)|<span data-ttu-id="ae32c-109">動的メソッドがガベージ コレクションされ、その後にアンロードされたことをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="ae32c-109">Notifies the profiler that a dynamic method has been garbage collected and subsequently unloaded.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ae32c-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="ae32c-110">Requirements</span></span>  
 <span data-ttu-id="ae32c-111">**プラットフォーム:**[システム要件](../../get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae32c-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae32c-112">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ae32c-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
<span data-ttu-id="ae32c-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="ae32c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="ae32c-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="ae32c-114">See also</span></span>

- [<span data-ttu-id="ae32c-115">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="ae32c-115">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="ae32c-116">ICorProfilerCallback8 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ae32c-116">ICorProfilerCallback8 Interface</span></span>](icorprofilercallback9-interface.md)
- [<span data-ttu-id="ae32c-117">ICorProfilerCallback8.DynamicMethodJITCompilationStarted メソッド</span><span class="sxs-lookup"><span data-stu-id="ae32c-117">ICorProfilerCallback8.DynamicMethodJITCompilationStarted method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [<span data-ttu-id="ae32c-118">ICorProfilerCallback8.DynamicMethodJITCompilationFinished メソッド</span><span class="sxs-lookup"><span data-stu-id="ae32c-118">ICorProfilerCallback8.DynamicMethodJITCompilationFinished method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
