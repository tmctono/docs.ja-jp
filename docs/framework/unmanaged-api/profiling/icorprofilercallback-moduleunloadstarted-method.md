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
ms.openlocfilehash: f0000e9b063022e828e52b9b940ec6f4e0ce4165
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445905"
---
# <a name="icorprofilercallbackmoduleunloadstarted-method"></a><span data-ttu-id="53a31-102">ICorProfilerCallback::ModuleUnloadStarted メソッド</span><span class="sxs-lookup"><span data-stu-id="53a31-102">ICorProfilerCallback::ModuleUnloadStarted Method</span></span>
<span data-ttu-id="53a31-103">モジュールがアンロードされていることをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="53a31-103">Notifies the profiler that a module is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53a31-104">構文</span><span class="sxs-lookup"><span data-stu-id="53a31-104">Syntax</span></span>  
  
```cpp  
HRESULT ModuleUnloadStarted(  
    [in] ModuleID moduleId);   
```  
  
## <a name="parameters"></a><span data-ttu-id="53a31-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="53a31-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="53a31-106">からアンロードされるモジュールの ID。</span><span class="sxs-lookup"><span data-stu-id="53a31-106">[in] The ID of the module that is being unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="53a31-107">コメント</span><span class="sxs-lookup"><span data-stu-id="53a31-107">Remarks</span></span>  
 <span data-ttu-id="53a31-108">`moduleId` の値は、`ModuleUnloadStarted` メソッドから制御が戻った後の情報要求に対して無効です。これは、このモジュールに関する情報を取得するためのプロファイラーの最後の機会です。</span><span class="sxs-lookup"><span data-stu-id="53a31-108">The value of `moduleId` is not valid for an information request after the `ModuleUnloadStarted` method returns — this is the profiler's last chance to get information about this module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="53a31-109">要件</span><span class="sxs-lookup"><span data-stu-id="53a31-109">Requirements</span></span>  
 <span data-ttu-id="53a31-110">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="53a31-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="53a31-111">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="53a31-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="53a31-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="53a31-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="53a31-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="53a31-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53a31-114">参照</span><span class="sxs-lookup"><span data-stu-id="53a31-114">See also</span></span>

- [<span data-ttu-id="53a31-115">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="53a31-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="53a31-116">ModuleUnloadFinished メソッド</span><span class="sxs-lookup"><span data-stu-id="53a31-116">ModuleUnloadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleunloadfinished-method.md)
