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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 53bcc04c8d68a79217ebda5284efe7d8e18fdb91
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57478779"
---
# <a name="icorprofilerinfogetthreadinfo-method"></a><span data-ttu-id="5a822-102">ICorProfilerInfo::GetThreadInfo メソッド</span><span class="sxs-lookup"><span data-stu-id="5a822-102">ICorProfilerInfo::GetThreadInfo Method</span></span>
<span data-ttu-id="5a822-103">指定したスレッドの現在の Win32 スレッド id を取得します。</span><span class="sxs-lookup"><span data-stu-id="5a822-103">Gets the current Win32 thread identity for the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a822-104">構文</span><span class="sxs-lookup"><span data-stu-id="5a822-104">Syntax</span></span>  
  
```  
HRESULT GetThreadInfo(  
    [in]  ThreadID threadId,  
    [out] DWORD    *pdwWin32ThreadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5a822-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5a822-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="5a822-106">[in]現在、Win32 ID を取得する対象のスレッドの ID</span><span class="sxs-lookup"><span data-stu-id="5a822-106">[in] The ID of the thread for which to get the current Win32 ID.</span></span>  
  
 `pdwWin32ThreadId`  
 <span data-ttu-id="5a822-107">[out]指定したスレッドの現在の Win32 スレッドへのポインターの id。</span><span class="sxs-lookup"><span data-stu-id="5a822-107">[out] A pointer to the specified thread's current Win32 thread ID.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a822-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="5a822-108">Requirements</span></span>  
 <span data-ttu-id="5a822-109">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a822-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a822-110">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5a822-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5a822-111">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5a822-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5a822-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a822-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a822-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="5a822-113">See also</span></span>
- [<span data-ttu-id="5a822-114">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5a822-114">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
