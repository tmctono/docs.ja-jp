---
title: ICorProfilerInfo::GetCurrentThreadID メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetCurrentThreadID
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetCurrentThreadID
helpviewer_keywords:
- GetCurrentThreadID method, ICorProfilerInfo interface [.NET Framework profiling]
- ICorProfilerInfo::GetCurrentThreadID method [.NET Framework profiling]
ms.assetid: 39bbdb30-6a7a-4202-8da3-67ae9a0ab3a8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 32b44cb3a96205e8a784c81a05324370fb5ac67e
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57478545"
---
# <a name="icorprofilerinfogetcurrentthreadid-method"></a><span data-ttu-id="fbd73-102">ICorProfilerInfo::GetCurrentThreadID メソッド</span><span class="sxs-lookup"><span data-stu-id="fbd73-102">ICorProfilerInfo::GetCurrentThreadID Method</span></span>
<span data-ttu-id="fbd73-103">マネージ スレッドである場合は、現在のスレッドの ID を取得します。</span><span class="sxs-lookup"><span data-stu-id="fbd73-103">Gets the ID of the current thread, if it is a managed thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fbd73-104">構文</span><span class="sxs-lookup"><span data-stu-id="fbd73-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentThreadID(  
    [out] ThreadID *pThreadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fbd73-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="fbd73-105">Parameters</span></span>  
 `pThreadId`  
 <span data-ttu-id="fbd73-106">[out]マネージ スレッドの返された ID へのポインター。</span><span class="sxs-lookup"><span data-stu-id="fbd73-106">[out] A pointer to the returned ID of the managed thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fbd73-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="fbd73-107">Remarks</span></span>  
 <span data-ttu-id="fbd73-108">現在のスレッドが、内部ランタイム スレッドまたは他の非管理対象のスレッドの場合`GetCurrentThreadID`、HRESULT の戻り値として CORPROF_E_NOT_MANAGED_THREAD を返します、`pThreadId`パラメーターは null になります。</span><span class="sxs-lookup"><span data-stu-id="fbd73-108">If the current thread is an internal runtime thread or other unmanaged thread, `GetCurrentThreadID` returns CORPROF_E_NOT_MANAGED_THREAD as the HRESULT, and the returned value of the `pThreadId` parameter will be null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fbd73-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="fbd73-109">Requirements</span></span>  
 <span data-ttu-id="fbd73-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fbd73-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fbd73-111">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fbd73-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="fbd73-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fbd73-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fbd73-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fbd73-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbd73-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="fbd73-114">See also</span></span>
- [<span data-ttu-id="fbd73-115">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fbd73-115">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
