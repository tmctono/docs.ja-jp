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
ms.openlocfilehash: 2b228337a55d50b94da966b45877e2000b3c03e4
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866313"
---
# <a name="icorprofilercallbackfunctionunloadstarted-method"></a><span data-ttu-id="88b47-102">ICorProfilerCallback::FunctionUnloadStarted メソッド</span><span class="sxs-lookup"><span data-stu-id="88b47-102">ICorProfilerCallback::FunctionUnloadStarted Method</span></span>
<span data-ttu-id="88b47-103">ランタイムが関数のアンロードを開始したことをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="88b47-103">Notifies the profiler that the runtime has started to unload a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88b47-104">構文</span><span class="sxs-lookup"><span data-stu-id="88b47-104">Syntax</span></span>  
  
```cpp  
HRESULT FunctionUnloadStarted(  
    [in] FunctionID functionId);   
```  
  
## <a name="parameters"></a><span data-ttu-id="88b47-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="88b47-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="88b47-106">\[] アンロードされる関数の ID。</span><span class="sxs-lookup"><span data-stu-id="88b47-106">\[in] The ID of the function that is being unloaded.</span></span>

## <a name="remarks"></a><span data-ttu-id="88b47-107">コメント</span><span class="sxs-lookup"><span data-stu-id="88b47-107">Remarks</span></span>  
 <span data-ttu-id="88b47-108">このメソッドが呼び出し元に戻った後、`functionId` パラメーターの値は無効になりました。</span><span class="sxs-lookup"><span data-stu-id="88b47-108">The value of the `functionId` parameter is no longer valid after this method returns to the caller.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="88b47-109">要件</span><span class="sxs-lookup"><span data-stu-id="88b47-109">Requirements</span></span>  
 <span data-ttu-id="88b47-110">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="88b47-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="88b47-111">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="88b47-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="88b47-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="88b47-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="88b47-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="88b47-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88b47-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="88b47-114">See also</span></span>

- [<span data-ttu-id="88b47-115">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="88b47-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
