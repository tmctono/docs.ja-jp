---
title: ICorProfilerCallback::FunctionUnloadStarted メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.FunctionUnloadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::FunctionUnloadStarted
helpviewer_keywords:
- FunctionUnloadStarted method [.NET Framework profiling]
- ICorProfilerCallback::FunctionUnloadStarted method [.NET Framework profiling]
ms.assetid: d6a5fa8b-09c6-47a5-b60e-6cf2e355df30
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b6dd7792fe298aa1950b23053a7c5cd576b62e7b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67755897"
---
# <a name="icorprofilercallbackfunctionunloadstarted-method"></a><span data-ttu-id="d973d-102">ICorProfilerCallback::FunctionUnloadStarted メソッド</span><span class="sxs-lookup"><span data-stu-id="d973d-102">ICorProfilerCallback::FunctionUnloadStarted Method</span></span>
<span data-ttu-id="d973d-103">関数のアンロードをランタイムが開始されたことをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="d973d-103">Notifies the profiler that the runtime has started to unload a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d973d-104">構文</span><span class="sxs-lookup"><span data-stu-id="d973d-104">Syntax</span></span>  
  
```cpp  
HRESULT FunctionUnloadStarted(  
    [in] FunctionID functionId);   
```  
  
## <a name="parameters"></a><span data-ttu-id="d973d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d973d-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="d973d-106">[in]アンロードされている関数の ID。</span><span class="sxs-lookup"><span data-stu-id="d973d-106">[in] The ID of the function that is being unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d973d-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="d973d-107">Remarks</span></span>  
 <span data-ttu-id="d973d-108">値、`functionId`このメソッドが呼び出し元に返された後にパラメーターが無効になっています。</span><span class="sxs-lookup"><span data-stu-id="d973d-108">The value of the `functionId` parameter is no longer valid after this method returns to the caller.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d973d-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="d973d-109">Requirements</span></span>  
 <span data-ttu-id="d973d-110">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d973d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d973d-111">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d973d-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d973d-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d973d-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d973d-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d973d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d973d-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="d973d-114">See also</span></span>

- [<span data-ttu-id="d973d-115">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d973d-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
