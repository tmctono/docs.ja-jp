---
title: EClrOperation 列挙型
ms.date: 03/30/2017
api_name:
- EClrOperation
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EClrOperation
helpviewer_keywords:
- EClrOperation enumeration [.NET Framework hosting]
ms.assetid: 5aef6808-5aac-4b2f-a2c7-fee1575c55ed
topic_type:
- apiref
ms.openlocfilehash: 6becc44b061ff2baac63437b6a72375d1c3735b2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131161"
---
# <a name="eclroperation-enumeration"></a><span data-ttu-id="e1077-102">EClrOperation 列挙型</span><span class="sxs-lookup"><span data-stu-id="e1077-102">EClrOperation Enumeration</span></span>
<span data-ttu-id="e1077-103">ホストがポリシーアクションを適用できる操作のセットについて説明します。</span><span class="sxs-lookup"><span data-stu-id="e1077-103">Describes the set of operations for which a host can apply policy actions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1077-104">構文</span><span class="sxs-lookup"><span data-stu-id="e1077-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    OPR_ThreadAbort,  
    OPR_ThreadRudeAbortInNonCriticalRegion,  
    OPR_ThreadRudeAbortInCriticalRegion,  
    OPR_AppDomainUnload,  
    OPR_AppDomainRudeUnload,  
    OPR_ProcessExit,  
    OPR_FinalizerRun  
} EClrOperation;  
```  
  
## <a name="members"></a><span data-ttu-id="e1077-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="e1077-105">Members</span></span>  
  
|<span data-ttu-id="e1077-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="e1077-106">Member</span></span>|<span data-ttu-id="e1077-107">説明</span><span class="sxs-lookup"><span data-stu-id="e1077-107">Description</span></span>|  
|------------|-----------------|  
|`OPR_AppDomainRudeUnload`|<span data-ttu-id="e1077-108">ホストは、<xref:System.AppDomain> が正常でない (ルー) 方法でアンロードされたときに実行されるポリシーアクションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="e1077-108">The host can specify policy actions to be taken when an <xref:System.AppDomain> is unloaded in a non-graceful (rude) manner.</span></span>|  
|`OPR_AppDomainUnload`|<span data-ttu-id="e1077-109">ホストは、<xref:System.AppDomain> がアンロードされたときに実行するポリシーアクションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="e1077-109">The host can specify policy actions to be taken when an <xref:System.AppDomain> is unloaded.</span></span>|  
|`OPR_FinalizerRun`|<span data-ttu-id="e1077-110">ホストは、ファイナライザーの実行時に実行されるポリシーアクションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="e1077-110">The host can specify policy actions to be taken when finalizers run.</span></span>|  
|`OPR_ProcessExit`|<span data-ttu-id="e1077-111">ホストは、プロセスが終了したときに実行するポリシーアクションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="e1077-111">The host can specify policy actions to be taken when the process exits.</span></span>|  
|`OPR_ThreadAbort`|<span data-ttu-id="e1077-112">ホストは、スレッドが中止されたときに実行されるポリシーアクションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="e1077-112">The host can specify policy actions to be taken when a thread is aborted.</span></span>|  
|`OPR_ThreadRudeAbortInCriticalRegion`|<span data-ttu-id="e1077-113">ホストは、コードの重要な領域でルースレッドの中止が発生したときに実行されるポリシーアクションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="e1077-113">The host can specify policy actions to be taken when a rude thread abort occurs in a critical region of code.</span></span>|  
|`OPR_ThreadRudeAbortInNonCriticalRegion`|<span data-ttu-id="e1077-114">ホストは、非クリティカルなコード領域で、ルードスレッドの中止が発生したときに実行するポリシーアクションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="e1077-114">The host can specify policy actions to be take when a rude thread abort occurs in a non-critical region of code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e1077-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="e1077-115">Remarks</span></span>  
 <span data-ttu-id="e1077-116">共通言語ランタイム (CLR) の信頼性インフラストラクチャでは、コードの重要な領域で発生する中止とリソース割り当ての失敗と、コードの重要ではない領域で発生するエラーを区別します。</span><span class="sxs-lookup"><span data-stu-id="e1077-116">The common language runtime (CLR) reliability infrastructure distinguishes between aborts and resource allocation failures that occur in critical regions of code and those that occur in non-critical regions of code.</span></span> <span data-ttu-id="e1077-117">この区別は、コード内でエラーが発生した場所に応じて、ホストがさまざまなポリシーを設定できるように設計されています。</span><span class="sxs-lookup"><span data-stu-id="e1077-117">This distinction is designed to allow hosts to set different policies depending on where a failure occurs in the code.</span></span>  
  
 <span data-ttu-id="e1077-118">*コードの重要な領域*は、タスクの中止、またはリソースの要求を完了できないことが CLR によって保証されない場合、現在のタスクにのみ影響します。</span><span class="sxs-lookup"><span data-stu-id="e1077-118">A *critical region of code* is any space where the CLR cannot guarantee that aborting a task or failing to complete a request for resources will affect only the current task.</span></span> <span data-ttu-id="e1077-119">たとえば、タスクがロックを保持していて、メモリ割り当て要求の発生時に失敗したことを示す HRESULT を受け取った場合、<xref:System.AppDomain> に他のタスクが含まれている可能性があるため、そのタスクを中止して <xref:System.AppDomain>の安定性を確保するだけでは不十分です。同じロックを待機しています。</span><span class="sxs-lookup"><span data-stu-id="e1077-119">For example, if a task is holding a lock and receives an HRESULT that indicates failure upon making a memory allocation request, it is insufficient simply to abort that task to ensure the stability of the <xref:System.AppDomain>, because the <xref:System.AppDomain> might contain other tasks waiting for the same lock.</span></span> <span data-ttu-id="e1077-120">現在のタスクを破棄すると、その他のタスクが応答を停止する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e1077-120">To abandon the current task might cause those other tasks to stop responding.</span></span> <span data-ttu-id="e1077-121">このような場合、ホストは、潜在的に不安定になるリスクではなく、<xref:System.AppDomain> 全体をアンロードする機能を必要とします。</span><span class="sxs-lookup"><span data-stu-id="e1077-121">In such a case, the host needs the ability to unload the entire <xref:System.AppDomain> rather than risk potential instability.</span></span>  
  
 <span data-ttu-id="e1077-122">一方、クリティカルでは*ないコード領域*とは、CLR が、エラーが発生したタスクのみに影響を与えることを CLR が保証できる領域です。</span><span class="sxs-lookup"><span data-stu-id="e1077-122">A *non-critical region of code*, on the other hand, is a region where the CLR can guarantee that an abort or a failure will affect only the task upon which the error occurs.</span></span>  
  
 <span data-ttu-id="e1077-123">また、この CLR では、グレースフルとグレースフルの (ルード) 中止が区別されます。</span><span class="sxs-lookup"><span data-stu-id="e1077-123">The CLR also distinguishes between graceful and non-graceful (rude) aborts.</span></span> <span data-ttu-id="e1077-124">一般に、通常または正常な中止では、タスクを中止する前に例外処理ルーチンとファイナライザーを実行するすべての作業を行います。ただし、ルードアボートではこのような保証は行われません。</span><span class="sxs-lookup"><span data-stu-id="e1077-124">In general, a normal or graceful abort makes every effort to run exception-handling routines and finalizers before aborting a task, while a rude abort makes no such guarantees.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e1077-125">［要件］</span><span class="sxs-lookup"><span data-stu-id="e1077-125">Requirements</span></span>  
 <span data-ttu-id="e1077-126">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e1077-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1077-127">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="e1077-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e1077-128">**ライブラリ:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="e1077-128">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e1077-129">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1077-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1077-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="e1077-130">See also</span></span>

- [<span data-ttu-id="e1077-131">EClrFailure 列挙型</span><span class="sxs-lookup"><span data-stu-id="e1077-131">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [<span data-ttu-id="e1077-132">EPolicyAction 列挙型</span><span class="sxs-lookup"><span data-stu-id="e1077-132">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="e1077-133">ICLRPolicyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e1077-133">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="e1077-134">IHostPolicyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e1077-134">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
- [<span data-ttu-id="e1077-135">ホスティングの列挙型</span><span class="sxs-lookup"><span data-stu-id="e1077-135">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
