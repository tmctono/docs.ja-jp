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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3a45c757a9176c77c7dbf58333b66d9b26514265
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471213"
---
# <a name="icorprofilercallbackassemblyunloadstarted-method"></a><span data-ttu-id="5af75-102">ICorProfilerCallback::AssemblyUnloadStarted メソッド</span><span class="sxs-lookup"><span data-stu-id="5af75-102">ICorProfilerCallback::AssemblyUnloadStarted Method</span></span>
<span data-ttu-id="5af75-103">アセンブリがアンロードされることをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="5af75-103">Notifies the profiler that an assembly is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5af75-104">構文</span><span class="sxs-lookup"><span data-stu-id="5af75-104">Syntax</span></span>  
  
```  
HRESULT AssemblyUnloadStarted(  
    [in] AssemblyID assemblyId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5af75-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5af75-105">Parameters</span></span>  
 `assemblyId`  
 <span data-ttu-id="5af75-106">[in]アンロードされているアセンブリを識別します。</span><span class="sxs-lookup"><span data-stu-id="5af75-106">[in] Identifies the assembly that is being unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5af75-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="5af75-107">Remarks</span></span>  
 <span data-ttu-id="5af75-108">値`assemblyId`は後の情報の要求は無効です、`AssemblyUnloadStarted`メソッドを返します。-これはこのアセンブリに関する情報を取得、プロファイラーの最後のチャンスです。</span><span class="sxs-lookup"><span data-stu-id="5af75-108">The value of `assemblyId` is not valid for an information request after the `AssemblyUnloadStarted` method returns — this is the profiler's last chance to get information about this assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5af75-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="5af75-109">Requirements</span></span>  
 <span data-ttu-id="5af75-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5af75-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5af75-111">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5af75-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5af75-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5af75-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5af75-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5af75-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5af75-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="5af75-114">See also</span></span>
- [<span data-ttu-id="5af75-115">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5af75-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="5af75-116">AssemblyUnloadFinished メソッド</span><span class="sxs-lookup"><span data-stu-id="5af75-116">AssemblyUnloadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyunloadfinished-method.md)
