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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: be91772f07e1a06c7df5b16fd70812e6a522d736
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61597220"
---
# <a name="icorprofilercallbackexceptionsearchfilterenter-method"></a><span data-ttu-id="d5dba-102">ICorProfilerCallback::ExceptionSearchFilterEnter メソッド</span><span class="sxs-lookup"><span data-stu-id="d5dba-102">ICorProfilerCallback::ExceptionSearchFilterEnter Method</span></span>
<span data-ttu-id="d5dba-103">例外処理の検索フェーズで、ユーザー定義の例外フィルターの実行が開始されたことをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="d5dba-103">Notifies the profiler that the search phase of exception handling has begun executing a user-defined exception filter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5dba-104">構文</span><span class="sxs-lookup"><span data-stu-id="d5dba-104">Syntax</span></span>  
  
```  
HRESULT ExceptionSearchFilterEnter(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d5dba-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d5dba-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="d5dba-106">[in]フィルターを含む関数の ID。</span><span class="sxs-lookup"><span data-stu-id="d5dba-106">[in] The ID of the function that contains the filter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d5dba-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="d5dba-107">Requirements</span></span>  
 <span data-ttu-id="d5dba-108">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d5dba-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5dba-109">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d5dba-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d5dba-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d5dba-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d5dba-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5dba-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5dba-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="d5dba-112">See also</span></span>

- [<span data-ttu-id="d5dba-113">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d5dba-113">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="d5dba-114">ExceptionSearchFilterLeave メソッド</span><span class="sxs-lookup"><span data-stu-id="d5dba-114">ExceptionSearchFilterLeave Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterleave-method.md)
