---
title: ICorProfilerCallback::ExceptionSearchFunctionEnter メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionSearchFunctionEnter
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionSearchFunctionEnter
helpviewer_keywords:
- ExceptionSearchFunctionEnter method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionSearchFunctionEnter method [.NET Framework profiling]
ms.assetid: bfd54573-b7e6-4bd1-a184-7f08a8b39fae
topic_type:
- apiref
ms.openlocfilehash: 244227aadb50720514f7511be563089d520b4bf5
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500196"
---
# <a name="icorprofilercallbackexceptionsearchfunctionenter-method"></a><span data-ttu-id="49615-102">ICorProfilerCallback::ExceptionSearchFunctionEnter メソッド</span><span class="sxs-lookup"><span data-stu-id="49615-102">ICorProfilerCallback::ExceptionSearchFunctionEnter Method</span></span>
<span data-ttu-id="49615-103">現在の例外のハンドラーを検索するために、例外処理の検索フェーズで関数の検索が開始されたことをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="49615-103">Notifies the profiler that the search phase of exception handling has begun searching a function to find a handler for the current exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49615-104">構文</span><span class="sxs-lookup"><span data-stu-id="49615-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionSearchFunctionEnter(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="49615-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="49615-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="49615-106">\[in] 入力された関数の ID。</span><span class="sxs-lookup"><span data-stu-id="49615-106">\[in] The ID of the function that has been entered.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="49615-107">要件</span><span class="sxs-lookup"><span data-stu-id="49615-107">Requirements</span></span>  
 <span data-ttu-id="49615-108">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="49615-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49615-109">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="49615-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="49615-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="49615-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="49615-111">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49615-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49615-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="49615-112">See also</span></span>

- [<span data-ttu-id="49615-113">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="49615-113">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="49615-114">ExceptionSearchFunctionLeave メソッド</span><span class="sxs-lookup"><span data-stu-id="49615-114">ExceptionSearchFunctionLeave Method</span></span>](icorprofilercallback-exceptionsearchfunctionleave-method.md)
