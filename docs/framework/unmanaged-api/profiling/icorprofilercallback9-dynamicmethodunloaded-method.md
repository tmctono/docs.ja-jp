---
title: ICorProfilerCallback9::DynamicMethodUnloaded メソッド
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback9.DynamicMethodUnloaded
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 96cdfb79c1573648173305d6ee789aa8db030ff8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59211011"
---
# <a name="icorprofilercallback9dynamicmethodunloaded-method"></a><span data-ttu-id="e9c8f-102">ICorProfilerCallback9::DynamicMethodUnloaded メソッド</span><span class="sxs-lookup"><span data-stu-id="e9c8f-102">ICorProfilerCallback9::DynamicMethodUnloaded Method</span></span>
<span data-ttu-id="e9c8f-103">[.NET Framework 4.7.2 以降のバージョンでサポートされます]</span><span class="sxs-lookup"><span data-stu-id="e9c8f-103">[Supported in the .NET Framework 4.7.2 and later versions]</span></span>  
  
<span data-ttu-id="e9c8f-104">動的メソッドは、ガベージ コレクションされ、その後アンロードされるたびに、プロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="e9c8f-104">Notifies the profiler whenever a dynamic method is garbage collected and subsequently unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9c8f-105">構文</span><span class="sxs-lookup"><span data-stu-id="e9c8f-105">Syntax</span></span>  
  
```  
HRESULT DynamicMethodUnloaded(  
     [in]  FunctionID  functionId
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e9c8f-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e9c8f-106">Parameters</span></span>  
<span data-ttu-id="e9c8f-107">[入力]</span><span class="sxs-lookup"><span data-stu-id="e9c8f-107">[in]</span></span> `functionId`  
<span data-ttu-id="e9c8f-108">ガベージ コレクションされ、アンロードされているメモリ内の関数の識別子。</span><span class="sxs-lookup"><span data-stu-id="e9c8f-108">The identifier of the in-memory function that has been garbage collected and unloaded.</span></span>   

## <a name="requirements"></a><span data-ttu-id="e9c8f-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="e9c8f-109">Requirements</span></span>  
 <span data-ttu-id="e9c8f-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9c8f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9c8f-111">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e9c8f-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e9c8f-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e9c8f-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="e9c8f-113">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="e9c8f-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e9c8f-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="e9c8f-114">See also</span></span>

- [<span data-ttu-id="e9c8f-115">ICorProfilerCallback8.DynamicMethodJITCompilationStarted メソッド</span><span class="sxs-lookup"><span data-stu-id="e9c8f-115">ICorProfilerCallback8.DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [<span data-ttu-id="e9c8f-116">ICorProfilerCallback8.DynamicMethodJITCompilationFinished メソッド</span><span class="sxs-lookup"><span data-stu-id="e9c8f-116">ICorProfilerCallback8.DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
- [<span data-ttu-id="e9c8f-117">ICorProfilerCallback9 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e9c8f-117">ICorProfilerCallback9 Interface</span></span>](icorprofilercallback9-interface.md)
- [<span data-ttu-id="e9c8f-118">COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS</span><span class="sxs-lookup"><span data-stu-id="e9c8f-118">COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS</span></span>](cor-prf-high-monitor-enumeration.md)
