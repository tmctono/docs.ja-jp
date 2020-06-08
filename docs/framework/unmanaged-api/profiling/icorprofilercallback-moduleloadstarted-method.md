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
ms.openlocfilehash: a04f72fff9a88c8689821131b08b35500c23b3d9
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503355"
---
# <a name="icorprofilercallbackmoduleloadstarted-method"></a><span data-ttu-id="ea73c-102">ICorProfilerCallback::ModuleLoadStarted メソッド</span><span class="sxs-lookup"><span data-stu-id="ea73c-102">ICorProfilerCallback::ModuleLoadStarted Method</span></span>
<span data-ttu-id="ea73c-103">モジュールが読み込まれていることをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="ea73c-103">Notifies the profiler that a module is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea73c-104">構文</span><span class="sxs-lookup"><span data-stu-id="ea73c-104">Syntax</span></span>  
  
```cpp  
HRESULT ModuleLoadStarted(  
    [in] ModuleID moduleId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ea73c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ea73c-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="ea73c-106">から読み込まれているモジュールの ID。</span><span class="sxs-lookup"><span data-stu-id="ea73c-106">[in] The ID of the module that is being loaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ea73c-107">解説</span><span class="sxs-lookup"><span data-stu-id="ea73c-107">Remarks</span></span>  
 <span data-ttu-id="ea73c-108">の値は、 `moduleId` [ICorProfilerCallback:: ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md)メソッドが呼び出されるまで、情報要求に対して無効です。</span><span class="sxs-lookup"><span data-stu-id="ea73c-108">The value of `moduleId` is not valid for an information request until the [ICorProfilerCallback::ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea73c-109">要件</span><span class="sxs-lookup"><span data-stu-id="ea73c-109">Requirements</span></span>  
 <span data-ttu-id="ea73c-110">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ea73c-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea73c-111">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ea73c-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ea73c-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ea73c-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ea73c-113">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea73c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea73c-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="ea73c-114">See also</span></span>

- [<span data-ttu-id="ea73c-115">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ea73c-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
