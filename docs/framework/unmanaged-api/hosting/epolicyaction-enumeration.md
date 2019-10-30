---
title: EPolicyAction 列挙型
ms.date: 03/30/2017
api_name:
- EPolicyAction
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EPolicyAction
helpviewer_keywords:
- EPolicyAction enumeration [.NET Framework hosting]
ms.assetid: 72dd76ba-239e-45ac-9ded-318fb07d6c6d
topic_type:
- apiref
ms.openlocfilehash: eaba6b2166a82cfe825ffb98db515e24d4656462
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138233"
---
# <a name="epolicyaction-enumeration"></a><span data-ttu-id="189af-102">EPolicyAction 列挙型</span><span class="sxs-lookup"><span data-stu-id="189af-102">EPolicyAction Enumeration</span></span>
<span data-ttu-id="189af-103">[EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)によって記述された操作や[eclrfailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)によって記述されたエラーについて、ホストが設定できるポリシーアクションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="189af-103">Describes the policy actions the host can set for operations described by [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) and failures described by [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="189af-104">構文</span><span class="sxs-lookup"><span data-stu-id="189af-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eNoAction,  
    eThrowException,  
    eAbortThread,  
    eRudeAbortThread,  
    eUnloadAppDomain,  
    eRudeUnloadAppDomain,  
    eExitProcess,  
    eFastExitProcess,  
    eRudeExitProcess,  
    eDisableRuntime  
} EPolicyAction;  
```  
  
## <a name="members"></a><span data-ttu-id="189af-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="189af-105">Members</span></span>  
  
|<span data-ttu-id="189af-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="189af-106">Member</span></span>|<span data-ttu-id="189af-107">説明</span><span class="sxs-lookup"><span data-stu-id="189af-107">Description</span></span>|  
|------------|-----------------|  
|`eAbortThread`|<span data-ttu-id="189af-108">共通言語ランタイム (CLR) がスレッドを正常に中止する必要があることを指定します。</span><span class="sxs-lookup"><span data-stu-id="189af-108">Specifies that the common language runtime (CLR) should abort the thread gracefully.</span></span> <span data-ttu-id="189af-109">正常な中止には、すべての `finally` ブロック、スレッドの中止に関連するすべての `catch` ブロック、およびファイナライザーを実行する試行が含まれます。</span><span class="sxs-lookup"><span data-stu-id="189af-109">A graceful abort includes attempts to run all `finally` blocks, any `catch` blocks related to thread aborts, and finalizers.</span></span>|  
|`eDisableRuntime`|<span data-ttu-id="189af-110">CLR が無効化された状態になるように指定します。</span><span class="sxs-lookup"><span data-stu-id="189af-110">Specifies that the CLR should enter a disabled state.</span></span> <span data-ttu-id="189af-111">影響を受けるプロセスでは、それ以上のマネージコードを実行できず、スレッドは CLR への入力がブロックされます。</span><span class="sxs-lookup"><span data-stu-id="189af-111">No further managed code can be executed in the affected process, and threads are blocked from entering the CLR.</span></span>|  
|`eExitProcess`|<span data-ttu-id="189af-112">CLR がプロセスを正常に終了する必要があることを指定します。これには、ファイナライザーの実行やクリーンアップおよびログ操作の実行が含まれます。</span><span class="sxs-lookup"><span data-stu-id="189af-112">Specifies that the CLR should attempt a graceful exit of the process, including running finalizers and performing cleanup and logging operations.</span></span>|  
|`eFastExitProcess`|<span data-ttu-id="189af-113">CLR がファイナライザーを実行したりクリーンアップ操作やログ操作を実行したりせずに、プロセスをすぐに終了するように指定します。</span><span class="sxs-lookup"><span data-stu-id="189af-113">Specifies that the CLR should exit the process immediately, without running finalizers or performing cleanup and logging operations.</span></span> <span data-ttu-id="189af-114">ただし、通知はデバッガーに送信されます。</span><span class="sxs-lookup"><span data-stu-id="189af-114">However, notification is sent to the debugger.</span></span>|  
|`eNoAction`|<span data-ttu-id="189af-115">アクションを実行しないことを指定します。</span><span class="sxs-lookup"><span data-stu-id="189af-115">Specifies that no action should be taken.</span></span>|  
|`eRudeAbortThread`|<span data-ttu-id="189af-116">CLR がルースレッド中止を実行することを指定します。</span><span class="sxs-lookup"><span data-stu-id="189af-116">Specifies that the CLR should perform a rude thread abort.</span></span> <span data-ttu-id="189af-117"><xref:System.EnterpriseServices.MustRunInClientContextAttribute> でマークされた `catch` および `finally` ブロックだけが実行されます。</span><span class="sxs-lookup"><span data-stu-id="189af-117">Only those `catch` and `finally` blocks marked with <xref:System.EnterpriseServices.MustRunInClientContextAttribute> are executed.</span></span>|  
|`eRudeExitProcess`|<span data-ttu-id="189af-118">CLR がファイナライザーまたはログ操作を実行せずにプロセスを終了する必要があることを指定します。</span><span class="sxs-lookup"><span data-stu-id="189af-118">Specifies that the CLR should exit the process without running finalizers or logging operations.</span></span>|  
|`eRudeUnloadAppDomain`|<span data-ttu-id="189af-119">CLR が <xref:System.AppDomain>のルードアンロードを実行する必要があることを指定します。</span><span class="sxs-lookup"><span data-stu-id="189af-119">Specifies that the CLR should perform a rude unload of the <xref:System.AppDomain>.</span></span> <span data-ttu-id="189af-120"><xref:System.EnterpriseServices.MustRunInClientContextAttribute> でマークされたファイナライザーだけが実行されます。</span><span class="sxs-lookup"><span data-stu-id="189af-120">Only finalizers marked with <xref:System.EnterpriseServices.MustRunInClientContextAttribute> are executed.</span></span> <span data-ttu-id="189af-121">同様に、スタック内のこの <xref:System.AppDomain> を持つすべてのスレッドは `ThreadAbortException`を受け取りますが、<xref:System.EnterpriseServices.MustRunInClientContextAttribute> でマークされた `catch` および `finally` ブロックだけが実行されます。</span><span class="sxs-lookup"><span data-stu-id="189af-121">Similarly, all threads with this <xref:System.AppDomain> in their stack receive a `ThreadAbortException`, but only those `catch` and `finally` blocks marked with <xref:System.EnterpriseServices.MustRunInClientContextAttribute> are executed.</span></span>|  
|`eThrowException`|<span data-ttu-id="189af-122">メモリ不足、バッファーオーバーフローなどの条件に適した例外をスローする必要があることを指定します。</span><span class="sxs-lookup"><span data-stu-id="189af-122">Specifies that an exception appropriate to the condition, such as out-of-memory, buffer overflow, and so forth, should be thrown.</span></span>|  
|`eUnloadAppDomain`|<span data-ttu-id="189af-123"><xref:System.AppDomain> をアンロードする必要があることを指定します。</span><span class="sxs-lookup"><span data-stu-id="189af-123">Specifies that the <xref:System.AppDomain> should be unloaded.</span></span> <span data-ttu-id="189af-124">CLR はファイナライザーの実行を試みます。</span><span class="sxs-lookup"><span data-stu-id="189af-124">The CLR attempts to run finalizers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="189af-125">Remarks</span><span class="sxs-lookup"><span data-stu-id="189af-125">Remarks</span></span>  
 <span data-ttu-id="189af-126">ホストは、 [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)インターフェイスのメソッドを呼び出すことによって、ポリシーアクションを設定します。</span><span class="sxs-lookup"><span data-stu-id="189af-126">The host sets policy actions by calling methods of the [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md) interface.</span></span> <span data-ttu-id="189af-127">ルードと正常な中止の詳細については、 [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)列挙体を参照してください。</span><span class="sxs-lookup"><span data-stu-id="189af-127">For information about rude and graceful aborts, see the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="189af-128">［要件］</span><span class="sxs-lookup"><span data-stu-id="189af-128">Requirements</span></span>  
 <span data-ttu-id="189af-129">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="189af-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="189af-130">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="189af-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="189af-131">**ライブラリ:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="189af-131">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="189af-132">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="189af-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="189af-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="189af-133">See also</span></span>

- [<span data-ttu-id="189af-134">EClrFailure 列挙型</span><span class="sxs-lookup"><span data-stu-id="189af-134">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [<span data-ttu-id="189af-135">ICLRPolicyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="189af-135">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="189af-136">IHostPolicyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="189af-136">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
- [<span data-ttu-id="189af-137">ホスティングの列挙型</span><span class="sxs-lookup"><span data-stu-id="189af-137">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
