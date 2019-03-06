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
ms.openlocfilehash: 7bc4b1a58bba592cfff408f034fb19c0c27616c3
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57480547"
---
# <a name="icorprofilercallbackmoduleloadstarted-method"></a><span data-ttu-id="9b884-102">ICorProfilerCallback::ModuleLoadStarted メソッド</span><span class="sxs-lookup"><span data-stu-id="9b884-102">ICorProfilerCallback::ModuleLoadStarted Method</span></span>
<span data-ttu-id="9b884-103">モジュールが読み込まれていることをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="9b884-103">Notifies the profiler that a module is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b884-104">構文</span><span class="sxs-lookup"><span data-stu-id="9b884-104">Syntax</span></span>  
  
```  
HRESULT ModuleLoadStarted(  
    [in] ModuleID moduleId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9b884-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9b884-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="9b884-106">[in]読み込まれているモジュールの ID。</span><span class="sxs-lookup"><span data-stu-id="9b884-106">[in] The ID of the module that is being loaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9b884-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="9b884-107">Remarks</span></span>  
 <span data-ttu-id="9b884-108">値`moduleId`まで情報の要求に対して無効です、 [icorprofilercallback::moduleloadfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)メソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="9b884-108">The value of `moduleId` is not valid for an information request until the [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b884-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="9b884-109">Requirements</span></span>  
 <span data-ttu-id="9b884-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9b884-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b884-111">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9b884-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9b884-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9b884-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9b884-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b884-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b884-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="9b884-114">See also</span></span>
- [<span data-ttu-id="9b884-115">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9b884-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
