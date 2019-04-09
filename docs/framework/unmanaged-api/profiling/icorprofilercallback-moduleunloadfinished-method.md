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
ms.openlocfilehash: f096c1f3898348141e13da44f39f2768417acd1c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59152244"
---
# <a name="icorprofilercallbackmoduleunloadfinished-method"></a><span data-ttu-id="9e872-102">ICorProfilerCallback::ModuleUnloadFinished メソッド</span><span class="sxs-lookup"><span data-stu-id="9e872-102">ICorProfilerCallback::ModuleUnloadFinished Method</span></span>
<span data-ttu-id="9e872-103">モジュールのアンロードが完了したことをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="9e872-103">Notifies the profiler that a module has finished unloading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e872-104">構文</span><span class="sxs-lookup"><span data-stu-id="9e872-104">Syntax</span></span>  
  
```  
HRESULT ModuleUnloadFinished(  
    [in] ModuleID moduleId,  
    [in] HRESULT  hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9e872-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9e872-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="9e872-106">[in]アンロードされたモジュールの ID。</span><span class="sxs-lookup"><span data-stu-id="9e872-106">[in] The ID of the module that was unloaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="9e872-107">[in]かどうか、モジュールがアンロードされた正常を示す HRESULT。</span><span class="sxs-lookup"><span data-stu-id="9e872-107">[in] An HRESULT that indicates whether the module was unloaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9e872-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="9e872-108">Remarks</span></span>  
 <span data-ttu-id="9e872-109">値`moduleId`は後の情報の要求は無効です、 [icorprofilercallback::moduleunloadstarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleunloadstarted-method.md)メソッドを返します。</span><span class="sxs-lookup"><span data-stu-id="9e872-109">The value of `moduleId` is not valid for an information request after the [ICorProfilerCallback::ModuleUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleunloadstarted-method.md) method returns.</span></span>  
  
 <span data-ttu-id="9e872-110">クラスのアンロードの一部が後に続ける可能性があります、`ModuleUnloadFinished`コールバック。</span><span class="sxs-lookup"><span data-stu-id="9e872-110">Some parts of unloading the class might continue after the `ModuleUnloadFinished` callback.</span></span> <span data-ttu-id="9e872-111">エラーの HRESULT で`hrStatus`失敗を示します。</span><span class="sxs-lookup"><span data-stu-id="9e872-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="9e872-112">ただし、成功 HRESULT で`hrStatus`のみに、モジュールのアンロードの最初の部分が成功したことを示します。</span><span class="sxs-lookup"><span data-stu-id="9e872-112">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the module has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e872-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="9e872-113">Requirements</span></span>  
 <span data-ttu-id="9e872-114">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e872-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e872-115">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9e872-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9e872-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9e872-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="9e872-117">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="9e872-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9e872-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="9e872-118">See also</span></span>

- [<span data-ttu-id="9e872-119">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9e872-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
