---
title: ICorProfilerCallback::ExceptionSearchCatcherFound メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionSearchCatcherFound
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionSearchCatcherFound
helpviewer_keywords:
- ExceptionSearchCatcherFound method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionSearchCatcherFound method [.NET Framework profiling]
ms.assetid: 190f424d-5e37-4163-a191-0895686e9476
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a4dc6b66aff34bae869737591040e5fc1e552834
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57499668"
---
# <a name="icorprofilercallbackexceptionsearchcatcherfound-method"></a><span data-ttu-id="2f815-102">ICorProfilerCallback::ExceptionSearchCatcherFound メソッド</span><span class="sxs-lookup"><span data-stu-id="2f815-102">ICorProfilerCallback::ExceptionSearchCatcherFound Method</span></span>
<span data-ttu-id="2f815-103">例外処理の検索フェーズでスローされた例外のハンドラーが見つかったことをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="2f815-103">Notifies the profiler that the search phase of exception handling has located a handler for the exception that was thrown.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f815-104">構文</span><span class="sxs-lookup"><span data-stu-id="2f815-104">Syntax</span></span>  
  
```  
RESULT ExceptionSearchCatcherFound(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2f815-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2f815-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="2f815-106">[in]例外ハンドラーを含む関数の ID。</span><span class="sxs-lookup"><span data-stu-id="2f815-106">[in] The ID of the function that contains the exception handler.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2f815-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="2f815-107">Requirements</span></span>  
 <span data-ttu-id="2f815-108">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2f815-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f815-109">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2f815-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2f815-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2f815-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2f815-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2f815-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f815-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="2f815-112">See also</span></span>
- [<span data-ttu-id="2f815-113">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2f815-113">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
