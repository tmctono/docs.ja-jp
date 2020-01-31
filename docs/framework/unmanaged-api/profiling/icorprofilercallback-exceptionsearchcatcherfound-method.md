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
ms.openlocfilehash: 8f5997dddf78dd75d482bc45d2ee730b20d9ab16
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866475"
---
# <a name="icorprofilercallbackexceptionsearchcatcherfound-method"></a><span data-ttu-id="1d573-102">ICorProfilerCallback::ExceptionSearchCatcherFound メソッド</span><span class="sxs-lookup"><span data-stu-id="1d573-102">ICorProfilerCallback::ExceptionSearchCatcherFound Method</span></span>
<span data-ttu-id="1d573-103">例外処理の検索フェーズによってスローされた例外のハンドラーが見つかったことをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="1d573-103">Notifies the profiler that the search phase of exception handling has located a handler for the exception that was thrown.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d573-104">構文</span><span class="sxs-lookup"><span data-stu-id="1d573-104">Syntax</span></span>  
  
```cpp  
RESULT ExceptionSearchCatcherFound(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1d573-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1d573-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="1d573-106">\[] には、例外ハンドラーを含む関数の ID を入力します。</span><span class="sxs-lookup"><span data-stu-id="1d573-106">\[in] The ID of the function that contains the exception handler.</span></span>

## <a name="requirements"></a><span data-ttu-id="1d573-107">要件</span><span class="sxs-lookup"><span data-stu-id="1d573-107">Requirements</span></span>  
 <span data-ttu-id="1d573-108">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d573-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d573-109">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1d573-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1d573-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1d573-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1d573-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d573-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d573-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="1d573-112">See also</span></span>

- [<span data-ttu-id="1d573-113">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1d573-113">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
