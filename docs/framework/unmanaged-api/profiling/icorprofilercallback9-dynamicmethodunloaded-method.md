---
title: メソッドの読み取り:D
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback9.DynamicMethodUnloaded
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 0eb38c83e9ab706c96bdef971f0bf17cc096822b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177034"
---
# <a name="icorprofilercallback9dynamicmethodunloaded-method"></a><span data-ttu-id="1234a-102">メソッドの読み取り:D</span><span class="sxs-lookup"><span data-stu-id="1234a-102">ICorProfilerCallback9::DynamicMethodUnloaded Method</span></span>
<span data-ttu-id="1234a-103">[.NET Framework 4.7.2 以降のバージョンでサポートされています]</span><span class="sxs-lookup"><span data-stu-id="1234a-103">[Supported in the .NET Framework 4.7.2 and later versions]</span></span>  
  
<span data-ttu-id="1234a-104">動的メソッドがガベージ コレクションされ、その後アンロードされるたびにプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="1234a-104">Notifies the profiler whenever a dynamic method is garbage collected and subsequently unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1234a-105">構文</span><span class="sxs-lookup"><span data-stu-id="1234a-105">Syntax</span></span>  
  
```cpp  
HRESULT DynamicMethodUnloaded(  
     [in]  FunctionID  functionId
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1234a-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1234a-106">Parameters</span></span>  
<span data-ttu-id="1234a-107">[入力] `functionId`</span><span class="sxs-lookup"><span data-stu-id="1234a-107">[in] `functionId`</span></span>  
<span data-ttu-id="1234a-108">ガベージ コレクションおよびアンロードされたメモリ内関数の識別子。</span><span class="sxs-lookup"><span data-stu-id="1234a-108">The identifier of the in-memory function that has been garbage collected and unloaded.</span></span>

## <a name="requirements"></a><span data-ttu-id="1234a-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="1234a-109">Requirements</span></span>  
 <span data-ttu-id="1234a-110">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1234a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1234a-111">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1234a-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1234a-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1234a-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1234a-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="1234a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1234a-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="1234a-114">See also</span></span>

- [<span data-ttu-id="1234a-115">メソッドを開始しました。</span><span class="sxs-lookup"><span data-stu-id="1234a-115">ICorProfilerCallback8.DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [<span data-ttu-id="1234a-116">メソッドを終了しました。</span><span class="sxs-lookup"><span data-stu-id="1234a-116">ICorProfilerCallback8.DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
- [<span data-ttu-id="1234a-117">ICorProfilerCallback9 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1234a-117">ICorProfilerCallback9 Interface</span></span>](icorprofilercallback9-interface.md)
- [<span data-ttu-id="1234a-118">COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS</span><span class="sxs-lookup"><span data-stu-id="1234a-118">COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS</span></span>](cor-prf-high-monitor-enumeration.md)
