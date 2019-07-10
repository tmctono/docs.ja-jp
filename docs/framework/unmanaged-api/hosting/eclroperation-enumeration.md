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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 01b000ed3d75ddb6a7882cb8f03ff2cec64fb9fe
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67767879"
---
# <a name="eclroperation-enumeration"></a><span data-ttu-id="6e562-102">EClrOperation 列挙型</span><span class="sxs-lookup"><span data-stu-id="6e562-102">EClrOperation Enumeration</span></span>
<span data-ttu-id="6e562-103">ホストがポリシーのアクションを適用できる操作のセットについて説明します。</span><span class="sxs-lookup"><span data-stu-id="6e562-103">Describes the set of operations for which a host can apply policy actions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e562-104">構文</span><span class="sxs-lookup"><span data-stu-id="6e562-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="6e562-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="6e562-105">Members</span></span>  
  
|<span data-ttu-id="6e562-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="6e562-106">Member</span></span>|<span data-ttu-id="6e562-107">説明</span><span class="sxs-lookup"><span data-stu-id="6e562-107">Description</span></span>|  
|------------|-----------------|  
|`OPR_AppDomainRudeUnload`|<span data-ttu-id="6e562-108">ホストは、ときに実行するポリシーのアクションを指定できます、<xref:System.AppDomain>非グレースフル (ルード) 方式でモジュールはアンロードされます。</span><span class="sxs-lookup"><span data-stu-id="6e562-108">The host can specify policy actions to be taken when an <xref:System.AppDomain> is unloaded in a non-graceful (rude) manner.</span></span>|  
|`OPR_AppDomainUnload`|<span data-ttu-id="6e562-109">ホストは、ときに実行するポリシーのアクションを指定できます、<xref:System.AppDomain>がアンロードされます。</span><span class="sxs-lookup"><span data-stu-id="6e562-109">The host can specify policy actions to be taken when an <xref:System.AppDomain> is unloaded.</span></span>|  
|`OPR_FinalizerRun`|<span data-ttu-id="6e562-110">ホストは、ファイナライザーを実行するときに実行されるポリシーのアクションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="6e562-110">The host can specify policy actions to be taken when finalizers run.</span></span>|  
|`OPR_ProcessExit`|<span data-ttu-id="6e562-111">ホストは、プロセスが終了したときに実行されるポリシーのアクションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="6e562-111">The host can specify policy actions to be taken when the process exits.</span></span>|  
|`OPR_ThreadAbort`|<span data-ttu-id="6e562-112">ホストは、スレッドが中止されたときに実行されるポリシーのアクションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="6e562-112">The host can specify policy actions to be taken when a thread is aborted.</span></span>|  
|`OPR_ThreadRudeAbortInCriticalRegion`|<span data-ttu-id="6e562-113">ホストは、コードのクリティカル領域でルード スレッドの中止が発生したときに実行されるポリシーのアクションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="6e562-113">The host can specify policy actions to be taken when a rude thread abort occurs in a critical region of code.</span></span>|  
|`OPR_ThreadRudeAbortInNonCriticalRegion`|<span data-ttu-id="6e562-114">ホストは、重大でないコードの領域でルード スレッドの中止が発生したときに実行されるポリシーのアクションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="6e562-114">The host can specify policy actions to be take when a rude thread abort occurs in a non-critical region of code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6e562-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="6e562-115">Remarks</span></span>  
 <span data-ttu-id="6e562-116">共通言語ランタイム (CLR) の信頼性インフラストラクチャは、中止とリソース内のコードとコードの非クリティカル領域で発生した重要な領域の割り当てエラーを区別します。</span><span class="sxs-lookup"><span data-stu-id="6e562-116">The common language runtime (CLR) reliability infrastructure distinguishes between aborts and resource allocation failures that occur in critical regions of code and those that occur in non-critical regions of code.</span></span> <span data-ttu-id="6e562-117">この区別は、ホスト コードに障害が発生した場所に応じて異なるポリシーを設定できるように設計されています。</span><span class="sxs-lookup"><span data-stu-id="6e562-117">This distinction is designed to allow hosts to set different policies depending on where a failure occurs in the code.</span></span>  
  
 <span data-ttu-id="6e562-118">A*コードのクリティカル領域*は CLR がそのタスクを中止またはをリソースは、現在のタスクのみに影響を与えるは、要求を完了できない状態を保証できない領域。</span><span class="sxs-lookup"><span data-stu-id="6e562-118">A *critical region of code* is any space where the CLR cannot guarantee that aborting a task or failing to complete a request for resources will affect only the current task.</span></span> <span data-ttu-id="6e562-119">たとえば、タスクは、ロックが保持するいると、メモリの割り当て要求時にエラーを示す HRESULT を受け取るはの安定性を確保するには、そのタスクを中止するだけでは不十分、<xref:System.AppDomain>ため、<xref:System.AppDomain>他を含めることができますタスクが同じロックを待っています。</span><span class="sxs-lookup"><span data-stu-id="6e562-119">For example, if a task is holding a lock and receives an HRESULT that indicates failure upon making a memory allocation request, it is insufficient simply to abort that task to ensure the stability of the <xref:System.AppDomain>, because the <xref:System.AppDomain> might contain other tasks waiting for the same lock.</span></span> <span data-ttu-id="6e562-120">現在を破棄するには、タスクにその他のタスク応答を停止することがあります。</span><span class="sxs-lookup"><span data-stu-id="6e562-120">To abandon the current task might cause those other tasks to stop responding.</span></span> <span data-ttu-id="6e562-121">このような場合は、全体をアンロードする機能、ホストする必要があります。<xref:System.AppDomain>リスクの潜在的なが不安定になるのではなく。</span><span class="sxs-lookup"><span data-stu-id="6e562-121">In such a case, the host needs the ability to unload the entire <xref:System.AppDomain> rather than risk potential instability.</span></span>  
  
 <span data-ttu-id="6e562-122">A*コードの領域が重大でない*CLR が中断または障害の影響が、エラーが発生しているタスクだけことを保証できるリージョンは、その一方で、します。</span><span class="sxs-lookup"><span data-stu-id="6e562-122">A *non-critical region of code*, on the other hand, is a region where the CLR can guarantee that an abort or a failure will affect only the task upon which the error occurs.</span></span>  
  
 <span data-ttu-id="6e562-123">CLR は、グレースフルと非グレースフル (ルード) 中止間も区別します。</span><span class="sxs-lookup"><span data-stu-id="6e562-123">The CLR also distinguishes between graceful and non-graceful (rude) aborts.</span></span> <span data-ttu-id="6e562-124">一般に、正常または適切な中止は、ルード中止はこのような保証をいたしません中にタスクを中止する前に、例外処理ルーチンとファイナライザーを実行するよう努力します。</span><span class="sxs-lookup"><span data-stu-id="6e562-124">In general, a normal or graceful abort makes every effort to run exception-handling routines and finalizers before aborting a task, while a rude abort makes no such guarantees.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e562-125">必要条件</span><span class="sxs-lookup"><span data-stu-id="6e562-125">Requirements</span></span>  
 <span data-ttu-id="6e562-126">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6e562-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6e562-127">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6e562-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6e562-128">**ライブラリ:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6e562-128">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6e562-129">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6e562-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e562-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="6e562-130">See also</span></span>

- [<span data-ttu-id="6e562-131">EClrFailure 列挙型</span><span class="sxs-lookup"><span data-stu-id="6e562-131">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [<span data-ttu-id="6e562-132">EPolicyAction 列挙型</span><span class="sxs-lookup"><span data-stu-id="6e562-132">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="6e562-133">ICLRPolicyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6e562-133">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="6e562-134">IHostPolicyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6e562-134">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
- [<span data-ttu-id="6e562-135">ホスティングの列挙型</span><span class="sxs-lookup"><span data-stu-id="6e562-135">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
