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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8dd5e2ecf22ce14765df8972611f1f95109f76ed
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67769203"
---
# <a name="icorprofilercallbackmoduleunloadfinished-method"></a><span data-ttu-id="c35ec-102">ICorProfilerCallback::ModuleUnloadFinished メソッド</span><span class="sxs-lookup"><span data-stu-id="c35ec-102">ICorProfilerCallback::ModuleUnloadFinished Method</span></span>
<span data-ttu-id="c35ec-103">モジュールのアンロードが完了したことをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="c35ec-103">Notifies the profiler that a module has finished unloading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c35ec-104">構文</span><span class="sxs-lookup"><span data-stu-id="c35ec-104">Syntax</span></span>  
  
```cpp  
HRESULT ModuleUnloadFinished(  
    [in] ModuleID moduleId,  
    [in] HRESULT  hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c35ec-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c35ec-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="c35ec-106">[in]アンロードされたモジュールの ID。</span><span class="sxs-lookup"><span data-stu-id="c35ec-106">[in] The ID of the module that was unloaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="c35ec-107">[in]かどうか、モジュールがアンロードされた正常を示す HRESULT。</span><span class="sxs-lookup"><span data-stu-id="c35ec-107">[in] An HRESULT that indicates whether the module was unloaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c35ec-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="c35ec-108">Remarks</span></span>  
 <span data-ttu-id="c35ec-109">値`moduleId`は後の情報の要求は無効です、 [icorprofilercallback::moduleunloadstarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleunloadstarted-method.md)メソッドを返します。</span><span class="sxs-lookup"><span data-stu-id="c35ec-109">The value of `moduleId` is not valid for an information request after the [ICorProfilerCallback::ModuleUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleunloadstarted-method.md) method returns.</span></span>  
  
 <span data-ttu-id="c35ec-110">クラスのアンロードの一部が後に続ける可能性があります、`ModuleUnloadFinished`コールバック。</span><span class="sxs-lookup"><span data-stu-id="c35ec-110">Some parts of unloading the class might continue after the `ModuleUnloadFinished` callback.</span></span> <span data-ttu-id="c35ec-111">エラーの HRESULT で`hrStatus`失敗を示します。</span><span class="sxs-lookup"><span data-stu-id="c35ec-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="c35ec-112">ただし、成功 HRESULT で`hrStatus`のみに、モジュールのアンロードの最初の部分が成功したことを示します。</span><span class="sxs-lookup"><span data-stu-id="c35ec-112">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the module has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c35ec-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="c35ec-113">Requirements</span></span>  
 <span data-ttu-id="c35ec-114">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c35ec-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c35ec-115">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c35ec-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c35ec-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c35ec-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c35ec-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c35ec-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c35ec-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="c35ec-118">See also</span></span>

- [<span data-ttu-id="c35ec-119">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c35ec-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
