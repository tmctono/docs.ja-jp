---
title: COR_PRF_SUSPEND_REASON 列挙型
ms.date: 03/30/2017
api_name:
- COR_PRF_SUSPEND_REASON
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_SUSPEND_REASON
helpviewer_keywords:
- COR_PRF_SUSPEND_REASON enumeration [.NET Framework profiling]
ms.assetid: 75594833-bed3-47b2-a426-b75c5fe6fbcf
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 21533b5173bcd91d0c944fbde4eafc9817de8315
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61598988"
---
# <a name="corprfsuspendreason-enumeration"></a><span data-ttu-id="7c1a2-102">COR_PRF_SUSPEND_REASON 列挙型</span><span class="sxs-lookup"><span data-stu-id="7c1a2-102">COR_PRF_SUSPEND_REASON Enumeration</span></span>
<span data-ttu-id="7c1a2-103">ランタイムが中断された理由を示します。</span><span class="sxs-lookup"><span data-stu-id="7c1a2-103">Indicates the reason that the runtime is suspended.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c1a2-104">構文</span><span class="sxs-lookup"><span data-stu-id="7c1a2-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_SUSPEND_OTHER                   = 0x00,  
    COR_PRF_SUSPEND_FOR_GC                  = 0x01,  
    COR_PRF_SUSPEND_FOR_APPDOMAIN_SHUTDOWN  = 0x02,  
    COR_PRF_SUSPEND_FOR_CODE_PITCHING       = 0x03,  
    COR_PRF_SUSPEND_FOR_SHUTDOWN            = 0x04,  
    COR_PRF_SUSPEND_FOR_INPROC_DEBUGGER     = 0x06,  
    COR_PRF_SUSPEND_FOR_GC_PREP             = 0x07,    COR_PRF_SUSPEND_FOR_REJIT               = 8  
} COR_PRF_SUSPEND_REASON;  
```  
  
## <a name="members"></a><span data-ttu-id="7c1a2-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="7c1a2-105">Members</span></span>  
  
|<span data-ttu-id="7c1a2-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="7c1a2-106">Member</span></span>|<span data-ttu-id="7c1a2-107">説明</span><span class="sxs-lookup"><span data-stu-id="7c1a2-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FIELD_SUSPEND_OTHER`|<span data-ttu-id="7c1a2-108">不明な理由により、ランタイムは中断されます。</span><span class="sxs-lookup"><span data-stu-id="7c1a2-108">The runtime is suspended for an unspecified reason.</span></span>|  
|`COR_PRF_FIELD_SUSPEND_FOR_GC`|<span data-ttu-id="7c1a2-109">ガベージ コレクションの要求にサービス ランタイムは中断されます。</span><span class="sxs-lookup"><span data-stu-id="7c1a2-109">The runtime is suspended to service a garbage collection request.</span></span><br /><br /> <span data-ttu-id="7c1a2-110">ガベージ コレクションに関連するコールバックの間に発生、 [icorprofilercallback::runtimesuspendfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md)と[icorprofilercallback::runtimeresumestarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md)コールバック。</span><span class="sxs-lookup"><span data-stu-id="7c1a2-110">The garbage collection-related callbacks occur between the [ICorProfilerCallback::RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) and [ICorProfilerCallback::RuntimeResumeStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) callbacks.</span></span>|  
|`COR_PRF_FIELD_SUSPEND_FOR_APPDOMAIN_SHUTDOWN`|<span data-ttu-id="7c1a2-111">ランタイムは、中断できるように、`AppDomain`シャット ダウンすることができます。</span><span class="sxs-lookup"><span data-stu-id="7c1a2-111">The runtime is suspended so that an `AppDomain` can be shut down.</span></span><br /><br /> <span data-ttu-id="7c1a2-112">どのスレッドは、ランタイムが決定されます、ランタイムが中断されている間、`AppDomain`はシャット ダウンして復帰するときに中止するように設定されています。</span><span class="sxs-lookup"><span data-stu-id="7c1a2-112">While the runtime is suspended, the runtime will determine which threads are in the `AppDomain` that is being shut down and set them to abort when they resume.</span></span> <span data-ttu-id="7c1a2-113">あるない`AppDomain`-この中断の間の特定のコールバック。</span><span class="sxs-lookup"><span data-stu-id="7c1a2-113">There are no `AppDomain`-specific callbacks during this suspension.</span></span>|  
|`COR_PRF_FIELD_SUSPEND_FOR_CODE_PITCHING`|<span data-ttu-id="7c1a2-114">コード ピッチが実行できるように、ランタイムは中断されます。</span><span class="sxs-lookup"><span data-stu-id="7c1a2-114">The runtime is suspended so that code pitching can occur.</span></span><br /><br /> <span data-ttu-id="7c1a2-115">コード ピッチが場合にのみ、ジャストイン タイム (JIT) コンパイラ active コード ピッチが有効になっているが発生します。</span><span class="sxs-lookup"><span data-stu-id="7c1a2-115">Code pitching ensues only when the just-in-time (JIT) compiler is active with code pitching enabled.</span></span> <span data-ttu-id="7c1a2-116">ピッチングのコールバックの間で発生するコード、`ICorProfilerCallback::RuntimeSuspendFinished`と`ICorProfilerCallback::RuntimeResumeStarted`コールバック。</span><span class="sxs-lookup"><span data-stu-id="7c1a2-116">Code pitching callbacks occur between the `ICorProfilerCallback::RuntimeSuspendFinished` and `ICorProfilerCallback::RuntimeResumeStarted` callbacks.</span></span> <span data-ttu-id="7c1a2-117">**注:** この値は 2.0 では使用されないように、CLR JIT は、.NET Framework version 2.0 で関数をピッチいないします。</span><span class="sxs-lookup"><span data-stu-id="7c1a2-117">**Note:**  The CLR JIT does not pitch functions in the .NET Framework version 2.0, so this value is not used in 2.0.</span></span>|  
|`COR_PRF_FIELD_SUSPEND_FOR_SHUTDOWN`|<span data-ttu-id="7c1a2-118">ランタイムが中断されるため、シャット ダウンできます。</span><span class="sxs-lookup"><span data-stu-id="7c1a2-118">The runtime is suspended so that it can shut down.</span></span> <span data-ttu-id="7c1a2-119">操作を完了するすべてのスレッドが中断する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7c1a2-119">It must suspend all threads to complete the operation.</span></span>|  
|`COR_PRF_FIELD_SUSPEND_FOR_INPROC_DEBUGGER`|<span data-ttu-id="7c1a2-120">ランタイムは、インプロセス デバッグの中断します。</span><span class="sxs-lookup"><span data-stu-id="7c1a2-120">The runtime is suspended for in-process debugging.</span></span>|  
|`COR_PRF_FIELD_SUSPEND_FOR_GC_PREP`|<span data-ttu-id="7c1a2-121">ランタイムは、ガベージ コレクションの準備を中断します。</span><span class="sxs-lookup"><span data-stu-id="7c1a2-121">The runtime is suspended to prepare for a garbage collection.</span></span>|  
|`COR_PRF_SUSPEND_FOR_REJIT`|<span data-ttu-id="7c1a2-122">ランタイムの JIT 再コンパイルは中断されます。</span><span class="sxs-lookup"><span data-stu-id="7c1a2-122">The runtime is suspended for JIT recompilation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7c1a2-123">Remarks</span><span class="sxs-lookup"><span data-stu-id="7c1a2-123">Remarks</span></span>  
 <span data-ttu-id="7c1a2-124">アンマネージ コードに含まれるすべてのランタイム スレッドは、この時点で、中断されます、ランタイムが再開されるまで、実行時の再入力するまで実行を続行が許可されます。</span><span class="sxs-lookup"><span data-stu-id="7c1a2-124">All runtime threads that are in unmanaged code are permitted to continue running until they try to re-enter the runtime, at which point they will also be suspended until the runtime resumes.</span></span> <span data-ttu-id="7c1a2-125">これは、ランタイムに入る新しいスレッドにも適用されます。</span><span class="sxs-lookup"><span data-stu-id="7c1a2-125">This also applies to new threads that enter the runtime.</span></span> <span data-ttu-id="7c1a2-126">ランタイム内のすべてのスレッドは可能なコード内にある場合はすぐに中断または、割り込み可能なコードに到達したときに中断します。</span><span class="sxs-lookup"><span data-stu-id="7c1a2-126">All threads within the runtime are either suspended immediately if they are in interruptible code, or asked to suspend when they do reach interruptible code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c1a2-127">必要条件</span><span class="sxs-lookup"><span data-stu-id="7c1a2-127">Requirements</span></span>  
 <span data-ttu-id="7c1a2-128">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7c1a2-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c1a2-129">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7c1a2-129">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7c1a2-130">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7c1a2-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7c1a2-131">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c1a2-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c1a2-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="7c1a2-132">See also</span></span>

- [<span data-ttu-id="7c1a2-133">列挙型のプロファイリング</span><span class="sxs-lookup"><span data-stu-id="7c1a2-133">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
