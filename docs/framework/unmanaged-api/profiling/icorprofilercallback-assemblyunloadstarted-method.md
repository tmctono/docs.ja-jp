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
ms.openlocfilehash: 80054a8292c69b957664cb3573b0a8694c7f9fd2
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500404"
---
# <a name="icorprofilercallbackassemblyunloadstarted-method"></a><span data-ttu-id="6b081-102">ICorProfilerCallback::AssemblyUnloadStarted メソッド</span><span class="sxs-lookup"><span data-stu-id="6b081-102">ICorProfilerCallback::AssemblyUnloadStarted Method</span></span>
<span data-ttu-id="6b081-103">アセンブリがアンロードされていることをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="6b081-103">Notifies the profiler that an assembly is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b081-104">構文</span><span class="sxs-lookup"><span data-stu-id="6b081-104">Syntax</span></span>  
  
```cpp  
HRESULT AssemblyUnloadStarted(  
    [in] AssemblyID assemblyId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6b081-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6b081-105">Parameters</span></span>

- `assemblyId`

  <span data-ttu-id="6b081-106">\[in] は、アンロードされるアセンブリを識別します。</span><span class="sxs-lookup"><span data-stu-id="6b081-106">\[in] Identifies the assembly that is being unloaded.</span></span>

## <a name="remarks"></a><span data-ttu-id="6b081-107">解説</span><span class="sxs-lookup"><span data-stu-id="6b081-107">Remarks</span></span>  
 <span data-ttu-id="6b081-108">`assemblyId`メソッドから制御が戻った後、の値は情報要求に対して無効です `AssemblyUnloadStarted` 。これは、このアセンブリに関する情報を取得する最後の機会です。</span><span class="sxs-lookup"><span data-stu-id="6b081-108">The value of `assemblyId` is not valid for an information request after the `AssemblyUnloadStarted` method returns — this is the profiler's last chance to get information about this assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b081-109">要件</span><span class="sxs-lookup"><span data-stu-id="6b081-109">Requirements</span></span>  
 <span data-ttu-id="6b081-110">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b081-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b081-111">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6b081-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6b081-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6b081-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6b081-113">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6b081-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b081-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="6b081-114">See also</span></span>

- [<span data-ttu-id="6b081-115">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6b081-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="6b081-116">AssemblyUnloadFinished メソッド</span><span class="sxs-lookup"><span data-stu-id="6b081-116">AssemblyUnloadFinished Method</span></span>](icorprofilercallback-assemblyunloadfinished-method.md)
