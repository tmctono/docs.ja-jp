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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5e12410ab9886055dca8c3f9103c1e56475c2d5e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775155"
---
# <a name="corprfexclauseinfo-structure"></a><span data-ttu-id="12f07-102">COR_PRF_EX_CLAUSE_INFO 構造体</span><span class="sxs-lookup"><span data-stu-id="12f07-102">COR_PRF_EX_CLAUSE_INFO Structure</span></span>
<span data-ttu-id="12f07-103">特定の例外句インスタンスおよび関連するフレームに関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="12f07-103">Stores information about a specific exception clause instance and its associated frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12f07-104">構文</span><span class="sxs-lookup"><span data-stu-id="12f07-104">Syntax</span></span>  
  
```  
typedef struct COR_PRF_EX_CLAUSE_INFO {  
    COR_PRF_CLAUSE_TYPE clauseType;  
    UINT_PTR programCounter;  
    UINT_PTR framePointer;  
    UINT_PTR shadowStackPointer;  
} COR_PRF_EX_CLAUSE_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="12f07-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="12f07-105">Members</span></span>  
  
|<span data-ttu-id="12f07-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="12f07-106">Member</span></span>|<span data-ttu-id="12f07-107">説明</span><span class="sxs-lookup"><span data-stu-id="12f07-107">Description</span></span>|  
|------------|-----------------|  
|`clauseType`|<span data-ttu-id="12f07-108">値、 [COR_PRF_CLAUSE_TYPE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-clause-type-enumeration.md)例外句入力したコードまたは左の種類を指定する列挙体。</span><span class="sxs-lookup"><span data-stu-id="12f07-108">A value of the [COR_PRF_CLAUSE_TYPE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-clause-type-enumeration.md) enumeration that specifies the type of exception clause the code just entered or left.</span></span>|  
|`programCounter`|<span data-ttu-id="12f07-109">句のハンドラーのネイティブ エントリ ポイント: X86 EIP レジスタの内容など。</span><span class="sxs-lookup"><span data-stu-id="12f07-109">The native entry point of the clause handler — for example, the contents of the X86 EIP register.</span></span>|  
|`framePointer`|<span data-ttu-id="12f07-110">句のハンドラーの論理フレームへのポインター: X86 EBP レジスタの内容など。</span><span class="sxs-lookup"><span data-stu-id="12f07-110">The pointer to the logical frame for the clause handler — for example, the contents of the X86 EBP register.</span></span>|  
|`shadowStackPointer`|<span data-ttu-id="12f07-111">シャドウ スタックへのポインター。</span><span class="sxs-lookup"><span data-stu-id="12f07-111">The pointer to the shadow stack.</span></span> <span data-ttu-id="12f07-112">この値は、BSP レジスタの内容は、IA64 にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="12f07-112">This value is the contents of the BSP register and applies only to IA64.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="12f07-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="12f07-113">Remarks</span></span>  
 <span data-ttu-id="12f07-114">例外の通知が受信されると、 [icorprofilerinfo 2::getnotifiedexceptionclauseinfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md)例外句のネイティブのアドレスとフレームの情報を取得するために使用できます (`catch` / `finally`/フィルター) を実行するのには、またはが実行されています。</span><span class="sxs-lookup"><span data-stu-id="12f07-114">When an exception notification is received, [ICorProfilerInfo2::GetNotifiedExceptionClauseInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md) can be used to get the native address and frame information for the exception clause (`catch`/`finally`/filter) that is about to be run or has just been run.</span></span>  
  
 <span data-ttu-id="12f07-115">例外句の実行には、共通言語ランタイム (CLR) からこれらのコールバックが含まれます。</span><span class="sxs-lookup"><span data-stu-id="12f07-115">Execution of an exception clause involves these callbacks from the common language runtime (CLR):</span></span>  
  
- [<span data-ttu-id="12f07-116">ICorProfilerCallback::ExceptionCatcherEnter</span><span class="sxs-lookup"><span data-stu-id="12f07-116">ICorProfilerCallback::ExceptionCatcherEnter</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherenter-method.md)  
  
- [<span data-ttu-id="12f07-117">ICorProfilerCallback::ExceptionUnwindFinallyEnter</span><span class="sxs-lookup"><span data-stu-id="12f07-117">ICorProfilerCallback::ExceptionUnwindFinallyEnter</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyenter-method.md)  
  
- [<span data-ttu-id="12f07-118">ICorProfilerCallback::ExceptionSearchFilterEnter</span><span class="sxs-lookup"><span data-stu-id="12f07-118">ICorProfilerCallback::ExceptionSearchFilterEnter</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterenter-method.md)  
  
- [<span data-ttu-id="12f07-119">ICorProfilerCallback::ExceptionCatcherLeave</span><span class="sxs-lookup"><span data-stu-id="12f07-119">ICorProfilerCallback::ExceptionCatcherLeave</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherleave-method.md)  
  
- [<span data-ttu-id="12f07-120">ICorProfilerCallback::ExceptionUnwindFinallyLeave</span><span class="sxs-lookup"><span data-stu-id="12f07-120">ICorProfilerCallback::ExceptionUnwindFinallyLeave</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyleave-method.md)  
  
- [<span data-ttu-id="12f07-121">ICorProfilerCallback::ExceptionSearchFilterLeave</span><span class="sxs-lookup"><span data-stu-id="12f07-121">ICorProfilerCallback::ExceptionSearchFilterLeave</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterleave-method.md)  
  
## <a name="requirements"></a><span data-ttu-id="12f07-122">必要条件</span><span class="sxs-lookup"><span data-stu-id="12f07-122">Requirements</span></span>  
 <span data-ttu-id="12f07-123">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="12f07-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="12f07-124">**ヘッダー:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="12f07-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="12f07-125">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="12f07-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="12f07-126">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="12f07-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12f07-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="12f07-127">See also</span></span>

- [<span data-ttu-id="12f07-128">構造体のプロファイリング</span><span class="sxs-lookup"><span data-stu-id="12f07-128">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
