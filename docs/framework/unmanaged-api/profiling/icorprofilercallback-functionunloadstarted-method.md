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
ms.openlocfilehash: 988843559e55cc4cacd2a40bb3e6ac51721e99b6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175162"
---
# <a name="icorprofilercallbackfunctionunloadstarted-method"></a><span data-ttu-id="d287b-102">ICorProfilerCallback::FunctionUnloadStarted メソッド</span><span class="sxs-lookup"><span data-stu-id="d287b-102">ICorProfilerCallback::FunctionUnloadStarted Method</span></span>
<span data-ttu-id="d287b-103">ランタイムが関数のアンロードを開始したことをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="d287b-103">Notifies the profiler that the runtime has started to unload a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d287b-104">構文</span><span class="sxs-lookup"><span data-stu-id="d287b-104">Syntax</span></span>  
  
```cpp  
HRESULT FunctionUnloadStarted(  
    [in] FunctionID functionId);
```  
  
## <a name="parameters"></a><span data-ttu-id="d287b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d287b-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="d287b-106">\[in] アンロードされている関数の ID。</span><span class="sxs-lookup"><span data-stu-id="d287b-106">\[in] The ID of the function that is being unloaded.</span></span>

## <a name="remarks"></a><span data-ttu-id="d287b-107">解説</span><span class="sxs-lookup"><span data-stu-id="d287b-107">Remarks</span></span>  
 <span data-ttu-id="d287b-108">このメソッドが呼`functionId`び出し元に戻った後、パラメーターの値は無効になります。</span><span class="sxs-lookup"><span data-stu-id="d287b-108">The value of the `functionId` parameter is no longer valid after this method returns to the caller.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d287b-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="d287b-109">Requirements</span></span>  
 <span data-ttu-id="d287b-110">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d287b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d287b-111">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d287b-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d287b-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d287b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d287b-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d287b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d287b-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="d287b-114">See also</span></span>

- [<span data-ttu-id="d287b-115">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d287b-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
