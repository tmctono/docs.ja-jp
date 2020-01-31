---
title: ICorProfilerCallback::AssemblyUnloadStarted メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AssemblyUnloadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AssemblyUnloadStarted
helpviewer_keywords:
- ICorProfilerCallback::AssemblyUnloadStarted method [.NET Framework profiling]
- AssemblyUnloadStarted method [.NET Framework profiling]
ms.assetid: 6e47b7e5-0335-4dd3-8c42-d3c07d62b102
topic_type:
- apiref
ms.openlocfilehash: 0a677e33950f178b916a5e9e9cbb7bd918c1349b
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866612"
---
# <a name="icorprofilercallbackassemblyunloadstarted-method"></a><span data-ttu-id="1c201-102">ICorProfilerCallback::AssemblyUnloadStarted メソッド</span><span class="sxs-lookup"><span data-stu-id="1c201-102">ICorProfilerCallback::AssemblyUnloadStarted Method</span></span>
<span data-ttu-id="1c201-103">アセンブリがアンロードされていることをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="1c201-103">Notifies the profiler that an assembly is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c201-104">構文</span><span class="sxs-lookup"><span data-stu-id="1c201-104">Syntax</span></span>  
  
```cpp  
HRESULT AssemblyUnloadStarted(  
    [in] AssemblyID assemblyId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1c201-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1c201-105">Parameters</span></span>

- `assemblyId`

  <span data-ttu-id="1c201-106">の \[] アンロードされるアセンブリを識別します。</span><span class="sxs-lookup"><span data-stu-id="1c201-106">\[in] Identifies the assembly that is being unloaded.</span></span>

## <a name="remarks"></a><span data-ttu-id="1c201-107">コメント</span><span class="sxs-lookup"><span data-stu-id="1c201-107">Remarks</span></span>  
 <span data-ttu-id="1c201-108">`assemblyId` の値は、`AssemblyUnloadStarted` メソッドから返された後の情報要求に対して無効です。これは、このアセンブリに関する情報を取得するためのプロファイラーの最後の機会です。</span><span class="sxs-lookup"><span data-stu-id="1c201-108">The value of `assemblyId` is not valid for an information request after the `AssemblyUnloadStarted` method returns — this is the profiler's last chance to get information about this assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c201-109">要件</span><span class="sxs-lookup"><span data-stu-id="1c201-109">Requirements</span></span>  
 <span data-ttu-id="1c201-110">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c201-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c201-111">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1c201-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1c201-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1c201-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1c201-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c201-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c201-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="1c201-114">See also</span></span>

- [<span data-ttu-id="1c201-115">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1c201-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="1c201-116">AssemblyUnloadFinished メソッド</span><span class="sxs-lookup"><span data-stu-id="1c201-116">AssemblyUnloadFinished Method</span></span>](icorprofilercallback-assemblyunloadfinished-method.md)
