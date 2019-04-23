---
title: ICorProfilerCallback::AssemblyLoadStarted メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AssemblyLoadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AssemblyLoadStarted
helpviewer_keywords:
- ICorProfilerCallback::AssemblyLoadStarted method [.NET Framework profiling]
- AssemblyLoadStarted method [.NET Framework profiling]
ms.assetid: 67e8209d-a0ca-4118-a6e6-c1ee0abc2221
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a96a2a0d6e4bc48a46850aeaadd17c2669419cef
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59219357"
---
# <a name="icorprofilercallbackassemblyloadstarted-method"></a><span data-ttu-id="c9bbd-102">ICorProfilerCallback::AssemblyLoadStarted メソッド</span><span class="sxs-lookup"><span data-stu-id="c9bbd-102">ICorProfilerCallback::AssemblyLoadStarted Method</span></span>
<span data-ttu-id="c9bbd-103">アセンブリが読み込まれていることをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="c9bbd-103">Notifies the profiler that an assembly is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9bbd-104">構文</span><span class="sxs-lookup"><span data-stu-id="c9bbd-104">Syntax</span></span>  
  
```  
HRESULT AssemblyLoadStarted(  
    [in] AssemblyID assemblyId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c9bbd-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c9bbd-105">Parameters</span></span>  
 `assemblyId`  
 <span data-ttu-id="c9bbd-106">[in]読み込まれているアセンブリを識別します。</span><span class="sxs-lookup"><span data-stu-id="c9bbd-106">[in] Identifies the assembly that is being loaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c9bbd-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="c9bbd-107">Remarks</span></span>  
 <span data-ttu-id="c9bbd-108">値`assemblyId`まで情報の要求に対して無効です、 [icorprofilercallback::assemblyloadfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyloadfinished-method.md)メソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="c9bbd-108">The value of `assemblyId` is not valid for an information request until the [ICorProfilerCallback::AssemblyLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c9bbd-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="c9bbd-109">Requirements</span></span>  
 <span data-ttu-id="c9bbd-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c9bbd-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c9bbd-111">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c9bbd-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c9bbd-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c9bbd-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c9bbd-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c9bbd-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9bbd-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="c9bbd-114">See also</span></span>

- [<span data-ttu-id="c9bbd-115">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c9bbd-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
