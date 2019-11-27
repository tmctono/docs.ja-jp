---
title: ICorProfilerCallback2::FinalizeableObjectQueued メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.FinalizeableObjectQueued
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::FinalizeableObjectQueued
helpviewer_keywords:
- FinalizeableObjectQueued method [.NET Framework profiling]
- ICorProfilerCallback2::FinalizeableObjectQueued method [.NET Framework profiling]
ms.assetid: 92d76893-683c-475d-9996-5bff03cdb10f
topic_type:
- apiref
ms.openlocfilehash: ade0ba0517e47e9500683836b87d7a8ac1dfcfdb
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74439850"
---
# <a name="icorprofilercallback2finalizeableobjectqueued-method"></a><span data-ttu-id="b87ba-102">ICorProfilerCallback2::FinalizeableObjectQueued メソッド</span><span class="sxs-lookup"><span data-stu-id="b87ba-102">ICorProfilerCallback2::FinalizeableObjectQueued Method</span></span>
<span data-ttu-id="b87ba-103">ファイナライザーを持つオブジェクトが `Finalize` メソッドを実行するためにファイナライザースレッドに対してキューに登録されていることをコードプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="b87ba-103">Notifies the code profiler that an object with a finalizer has been queued to the finalizer thread for execution of its `Finalize` method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b87ba-104">構文</span><span class="sxs-lookup"><span data-stu-id="b87ba-104">Syntax</span></span>  
  
```cpp  
HRESULT FinalizeableObjectQueued(  
    [in] DWORD finalizerFlags,  
    [in] ObjectID objectID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b87ba-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b87ba-105">Parameters</span></span>  
 `finalizerFlags`  
 <span data-ttu-id="b87ba-106">からファイナライザーの側面を説明する[COR_PRF_FINALIZER_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-finalizer-flags-enumeration.md)列挙体の値。</span><span class="sxs-lookup"><span data-stu-id="b87ba-106">[in] A value of the [COR_PRF_FINALIZER_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-finalizer-flags-enumeration.md) enumeration that describes aspects of the finalizer.</span></span>  
  
 `objectID`  
 <span data-ttu-id="b87ba-107">からキューに登録されたオブジェクトの ID。</span><span class="sxs-lookup"><span data-stu-id="b87ba-107">[in] The ID of the object that has been queued.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b87ba-108">要件</span><span class="sxs-lookup"><span data-stu-id="b87ba-108">Requirements</span></span>  
 <span data-ttu-id="b87ba-109">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b87ba-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b87ba-110">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b87ba-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b87ba-111">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b87ba-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b87ba-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b87ba-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b87ba-113">参照</span><span class="sxs-lookup"><span data-stu-id="b87ba-113">See also</span></span>

- [<span data-ttu-id="b87ba-114">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b87ba-114">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="b87ba-115">ICorProfilerCallback2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b87ba-115">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
