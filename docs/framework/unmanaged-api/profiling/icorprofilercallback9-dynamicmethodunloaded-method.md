---
title: ICorProfilerCallback9::D ynamicMethodUnloaded メソッド
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback9.DynamicMethodUnloaded
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 2391ad854b17ec117940a3d3568c40d6cf7f4725
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84498974"
---
# <a name="icorprofilercallback9dynamicmethodunloaded-method"></a><span data-ttu-id="24ea9-102">ICorProfilerCallback9::D ynamicMethodUnloaded メソッド</span><span class="sxs-lookup"><span data-stu-id="24ea9-102">ICorProfilerCallback9::DynamicMethodUnloaded Method</span></span>
<span data-ttu-id="24ea9-103">[.NET Framework 4.7.2 以降のバージョンでサポートされています]</span><span class="sxs-lookup"><span data-stu-id="24ea9-103">[Supported in the .NET Framework 4.7.2 and later versions]</span></span>  
  
<span data-ttu-id="24ea9-104">動的メソッドがガベージコレクションされ、その後アンロードされるたびに、プロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="24ea9-104">Notifies the profiler whenever a dynamic method is garbage collected and subsequently unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24ea9-105">構文</span><span class="sxs-lookup"><span data-stu-id="24ea9-105">Syntax</span></span>  
  
```cpp  
HRESULT DynamicMethodUnloaded(  
     [in]  FunctionID  functionId
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="24ea9-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="24ea9-106">Parameters</span></span>  
<span data-ttu-id="24ea9-107">[入力] `functionId`</span><span class="sxs-lookup"><span data-stu-id="24ea9-107">[in] `functionId`</span></span>  
<span data-ttu-id="24ea9-108">ガベージコレクションおよびアンロードされたメモリ内の関数の識別子。</span><span class="sxs-lookup"><span data-stu-id="24ea9-108">The identifier of the in-memory function that has been garbage collected and unloaded.</span></span>

## <a name="requirements"></a><span data-ttu-id="24ea9-109">要件</span><span class="sxs-lookup"><span data-stu-id="24ea9-109">Requirements</span></span>  
 <span data-ttu-id="24ea9-110">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="24ea9-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="24ea9-111">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="24ea9-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="24ea9-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="24ea9-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="24ea9-113">**.NET Framework のバージョン:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="24ea9-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24ea9-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="24ea9-114">See also</span></span>

- [<span data-ttu-id="24ea9-115">ICorProfilerCallback8 DynamicMethodJITCompilationStarted メソッド</span><span class="sxs-lookup"><span data-stu-id="24ea9-115">ICorProfilerCallback8.DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [<span data-ttu-id="24ea9-116">ICorProfilerCallback8 DynamicMethodJITCompilationFinished メソッド</span><span class="sxs-lookup"><span data-stu-id="24ea9-116">ICorProfilerCallback8.DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
- [<span data-ttu-id="24ea9-117">ICorProfilerCallback9 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="24ea9-117">ICorProfilerCallback9 Interface</span></span>](icorprofilercallback9-interface.md)
- [<span data-ttu-id="24ea9-118">COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS</span><span class="sxs-lookup"><span data-stu-id="24ea9-118">COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS</span></span>](cor-prf-high-monitor-enumeration.md)
