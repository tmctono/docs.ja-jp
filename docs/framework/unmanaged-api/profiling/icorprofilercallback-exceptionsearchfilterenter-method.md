---
title: ICorProfilerCallback::ExceptionSearchFilterEnter メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionSearchFilterEnter
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionSearchFilterEnter
helpviewer_keywords:
- ExceptionSearchFilterEnter method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionSearchFilterEnter method [.NET Framework profiling]
ms.assetid: acc239ce-3eef-418c-b1df-c5a6dd8e8a4c
topic_type:
- apiref
ms.openlocfilehash: 304b8da670786851a70e38e6623d44b1bde71a04
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500235"
---
# <a name="icorprofilercallbackexceptionsearchfilterenter-method"></a><span data-ttu-id="6ec53-102">ICorProfilerCallback::ExceptionSearchFilterEnter メソッド</span><span class="sxs-lookup"><span data-stu-id="6ec53-102">ICorProfilerCallback::ExceptionSearchFilterEnter Method</span></span>
<span data-ttu-id="6ec53-103">例外処理の検索フェーズがユーザー定義の例外フィルターの実行を開始したことをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="6ec53-103">Notifies the profiler that the search phase of exception handling has begun executing a user-defined exception filter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ec53-104">構文</span><span class="sxs-lookup"><span data-stu-id="6ec53-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionSearchFilterEnter(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6ec53-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6ec53-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="6ec53-106">\[in] フィルターを含む関数の ID。</span><span class="sxs-lookup"><span data-stu-id="6ec53-106">\[in] The ID of the function that contains the filter.</span></span>

## <a name="requirements"></a><span data-ttu-id="6ec53-107">要件</span><span class="sxs-lookup"><span data-stu-id="6ec53-107">Requirements</span></span>  
 <span data-ttu-id="6ec53-108">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6ec53-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ec53-109">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6ec53-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6ec53-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6ec53-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6ec53-111">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ec53-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ec53-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="6ec53-112">See also</span></span>

- [<span data-ttu-id="6ec53-113">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6ec53-113">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="6ec53-114">ExceptionSearchFilterLeave メソッド</span><span class="sxs-lookup"><span data-stu-id="6ec53-114">ExceptionSearchFilterLeave Method</span></span>](icorprofilercallback-exceptionsearchfilterleave-method.md)
