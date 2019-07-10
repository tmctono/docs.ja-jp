---
title: ICorProfilerCallback::ClassLoadStarted メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ClassLoadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ClassLoadStarted
helpviewer_keywords:
- ICorProfilerCallback::ClassLoadStarted method [.NET Framework profiling]
- ClassLoadStarted method [.NET Framework profiling]
ms.assetid: 9f728de8-45c2-45a5-ac4a-45660bd36ecf
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 84ff6cb79abdb60a3c01c66580ed6fc10f6c137e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67762941"
---
# <a name="icorprofilercallbackclassloadstarted-method"></a><span data-ttu-id="887c5-102">ICorProfilerCallback::ClassLoadStarted メソッド</span><span class="sxs-lookup"><span data-stu-id="887c5-102">ICorProfilerCallback::ClassLoadStarted Method</span></span>
<span data-ttu-id="887c5-103">クラスが読み込まれていることをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="887c5-103">Notifies the profiler that a class is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="887c5-104">構文</span><span class="sxs-lookup"><span data-stu-id="887c5-104">Syntax</span></span>  
  
```cpp  
HRESULT ClassLoadStarted(  
    [in] ClassID classId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="887c5-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="887c5-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="887c5-106">[in]読み込まれているクラスを識別します。</span><span class="sxs-lookup"><span data-stu-id="887c5-106">[in] Identifies the class that is being loaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="887c5-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="887c5-107">Remarks</span></span>  
 <span data-ttu-id="887c5-108">値`classId`まで情報の要求に対して無効です、 [icorprofilercallback::classloadfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadfinished-method.md)メソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="887c5-108">The value of `classId` is not valid for an information request until the [ICorProfilerCallback::ClassLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="887c5-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="887c5-109">Requirements</span></span>  
 <span data-ttu-id="887c5-110">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="887c5-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="887c5-111">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="887c5-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="887c5-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="887c5-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="887c5-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="887c5-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="887c5-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="887c5-114">See also</span></span>

- [<span data-ttu-id="887c5-115">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="887c5-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
