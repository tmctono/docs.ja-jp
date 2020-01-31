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
ms.openlocfilehash: b13573d19ab4d8bb655c1e153530dc70173abe82
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866144"
---
# <a name="icorprofilercallbackmoduleunloadfinished-method"></a><span data-ttu-id="efb3a-102">ICorProfilerCallback::ModuleUnloadFinished メソッド</span><span class="sxs-lookup"><span data-stu-id="efb3a-102">ICorProfilerCallback::ModuleUnloadFinished Method</span></span>
<span data-ttu-id="efb3a-103">モジュールがアンロードを終了したことをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="efb3a-103">Notifies the profiler that a module has finished unloading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="efb3a-104">構文</span><span class="sxs-lookup"><span data-stu-id="efb3a-104">Syntax</span></span>  
  
```cpp  
HRESULT ModuleUnloadFinished(  
    [in] ModuleID moduleId,  
    [in] HRESULT  hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="efb3a-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="efb3a-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="efb3a-106">からアンロードされたモジュールの ID。</span><span class="sxs-lookup"><span data-stu-id="efb3a-106">[in] The ID of the module that was unloaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="efb3a-107">からモジュールが正常にアンロードされたかどうかを示す HRESULT。</span><span class="sxs-lookup"><span data-stu-id="efb3a-107">[in] An HRESULT that indicates whether the module was unloaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="efb3a-108">コメント</span><span class="sxs-lookup"><span data-stu-id="efb3a-108">Remarks</span></span>  
 <span data-ttu-id="efb3a-109">`moduleId` の値は、 [ICorProfilerCallback:: ModuleUnloadStarted](icorprofilercallback-moduleunloadstarted-method.md)メソッドが返された後の情報要求に対して無効です。</span><span class="sxs-lookup"><span data-stu-id="efb3a-109">The value of `moduleId` is not valid for an information request after the [ICorProfilerCallback::ModuleUnloadStarted](icorprofilercallback-moduleunloadstarted-method.md) method returns.</span></span>  
  
 <span data-ttu-id="efb3a-110">`ModuleUnloadFinished` コールバックの後に、クラスのアンロードの一部が続行される場合があります。</span><span class="sxs-lookup"><span data-stu-id="efb3a-110">Some parts of unloading the class might continue after the `ModuleUnloadFinished` callback.</span></span> <span data-ttu-id="efb3a-111">`hrStatus` のエラー HRESULT はエラーを示します。</span><span class="sxs-lookup"><span data-stu-id="efb3a-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="efb3a-112">ただし、`hrStatus` の成功 HRESULT は、モジュールのアンロードの最初の部分が成功したことのみを示します。</span><span class="sxs-lookup"><span data-stu-id="efb3a-112">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the module has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="efb3a-113">要件</span><span class="sxs-lookup"><span data-stu-id="efb3a-113">Requirements</span></span>  
 <span data-ttu-id="efb3a-114">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="efb3a-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="efb3a-115">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="efb3a-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="efb3a-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="efb3a-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="efb3a-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="efb3a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efb3a-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="efb3a-118">See also</span></span>

- [<span data-ttu-id="efb3a-119">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="efb3a-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
