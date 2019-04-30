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
ms.openlocfilehash: 802072f3a0151aabc5ca5796df57ea7c694a2070
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62041211"
---
# <a name="icorprofilerinfogetcurrentthreadid-method"></a><span data-ttu-id="f6ebd-102">ICorProfilerInfo::GetCurrentThreadID メソッド</span><span class="sxs-lookup"><span data-stu-id="f6ebd-102">ICorProfilerInfo::GetCurrentThreadID Method</span></span>
<span data-ttu-id="f6ebd-103">マネージ スレッドである場合は、現在のスレッドの ID を取得します。</span><span class="sxs-lookup"><span data-stu-id="f6ebd-103">Gets the ID of the current thread, if it is a managed thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6ebd-104">構文</span><span class="sxs-lookup"><span data-stu-id="f6ebd-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentThreadID(  
    [out] ThreadID *pThreadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f6ebd-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f6ebd-105">Parameters</span></span>  
 `pThreadId`  
 <span data-ttu-id="f6ebd-106">[out]マネージ スレッドの返された ID へのポインター。</span><span class="sxs-lookup"><span data-stu-id="f6ebd-106">[out] A pointer to the returned ID of the managed thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f6ebd-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="f6ebd-107">Remarks</span></span>  
 <span data-ttu-id="f6ebd-108">現在のスレッドが、内部ランタイム スレッドまたは他の非管理対象のスレッドの場合`GetCurrentThreadID`、HRESULT の戻り値として CORPROF_E_NOT_MANAGED_THREAD を返します、`pThreadId`パラメーターは null になります。</span><span class="sxs-lookup"><span data-stu-id="f6ebd-108">If the current thread is an internal runtime thread or other unmanaged thread, `GetCurrentThreadID` returns CORPROF_E_NOT_MANAGED_THREAD as the HRESULT, and the returned value of the `pThreadId` parameter will be null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6ebd-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="f6ebd-109">Requirements</span></span>  
 <span data-ttu-id="f6ebd-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f6ebd-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6ebd-111">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f6ebd-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f6ebd-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f6ebd-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f6ebd-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f6ebd-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6ebd-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="f6ebd-114">See also</span></span>

- [<span data-ttu-id="f6ebd-115">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f6ebd-115">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
