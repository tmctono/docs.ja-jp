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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9eb5b4ec4b3bb99de4755a5b64398e989df379b7
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57478831"
---
# <a name="icorprofilercallbackmoduleloadfinished-method"></a><span data-ttu-id="cfa44-102">ICorProfilerCallback::ModuleLoadFinished メソッド</span><span class="sxs-lookup"><span data-stu-id="cfa44-102">ICorProfilerCallback::ModuleLoadFinished Method</span></span>
<span data-ttu-id="cfa44-103">モジュールの読み込みが完了したことをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="cfa44-103">Notifies the profiler that a module has finished loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cfa44-104">構文</span><span class="sxs-lookup"><span data-stu-id="cfa44-104">Syntax</span></span>  
  
```  
HRESULT ModuleLoadFinished(  
    [in] ModuleID moduleId,  
    [in] HRESULT  hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cfa44-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="cfa44-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="cfa44-106">[in]読み込みが完了しているモジュールの ID。</span><span class="sxs-lookup"><span data-stu-id="cfa44-106">[in] The ID of the module that has finished loading.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="cfa44-107">[in]モジュールが正常に読み込まれたかどうかを示す HRESULT。</span><span class="sxs-lookup"><span data-stu-id="cfa44-107">[in] An HRESULT that indicates whether the module was loaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cfa44-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="cfa44-108">Remarks</span></span>  
 <span data-ttu-id="cfa44-109">値`moduleId`まで情報の要求に対して無効です、`ModuleLoadFinished`メソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="cfa44-109">The value of `moduleId` is not valid for an information request until the `ModuleLoadFinished` method is called.</span></span>  
  
 <span data-ttu-id="cfa44-110">モジュールの読み込みの一部が後に続ける可能性があります、`ModuleLoadFinished`コールバック。</span><span class="sxs-lookup"><span data-stu-id="cfa44-110">Some parts of loading the module might continue after the `ModuleLoadFinished` callback.</span></span> <span data-ttu-id="cfa44-111">エラーの HRESULT で`hrStatus`失敗を示します。</span><span class="sxs-lookup"><span data-stu-id="cfa44-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="cfa44-112">ただし、成功 HRESULT で`hrStatus`のみに、モジュールの読み込みの最初の部分が成功したことを示します。</span><span class="sxs-lookup"><span data-stu-id="cfa44-112">However, a success HRESULT in `hrStatus` indicates only that the first part of loading the module has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cfa44-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="cfa44-113">Requirements</span></span>  
 <span data-ttu-id="cfa44-114">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cfa44-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cfa44-115">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="cfa44-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="cfa44-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cfa44-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cfa44-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cfa44-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfa44-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="cfa44-118">See also</span></span>
- [<span data-ttu-id="cfa44-119">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cfa44-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="cfa44-120">ModuleLoadStarted メソッド</span><span class="sxs-lookup"><span data-stu-id="cfa44-120">ModuleLoadStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadstarted-method.md)
