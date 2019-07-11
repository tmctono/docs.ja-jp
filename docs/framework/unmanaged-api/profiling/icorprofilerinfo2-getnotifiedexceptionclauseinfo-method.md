---
title: ICorProfilerInfo2::GetNotifiedExceptionClauseInfo メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetNotifiedExceptionClauseInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetNotifiedExceptionClauseInfo
helpviewer_keywords:
- ICorProfilerInfo2::GetNotifiedExceptionCaluseInfo method [.NET Framework profiling]
- GetNotifiedExceptionCaluseInfo method [.NET Framework profiling]
ms.assetid: f9594a7e-cb0c-4c48-accb-29f762aa0c21
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a659e139040174a66043283ed4633d9c9d223ce8
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67774037"
---
# <a name="icorprofilerinfo2getnotifiedexceptionclauseinfo-method"></a><span data-ttu-id="355b9-102">ICorProfilerInfo2::GetNotifiedExceptionClauseInfo メソッド</span><span class="sxs-lookup"><span data-stu-id="355b9-102">ICorProfilerInfo2::GetNotifiedExceptionClauseInfo Method</span></span>
<span data-ttu-id="355b9-103">例外の句のネイティブのアドレスとフレームの情報を取得します (`catch`/`finally`/`filter`) を実行するのには、またはが実行されています。</span><span class="sxs-lookup"><span data-stu-id="355b9-103">Gets the native address and frame information for the exception clause (`catch`/`finally`/`filter`) that is about to be run or has just been run.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="355b9-104">構文</span><span class="sxs-lookup"><span data-stu-id="355b9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNotifiedExceptionClauseInfo(  
    [out] COR_PRF_EX_CLAUSE_INFO *pinfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="355b9-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="355b9-105">Parameters</span></span>  
 `pinfo`  
 <span data-ttu-id="355b9-106">[out]ポインターを[COR_PRF_EX_CLAUSE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-ex-clause-info-structure.md)現在の例外句インスタンスおよび関連するフレームを記述する構造体。</span><span class="sxs-lookup"><span data-stu-id="355b9-106">[out] A pointer to a [COR_PRF_EX_CLAUSE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-ex-clause-info-structure.md) structure that describes the current exception clause instance and its associated frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="355b9-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="355b9-107">Remarks</span></span>  
 <span data-ttu-id="355b9-108">例外の通知が受信されると、`GetNotifiedExceptionClauseInfo`例外句のネイティブのアドレスとフレームの情報を取得するために使用できます (`catch`/`finally`/`filter`) ですが (実行しようとしています[Icorprofilercallback::exceptioncatcherenter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherenter-method.md)、 [icorprofilercallback::exceptionunwindfinallyenter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyenter-method.md)、または[icorprofilercallback::exceptionsearchfilterenter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterenter-method.md)プロファイラーがコールバックを受信した) が実行されているか ([icorprofilercallback::exceptioncatcherleave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherleave-method.md)、 [icorprofilercallback::exceptionunwindfinallyleave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyleave-method.md)、または[Icorprofilercallback::exceptionsearchfilterleave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterleave-method.md)プロファイラーがコールバックを受信した)。</span><span class="sxs-lookup"><span data-stu-id="355b9-108">When an exception notification is received, `GetNotifiedExceptionClauseInfo` can be used to get the native address and frame information for the exception clause (`catch`/`finally`/`filter`) that is about to be run ([ICorProfilerCallback::ExceptionCatcherEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherenter-method.md), [ICorProfilerCallback::ExceptionUnwindFinallyEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyenter-method.md), or [ICorProfilerCallback::ExceptionSearchFilterEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterenter-method.md) callback is received by the profiler) or has just been run ([ICorProfilerCallback::ExceptionCatcherLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherleave-method.md), [ICorProfilerCallback::ExceptionUnwindFinallyLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyleave-method.md), or [ICorProfilerCallback::ExceptionSearchFilterLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterleave-method.md) callback is received by the profiler).</span></span>  
  
 <span data-ttu-id="355b9-109">この呼び出しは、照合 Leave のコールバックを受け取るかではその句のままに通知を現在の句で入れ子になった例外がスローされるまでに、Enter コールバックのいずれかの後にいつでも実行できます。</span><span class="sxs-lookup"><span data-stu-id="355b9-109">This call can be made at any time after one of the Enter callbacks above until either the matching Leave callback is received or a nested exception is thrown in the current clause, in which case there is no Leave notification for that clause.</span></span> <span data-ttu-id="355b9-110">スローされた例外をエスケープするためのことはできませんに注意してください、`filter`が常に休暇通知その場合、例外句。</span><span class="sxs-lookup"><span data-stu-id="355b9-110">Note that it is not possible for a thrown exception to escape a `filter` exception clause, so there is always a Leave notification in that case.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="355b9-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="355b9-111">Requirements</span></span>  
 <span data-ttu-id="355b9-112">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="355b9-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="355b9-113">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="355b9-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="355b9-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="355b9-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="355b9-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="355b9-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="355b9-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="355b9-116">See also</span></span>

- [<span data-ttu-id="355b9-117">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="355b9-117">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="355b9-118">ICorProfilerInfo2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="355b9-118">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
