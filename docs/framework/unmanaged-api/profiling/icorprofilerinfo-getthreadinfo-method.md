---
title: ICorProfilerInfo::GetThreadInfo メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetThreadInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetThreadInfo
helpviewer_keywords:
- ICorProfilerInfo::GetThreadInfo method [.NET Framework profiling]
- GetThreadInfo method [.NET Framework profiling]
ms.assetid: fc994fef-65c9-432a-84cb-66c8141147e7
topic_type:
- apiref
ms.openlocfilehash: 5edc4e0e2fc25ddae6ccabc1aa9c9a031292b63a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449895"
---
# <a name="icorprofilerinfogetthreadinfo-method"></a><span data-ttu-id="07968-102">ICorProfilerInfo::GetThreadInfo メソッド</span><span class="sxs-lookup"><span data-stu-id="07968-102">ICorProfilerInfo::GetThreadInfo Method</span></span>
<span data-ttu-id="07968-103">Gets the current Win32 thread identity for the specified thread.</span><span class="sxs-lookup"><span data-stu-id="07968-103">Gets the current Win32 thread identity for the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07968-104">構文</span><span class="sxs-lookup"><span data-stu-id="07968-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadInfo(  
    [in]  ThreadID threadId,  
    [out] DWORD    *pdwWin32ThreadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="07968-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="07968-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="07968-106">[in] The ID of the thread for which to get the current Win32 ID.</span><span class="sxs-lookup"><span data-stu-id="07968-106">[in] The ID of the thread for which to get the current Win32 ID.</span></span>  
  
 `pdwWin32ThreadId`  
 <span data-ttu-id="07968-107">[out] A pointer to the specified thread's current Win32 thread ID.</span><span class="sxs-lookup"><span data-stu-id="07968-107">[out] A pointer to the specified thread's current Win32 thread ID.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="07968-108">［要件］</span><span class="sxs-lookup"><span data-stu-id="07968-108">Requirements</span></span>  
 <span data-ttu-id="07968-109">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="07968-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="07968-110">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="07968-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="07968-111">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="07968-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="07968-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="07968-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07968-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="07968-113">See also</span></span>

- [<span data-ttu-id="07968-114">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="07968-114">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
