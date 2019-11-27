---
title: ICorProfilerCallback::ModuleUnloadFinished メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ModuleUnloadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ModuleUnloadFinished
helpviewer_keywords:
- ModuleUnloadFinished method [.NET Framework profiling]
- ICorProfilerCallback::ModuleUnloadFinished method [.NET Framework profiling]
ms.assetid: 185e3327-9f9c-44bc-8a5c-febea9a6bb5b
topic_type:
- apiref
ms.openlocfilehash: 40cb666c47c690dc930ec2cb7f6c89662464780e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445911"
---
# <a name="icorprofilercallbackmoduleunloadfinished-method"></a><span data-ttu-id="ef714-102">ICorProfilerCallback::ModuleUnloadFinished メソッド</span><span class="sxs-lookup"><span data-stu-id="ef714-102">ICorProfilerCallback::ModuleUnloadFinished Method</span></span>
<span data-ttu-id="ef714-103">モジュールがアンロードを終了したことをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="ef714-103">Notifies the profiler that a module has finished unloading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef714-104">構文</span><span class="sxs-lookup"><span data-stu-id="ef714-104">Syntax</span></span>  
  
```cpp  
HRESULT ModuleUnloadFinished(  
    [in] ModuleID moduleId,  
    [in] HRESULT  hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ef714-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ef714-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="ef714-106">からアンロードされたモジュールの ID。</span><span class="sxs-lookup"><span data-stu-id="ef714-106">[in] The ID of the module that was unloaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="ef714-107">からモジュールが正常にアンロードされたかどうかを示す HRESULT。</span><span class="sxs-lookup"><span data-stu-id="ef714-107">[in] An HRESULT that indicates whether the module was unloaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ef714-108">コメント</span><span class="sxs-lookup"><span data-stu-id="ef714-108">Remarks</span></span>  
 <span data-ttu-id="ef714-109">`moduleId` の値は、 [ICorProfilerCallback:: ModuleUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleunloadstarted-method.md)メソッドが返された後の情報要求に対して無効です。</span><span class="sxs-lookup"><span data-stu-id="ef714-109">The value of `moduleId` is not valid for an information request after the [ICorProfilerCallback::ModuleUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleunloadstarted-method.md) method returns.</span></span>  
  
 <span data-ttu-id="ef714-110">`ModuleUnloadFinished` コールバックの後に、クラスのアンロードの一部が続行される場合があります。</span><span class="sxs-lookup"><span data-stu-id="ef714-110">Some parts of unloading the class might continue after the `ModuleUnloadFinished` callback.</span></span> <span data-ttu-id="ef714-111">`hrStatus` のエラー HRESULT はエラーを示します。</span><span class="sxs-lookup"><span data-stu-id="ef714-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="ef714-112">ただし、`hrStatus` の成功 HRESULT は、モジュールのアンロードの最初の部分が成功したことのみを示します。</span><span class="sxs-lookup"><span data-stu-id="ef714-112">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the module has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef714-113">要件</span><span class="sxs-lookup"><span data-stu-id="ef714-113">Requirements</span></span>  
 <span data-ttu-id="ef714-114">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ef714-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef714-115">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ef714-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ef714-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ef714-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ef714-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef714-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef714-118">参照</span><span class="sxs-lookup"><span data-stu-id="ef714-118">See also</span></span>

- [<span data-ttu-id="ef714-119">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ef714-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
