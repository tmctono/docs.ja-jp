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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 75bd7da67cbac958f0b34c8295454a719962c7ed
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59201729"
---
# <a name="epolicyaction-enumeration"></a><span data-ttu-id="7c622-102">EPolicyAction 列挙型</span><span class="sxs-lookup"><span data-stu-id="7c622-102">EPolicyAction Enumeration</span></span>
<span data-ttu-id="7c622-103">ホストを設定できますで説明されている操作のポリシーのアクションについて説明します[EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)しで説明されているエラー [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)します。</span><span class="sxs-lookup"><span data-stu-id="7c622-103">Describes the policy actions the host can set for operations described by [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) and failures described by [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c622-104">構文</span><span class="sxs-lookup"><span data-stu-id="7c622-104">Syntax</span></span>  
  
```  
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
  
## <a name="members"></a><span data-ttu-id="7c622-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="7c622-105">Members</span></span>  
  
|<span data-ttu-id="7c622-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="7c622-106">Member</span></span>|<span data-ttu-id="7c622-107">説明</span><span class="sxs-lookup"><span data-stu-id="7c622-107">Description</span></span>|  
|------------|-----------------|  
|`eAbortThread`|<span data-ttu-id="7c622-108">共通言語ランタイム (CLR) の中止でスレッドが適切に処理する必要がありますを指定します。</span><span class="sxs-lookup"><span data-stu-id="7c622-108">Specifies that the common language runtime (CLR) should abort the thread gracefully.</span></span> <span data-ttu-id="7c622-109">適切な中止には、すべてを実行する試行が含まれています。`finally`いずれかのブロック`catch`スレッドの中止、およびファイナライザーに関連するブロック。</span><span class="sxs-lookup"><span data-stu-id="7c622-109">A graceful abort includes attempts to run all `finally` blocks, any `catch` blocks related to thread aborts, and finalizers.</span></span>|  
|`eDisableRuntime`|<span data-ttu-id="7c622-110">CLR が無効の状態を入力する必要がありますを指定します。</span><span class="sxs-lookup"><span data-stu-id="7c622-110">Specifies that the CLR should enter a disabled state.</span></span> <span data-ttu-id="7c622-111">マネージ コードを実行して、影響を受けるプロセスでそれ以上と、CLR に入るをスレッドがブロックされます。</span><span class="sxs-lookup"><span data-stu-id="7c622-111">No further managed code can be executed in the affected process, and threads are blocked from entering the CLR.</span></span>|  
|`eExitProcess`|<span data-ttu-id="7c622-112">CLR がファイナライザーを実行して、クリーンアップとログ記録操作を実行するなど、プロセスの正常な終了を試みる必要があることを指定します。</span><span class="sxs-lookup"><span data-stu-id="7c622-112">Specifies that the CLR should attempt a graceful exit of the process, including running finalizers and performing cleanup and logging operations.</span></span>|  
|`eFastExitProcess`|<span data-ttu-id="7c622-113">CLR しないで終了すること、プロセス、すぐにファイナライザーを実行するか、クリーンアップとログ記録操作を実行するを指定します。</span><span class="sxs-lookup"><span data-stu-id="7c622-113">Specifies that the CLR should exit the process immediately, without running finalizers or performing cleanup and logging operations.</span></span> <span data-ttu-id="7c622-114">ただし、デバッガーに通知が送信されます。</span><span class="sxs-lookup"><span data-stu-id="7c622-114">However, notification is sent to the debugger.</span></span>|  
|`eNoAction`|<span data-ttu-id="7c622-115">アクションを実行しないことを指定します。</span><span class="sxs-lookup"><span data-stu-id="7c622-115">Specifies that no action should be taken.</span></span>|  
|`eRudeAbortThread`|<span data-ttu-id="7c622-116">CLR がルード スレッドの中止を実行する必要がありますを指定します。</span><span class="sxs-lookup"><span data-stu-id="7c622-116">Specifies that the CLR should perform a rude thread abort.</span></span> <span data-ttu-id="7c622-117">だけ`catch`と`finally`でマークされたブロック<xref:System.EnterpriseServices.MustRunInClientContextAttribute>実行されます。</span><span class="sxs-lookup"><span data-stu-id="7c622-117">Only those `catch` and `finally` blocks marked with <xref:System.EnterpriseServices.MustRunInClientContextAttribute> are executed.</span></span>|  
|`eRudeExitProcess`|<span data-ttu-id="7c622-118">CLR がファイナライザーを実行するか、操作のログ記録しないでプロセスを終了することを指定します。</span><span class="sxs-lookup"><span data-stu-id="7c622-118">Specifies that the CLR should exit the process without running finalizers or logging operations.</span></span>|  
|`eRudeUnloadAppDomain`|<span data-ttu-id="7c622-119">CLR がのルード アンロードを実行する必要がありますを指定します、<xref:System.AppDomain>します。</span><span class="sxs-lookup"><span data-stu-id="7c622-119">Specifies that the CLR should perform a rude unload of the <xref:System.AppDomain>.</span></span> <span data-ttu-id="7c622-120">マークされた唯一のファイナライザー<xref:System.EnterpriseServices.MustRunInClientContextAttribute>実行されます。</span><span class="sxs-lookup"><span data-stu-id="7c622-120">Only finalizers marked with <xref:System.EnterpriseServices.MustRunInClientContextAttribute> are executed.</span></span> <span data-ttu-id="7c622-121">これと同様に、すべてのスレッド<xref:System.AppDomain>スタックには、受信、 `ThreadAbortException`、だけが`catch`と`finally`でマークされたブロック<xref:System.EnterpriseServices.MustRunInClientContextAttribute>実行されます。</span><span class="sxs-lookup"><span data-stu-id="7c622-121">Similarly, all threads with this <xref:System.AppDomain> in their stack receive a `ThreadAbortException`, but only those `catch` and `finally` blocks marked with <xref:System.EnterpriseServices.MustRunInClientContextAttribute> are executed.</span></span>|  
|`eThrowException`|<span data-ttu-id="7c622-122">メモリ不足、バッファーのオーバーフローなどの条件に該当する例外をスローすることを指定します。</span><span class="sxs-lookup"><span data-stu-id="7c622-122">Specifies that an exception appropriate to the condition, such as out-of-memory, buffer overflow, and so forth, should be thrown.</span></span>|  
|`eUnloadAppDomain`|<span data-ttu-id="7c622-123">指定します、<xref:System.AppDomain>がアンロードされます。</span><span class="sxs-lookup"><span data-stu-id="7c622-123">Specifies that the <xref:System.AppDomain> should be unloaded.</span></span> <span data-ttu-id="7c622-124">CLR は、ファイナライザーを実行しようとします。</span><span class="sxs-lookup"><span data-stu-id="7c622-124">The CLR attempts to run finalizers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7c622-125">Remarks</span><span class="sxs-lookup"><span data-stu-id="7c622-125">Remarks</span></span>  
 <span data-ttu-id="7c622-126">ホストのメソッドを呼び出すことによってポリシーのアクションを設定する、 [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="7c622-126">The host sets policy actions by calling methods of the [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md) interface.</span></span> <span data-ttu-id="7c622-127">ルードと正常な中止の詳細については、次を参照してください。、 [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)列挙体。</span><span class="sxs-lookup"><span data-stu-id="7c622-127">For information about rude and graceful aborts, see the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c622-128">必要条件</span><span class="sxs-lookup"><span data-stu-id="7c622-128">Requirements</span></span>  
 <span data-ttu-id="7c622-129">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7c622-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c622-130">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7c622-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7c622-131">**ライブラリ:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7c622-131">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7c622-132">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c622-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c622-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="7c622-133">See also</span></span>

- [<span data-ttu-id="7c622-134">EClrFailure 列挙型</span><span class="sxs-lookup"><span data-stu-id="7c622-134">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [<span data-ttu-id="7c622-135">ICLRPolicyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7c622-135">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="7c622-136">IHostPolicyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7c622-136">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
- [<span data-ttu-id="7c622-137">ホスティングの列挙型</span><span class="sxs-lookup"><span data-stu-id="7c622-137">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
