---
title: ICorProfilerCallback::ModuleLoadFinished メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ModuleLoadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ModuleLoadFinished
helpviewer_keywords:
- ModuleLoadFinished method [.NET Framework profiling]
- ICorProfilerCallback::ModuleLoadFinished method [.NET Framework profiling]
ms.assetid: 050649e5-ffc0-4458-a0a4-d9ee128a219e
topic_type:
- apiref
ms.openlocfilehash: 08fbf49e6944de4934a9fe7a960405ee96a7d8e3
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445942"
---
# <a name="icorprofilercallbackmoduleloadfinished-method"></a><span data-ttu-id="50346-102">ICorProfilerCallback::ModuleLoadFinished メソッド</span><span class="sxs-lookup"><span data-stu-id="50346-102">ICorProfilerCallback::ModuleLoadFinished Method</span></span>
<span data-ttu-id="50346-103">モジュールが読み込みを終了したことをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="50346-103">Notifies the profiler that a module has finished loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50346-104">構文</span><span class="sxs-lookup"><span data-stu-id="50346-104">Syntax</span></span>  
  
```cpp  
HRESULT ModuleLoadFinished(  
    [in] ModuleID moduleId,  
    [in] HRESULT  hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="50346-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="50346-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="50346-106">から読み込みを終了したモジュールの ID。</span><span class="sxs-lookup"><span data-stu-id="50346-106">[in] The ID of the module that has finished loading.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="50346-107">からモジュールが正常に読み込まれたかどうかを示す HRESULT。</span><span class="sxs-lookup"><span data-stu-id="50346-107">[in] An HRESULT that indicates whether the module was loaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="50346-108">コメント</span><span class="sxs-lookup"><span data-stu-id="50346-108">Remarks</span></span>  
 <span data-ttu-id="50346-109">`moduleId` の値は、`ModuleLoadFinished` メソッドが呼び出されるまで、情報要求に対して有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="50346-109">The value of `moduleId` is not valid for an information request until the `ModuleLoadFinished` method is called.</span></span>  
  
 <span data-ttu-id="50346-110">`ModuleLoadFinished` コールバックの後も、モジュールの読み込みの一部が続行される場合があります。</span><span class="sxs-lookup"><span data-stu-id="50346-110">Some parts of loading the module might continue after the `ModuleLoadFinished` callback.</span></span> <span data-ttu-id="50346-111">`hrStatus` のエラー HRESULT はエラーを示します。</span><span class="sxs-lookup"><span data-stu-id="50346-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="50346-112">ただし、`hrStatus` の成功 HRESULT は、モジュールの読み込みの最初の部分が成功したことのみを示します。</span><span class="sxs-lookup"><span data-stu-id="50346-112">However, a success HRESULT in `hrStatus` indicates only that the first part of loading the module has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50346-113">要件</span><span class="sxs-lookup"><span data-stu-id="50346-113">Requirements</span></span>  
 <span data-ttu-id="50346-114">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="50346-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50346-115">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="50346-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="50346-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="50346-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="50346-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50346-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50346-118">参照</span><span class="sxs-lookup"><span data-stu-id="50346-118">See also</span></span>

- [<span data-ttu-id="50346-119">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="50346-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="50346-120">ModuleLoadStarted メソッド</span><span class="sxs-lookup"><span data-stu-id="50346-120">ModuleLoadStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadstarted-method.md)
