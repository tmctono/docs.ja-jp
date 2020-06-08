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
ms.openlocfilehash: fd35f47c004d1ffb235cefe1cd2a1eb2c1fffaef
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503316"
---
# <a name="icorprofilercallbackmoduleunloadfinished-method"></a><span data-ttu-id="277cf-102">ICorProfilerCallback::ModuleUnloadFinished メソッド</span><span class="sxs-lookup"><span data-stu-id="277cf-102">ICorProfilerCallback::ModuleUnloadFinished Method</span></span>
<span data-ttu-id="277cf-103">モジュールがアンロードを終了したことをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="277cf-103">Notifies the profiler that a module has finished unloading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="277cf-104">構文</span><span class="sxs-lookup"><span data-stu-id="277cf-104">Syntax</span></span>  
  
```cpp  
HRESULT ModuleUnloadFinished(  
    [in] ModuleID moduleId,  
    [in] HRESULT  hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="277cf-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="277cf-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="277cf-106">からアンロードされたモジュールの ID。</span><span class="sxs-lookup"><span data-stu-id="277cf-106">[in] The ID of the module that was unloaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="277cf-107">からモジュールが正常にアンロードされたかどうかを示す HRESULT。</span><span class="sxs-lookup"><span data-stu-id="277cf-107">[in] An HRESULT that indicates whether the module was unloaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="277cf-108">解説</span><span class="sxs-lookup"><span data-stu-id="277cf-108">Remarks</span></span>  
 <span data-ttu-id="277cf-109">`moduleId` [ICorProfilerCallback:: ModuleUnloadStarted](icorprofilercallback-moduleunloadstarted-method.md)メソッドがを返すと、の値は情報要求に対して有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="277cf-109">The value of `moduleId` is not valid for an information request after the [ICorProfilerCallback::ModuleUnloadStarted](icorprofilercallback-moduleunloadstarted-method.md) method returns.</span></span>  
  
 <span data-ttu-id="277cf-110">クラスのアンロードの一部は、コールバック後に続行される場合があり `ModuleUnloadFinished` ます。</span><span class="sxs-lookup"><span data-stu-id="277cf-110">Some parts of unloading the class might continue after the `ModuleUnloadFinished` callback.</span></span> <span data-ttu-id="277cf-111">のエラー HRESULT は `hrStatus` エラーを示します。</span><span class="sxs-lookup"><span data-stu-id="277cf-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="277cf-112">ただし、の成功 HRESULT は、 `hrStatus` モジュールのアンロードの最初の部分が成功したことを示します。</span><span class="sxs-lookup"><span data-stu-id="277cf-112">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the module has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="277cf-113">要件</span><span class="sxs-lookup"><span data-stu-id="277cf-113">Requirements</span></span>  
 <span data-ttu-id="277cf-114">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="277cf-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="277cf-115">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="277cf-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="277cf-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="277cf-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="277cf-117">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="277cf-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="277cf-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="277cf-118">See also</span></span>

- [<span data-ttu-id="277cf-119">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="277cf-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
