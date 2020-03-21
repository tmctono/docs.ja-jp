---
title: ICorProfilerCallback::ModuleUnloadStarted メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ModuleUnloadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ModuleUnloadStarted
helpviewer_keywords:
- ModuleUnloadStarted method [.NET Framework profiling]
- ICorProfilerCallback::ModuleUnloadStarted method [.NET Framework profiling]
ms.assetid: 2debcaab-6005-4245-afdb-4268bb7e74bd
topic_type:
- apiref
ms.openlocfilehash: fcfdddbd5316c098754ea7b0d4714b050c64fe55
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175149"
---
# <a name="icorprofilercallbackmoduleunloadstarted-method"></a><span data-ttu-id="56d4e-102">ICorProfilerCallback::ModuleUnloadStarted メソッド</span><span class="sxs-lookup"><span data-stu-id="56d4e-102">ICorProfilerCallback::ModuleUnloadStarted Method</span></span>
<span data-ttu-id="56d4e-103">モジュールがアンロードされていることをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="56d4e-103">Notifies the profiler that a module is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56d4e-104">構文</span><span class="sxs-lookup"><span data-stu-id="56d4e-104">Syntax</span></span>  
  
```cpp  
HRESULT ModuleUnloadStarted(  
    [in] ModuleID moduleId);
```  
  
## <a name="parameters"></a><span data-ttu-id="56d4e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="56d4e-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="56d4e-106">[in]アンロードされるモジュールの ID。</span><span class="sxs-lookup"><span data-stu-id="56d4e-106">[in] The ID of the module that is being unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="56d4e-107">解説</span><span class="sxs-lookup"><span data-stu-id="56d4e-107">Remarks</span></span>  
 <span data-ttu-id="56d4e-108">メソッド`moduleId`が返された後`ModuleUnloadStarted`の情報要求の値は無効です。</span><span class="sxs-lookup"><span data-stu-id="56d4e-108">The value of `moduleId` is not valid for an information request after the `ModuleUnloadStarted` method returns — this is the profiler's last chance to get information about this module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="56d4e-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="56d4e-109">Requirements</span></span>  
 <span data-ttu-id="56d4e-110">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="56d4e-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="56d4e-111">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="56d4e-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="56d4e-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="56d4e-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="56d4e-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="56d4e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56d4e-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="56d4e-114">See also</span></span>

- [<span data-ttu-id="56d4e-115">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="56d4e-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="56d4e-116">ModuleUnloadFinished メソッド</span><span class="sxs-lookup"><span data-stu-id="56d4e-116">ModuleUnloadFinished Method</span></span>](icorprofilercallback-moduleunloadfinished-method.md)
