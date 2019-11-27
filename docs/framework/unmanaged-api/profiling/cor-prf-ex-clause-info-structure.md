---
title: COR_PRF_EX_CLAUSE_INFO 構造体
ms.date: 03/30/2017
api_name:
- COR_PRF_EX_CLAUSE_INFO
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_EX_CLAUSE_INFO
helpviewer_keywords:
- COR_PRF_EX_CLAUSE_INFO structure [.NET Framework profiling]
ms.assetid: 7d0d6fb7-bc9d-40f0-8163-c0d162eaba7d
topic_type:
- apiref
ms.openlocfilehash: df4bfe69b22439073342693a03376a0b506f9c70
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74428380"
---
# <a name="cor_prf_ex_clause_info-structure"></a><span data-ttu-id="c34f4-102">COR_PRF_EX_CLAUSE_INFO 構造体</span><span class="sxs-lookup"><span data-stu-id="c34f4-102">COR_PRF_EX_CLAUSE_INFO Structure</span></span>
<span data-ttu-id="c34f4-103">特定の例外句インスタンスおよび関連するフレームに関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="c34f4-103">Stores information about a specific exception clause instance and its associated frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c34f4-104">構文</span><span class="sxs-lookup"><span data-stu-id="c34f4-104">Syntax</span></span>  
  
```cpp  
typedef struct COR_PRF_EX_CLAUSE_INFO {  
    COR_PRF_CLAUSE_TYPE clauseType;  
    UINT_PTR programCounter;  
    UINT_PTR framePointer;  
    UINT_PTR shadowStackPointer;  
} COR_PRF_EX_CLAUSE_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="c34f4-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="c34f4-105">Members</span></span>  
  
|<span data-ttu-id="c34f4-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="c34f4-106">Member</span></span>|<span data-ttu-id="c34f4-107">説明</span><span class="sxs-lookup"><span data-stu-id="c34f4-107">Description</span></span>|  
|------------|-----------------|  
|`clauseType`|<span data-ttu-id="c34f4-108">入力または左にあるコードの例外句の種類を指定する[COR_PRF_CLAUSE_TYPE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-clause-type-enumeration.md)列挙体の値。</span><span class="sxs-lookup"><span data-stu-id="c34f4-108">A value of the [COR_PRF_CLAUSE_TYPE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-clause-type-enumeration.md) enumeration that specifies the type of exception clause the code just entered or left.</span></span>|  
|`programCounter`|<span data-ttu-id="c34f4-109">句ハンドラーのネイティブエントリポイント (たとえば、X86 EIP レジスタの内容)。</span><span class="sxs-lookup"><span data-stu-id="c34f4-109">The native entry point of the clause handler — for example, the contents of the X86 EIP register.</span></span>|  
|`framePointer`|<span data-ttu-id="c34f4-110">句ハンドラーの論理フレームへのポインター。たとえば、X86 EBP レジスタの内容。</span><span class="sxs-lookup"><span data-stu-id="c34f4-110">The pointer to the logical frame for the clause handler — for example, the contents of the X86 EBP register.</span></span>|  
|`shadowStackPointer`|<span data-ttu-id="c34f4-111">シャドウスタックへのポインター。</span><span class="sxs-lookup"><span data-stu-id="c34f4-111">The pointer to the shadow stack.</span></span> <span data-ttu-id="c34f4-112">この値は、BSP レジスタの内容であり、IA64 にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="c34f4-112">This value is the contents of the BSP register and applies only to IA64.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c34f4-113">コメント</span><span class="sxs-lookup"><span data-stu-id="c34f4-113">Remarks</span></span>  
 <span data-ttu-id="c34f4-114">例外通知を受信すると、 [ICorProfilerInfo2:: GetNotifiedExceptionClauseInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md)を使用して、実行される、または実行されようとしている例外句 (`catch`/`finally`/フィルター) のネイティブアドレスとフレーム情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="c34f4-114">When an exception notification is received, [ICorProfilerInfo2::GetNotifiedExceptionClauseInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md) can be used to get the native address and frame information for the exception clause (`catch`/`finally`/filter) that is about to be run or has just been run.</span></span>  
  
 <span data-ttu-id="c34f4-115">Exception 句の実行には、共通言語ランタイム (CLR) からのこれらのコールバックが含まれます。</span><span class="sxs-lookup"><span data-stu-id="c34f4-115">Execution of an exception clause involves these callbacks from the common language runtime (CLR):</span></span>  
  
- [<span data-ttu-id="c34f4-116">ICorProfilerCallback:: ExceptionCatcherEnter</span><span class="sxs-lookup"><span data-stu-id="c34f4-116">ICorProfilerCallback::ExceptionCatcherEnter</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherenter-method.md)  
  
- [<span data-ttu-id="c34f4-117">ICorProfilerCallback:: ExceptionUnwindFinallyEnter</span><span class="sxs-lookup"><span data-stu-id="c34f4-117">ICorProfilerCallback::ExceptionUnwindFinallyEnter</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyenter-method.md)  
  
- [<span data-ttu-id="c34f4-118">ICorProfilerCallback:: ExceptionSearchFilterEnter</span><span class="sxs-lookup"><span data-stu-id="c34f4-118">ICorProfilerCallback::ExceptionSearchFilterEnter</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterenter-method.md)  
  
- [<span data-ttu-id="c34f4-119">ICorProfilerCallback:: ExceptionCatcherLeave</span><span class="sxs-lookup"><span data-stu-id="c34f4-119">ICorProfilerCallback::ExceptionCatcherLeave</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherleave-method.md)  
  
- [<span data-ttu-id="c34f4-120">ICorProfilerCallback:: ExceptionUnwindFinallyLeave</span><span class="sxs-lookup"><span data-stu-id="c34f4-120">ICorProfilerCallback::ExceptionUnwindFinallyLeave</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyleave-method.md)  
  
- [<span data-ttu-id="c34f4-121">ICorProfilerCallback:: ExceptionSearchFilterLeave</span><span class="sxs-lookup"><span data-stu-id="c34f4-121">ICorProfilerCallback::ExceptionSearchFilterLeave</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterleave-method.md)  
  
## <a name="requirements"></a><span data-ttu-id="c34f4-122">要件</span><span class="sxs-lookup"><span data-stu-id="c34f4-122">Requirements</span></span>  
 <span data-ttu-id="c34f4-123">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c34f4-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c34f4-124">**ヘッダー:** Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="c34f4-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="c34f4-125">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c34f4-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c34f4-126">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c34f4-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c34f4-127">参照</span><span class="sxs-lookup"><span data-stu-id="c34f4-127">See also</span></span>

- [<span data-ttu-id="c34f4-128">構造体のプロファイリング</span><span class="sxs-lookup"><span data-stu-id="c34f4-128">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
