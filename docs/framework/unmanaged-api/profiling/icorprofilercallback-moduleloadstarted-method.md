---
title: ICorProfilerCallback::ModuleLoadStarted メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ModuleLoadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ModuleLoadStarted
helpviewer_keywords:
- ModuleLoadStarted method [.NET Framework profiling]
- ICorProfilerCallback::ModuleLoadStarted method [.NET Framework profiling]
ms.assetid: 9cd2fe75-408a-400f-a6b1-9979624a2fe2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3503aa1eb86246365e31f52313893ad8713f5748
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61992187"
---
# <a name="icorprofilercallbackmoduleloadstarted-method"></a><span data-ttu-id="63d32-102">ICorProfilerCallback::ModuleLoadStarted メソッド</span><span class="sxs-lookup"><span data-stu-id="63d32-102">ICorProfilerCallback::ModuleLoadStarted Method</span></span>
<span data-ttu-id="63d32-103">モジュールが読み込まれていることをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="63d32-103">Notifies the profiler that a module is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63d32-104">構文</span><span class="sxs-lookup"><span data-stu-id="63d32-104">Syntax</span></span>  
  
```  
HRESULT ModuleLoadStarted(  
    [in] ModuleID moduleId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="63d32-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="63d32-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="63d32-106">[in]読み込まれているモジュールの ID。</span><span class="sxs-lookup"><span data-stu-id="63d32-106">[in] The ID of the module that is being loaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="63d32-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="63d32-107">Remarks</span></span>  
 <span data-ttu-id="63d32-108">値`moduleId`まで情報の要求に対して無効です、 [icorprofilercallback::moduleloadfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)メソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="63d32-108">The value of `moduleId` is not valid for an information request until the [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63d32-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="63d32-109">Requirements</span></span>  
 <span data-ttu-id="63d32-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="63d32-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63d32-111">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="63d32-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="63d32-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="63d32-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="63d32-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63d32-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63d32-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="63d32-114">See also</span></span>

- [<span data-ttu-id="63d32-115">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="63d32-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
