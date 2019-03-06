---
title: ICorProfilerInfo::GetThreadContext メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetThreadContext
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetThreadContext
helpviewer_keywords:
- ICorProfilerInfo::GetThreadContext method [.NET Framework profiling]
- GetThreadContext method, ICorProfilerInfo interface [.NET Framework profiling]
ms.assetid: 79446216-4b8b-484c-8fe3-e87dbf9df2fd
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7b13402b6bccd825629b0110c948ed920c1fdf8a
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57487968"
---
# <a name="icorprofilerinfogetthreadcontext-method"></a><span data-ttu-id="3b69c-102">ICorProfilerInfo::GetThreadContext メソッド</span><span class="sxs-lookup"><span data-stu-id="3b69c-102">ICorProfilerInfo::GetThreadContext Method</span></span>
<span data-ttu-id="3b69c-103">指定したスレッドに関連付けられているコンテキスト id を取得します。</span><span class="sxs-lookup"><span data-stu-id="3b69c-103">Gets the context identity currently associated with the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b69c-104">構文</span><span class="sxs-lookup"><span data-stu-id="3b69c-104">Syntax</span></span>  
  
```  
HRESULT GetThreadContext(  
    [in]  ThreadID  threadId,  
    [out] ContextID *pContextId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3b69c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3b69c-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="3b69c-106">[in]スレッドの ID。</span><span class="sxs-lookup"><span data-stu-id="3b69c-106">[in] The ID of the thread.</span></span>  
  
 `pContextId`  
 <span data-ttu-id="3b69c-107">[out]指定したスレッドに関連付けられているコンテキストの ID へのポインター。</span><span class="sxs-lookup"><span data-stu-id="3b69c-107">[out] A pointer to the context ID currently associated with the specified thread.</span></span> <span data-ttu-id="3b69c-108">コンテキストが現在関連付けられているスレッドがない場合は、この関数は CORPROF_E_DATAINCOMPLETE を返します。</span><span class="sxs-lookup"><span data-stu-id="3b69c-108">If the thread has no context currently associated with it, this function will return CORPROF_E_DATAINCOMPLETE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b69c-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="3b69c-109">Requirements</span></span>  
 <span data-ttu-id="3b69c-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3b69c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b69c-111">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3b69c-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3b69c-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3b69c-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3b69c-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3b69c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b69c-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="3b69c-114">See also</span></span>
- [<span data-ttu-id="3b69c-115">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3b69c-115">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
