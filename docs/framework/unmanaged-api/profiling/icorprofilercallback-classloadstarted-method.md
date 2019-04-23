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
ms.openlocfilehash: db7a033944272756a739dec39d4df11fde1d48b3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59178608"
---
# <a name="icorprofilercallbackclassloadstarted-method"></a><span data-ttu-id="f90c6-102">ICorProfilerCallback::ClassLoadStarted メソッド</span><span class="sxs-lookup"><span data-stu-id="f90c6-102">ICorProfilerCallback::ClassLoadStarted Method</span></span>
<span data-ttu-id="f90c6-103">クラスが読み込まれていることをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="f90c6-103">Notifies the profiler that a class is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f90c6-104">構文</span><span class="sxs-lookup"><span data-stu-id="f90c6-104">Syntax</span></span>  
  
```  
HRESULT ClassLoadStarted(  
    [in] ClassID classId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f90c6-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f90c6-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="f90c6-106">[in]読み込まれているクラスを識別します。</span><span class="sxs-lookup"><span data-stu-id="f90c6-106">[in] Identifies the class that is being loaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f90c6-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="f90c6-107">Remarks</span></span>  
 <span data-ttu-id="f90c6-108">値`classId`まで情報の要求に対して無効です、 [icorprofilercallback::classloadfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadfinished-method.md)メソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="f90c6-108">The value of `classId` is not valid for an information request until the [ICorProfilerCallback::ClassLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f90c6-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="f90c6-109">Requirements</span></span>  
 <span data-ttu-id="f90c6-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f90c6-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f90c6-111">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f90c6-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f90c6-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f90c6-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f90c6-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f90c6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f90c6-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="f90c6-114">See also</span></span>

- [<span data-ttu-id="f90c6-115">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f90c6-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
