---
title: EClrFailure 列挙型
ms.date: 03/30/2017
api_name:
- EClrFailure
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EClrFailure
helpviewer_keywords:
- EClrFailure enumeration [.NET Framework hosting]
ms.assetid: 37b95cce-9bfb-4ecf-a00b-33dcba782c67
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cb19f950122f7b0db66830e9ed5dff44ccd370c2
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490437"
---
# <a name="eclrfailure-enumeration"></a><span data-ttu-id="b63a0-102">EClrFailure 列挙型</span><span class="sxs-lookup"><span data-stu-id="b63a0-102">EClrFailure Enumeration</span></span>
<span data-ttu-id="b63a0-103">ホストがポリシーのアクションを設定できるエラーのセットについて説明します。</span><span class="sxs-lookup"><span data-stu-id="b63a0-103">Describes the set of failures for which a host can set policy actions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b63a0-104">構文</span><span class="sxs-lookup"><span data-stu-id="b63a0-104">Syntax</span></span>  
  
```  
typedef enum {  
    FAIL_NonCriticalResource,  
    FAIL_CriticalResource,  
    FAIL_FatalRuntime,  
    FAIL_OrphanedLock  
    FAIL_StackOverflow  
    FAIL_AccessViolation  
    FAIL_CodeContract  
} EClrFailure;  
```  
  
## <a name="members"></a><span data-ttu-id="b63a0-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="b63a0-105">Members</span></span>  
  
|<span data-ttu-id="b63a0-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="b63a0-106">Member</span></span>|<span data-ttu-id="b63a0-107">説明</span><span class="sxs-lookup"><span data-stu-id="b63a0-107">Description</span></span>|  
|------------|-----------------|  
|`FAIL_NonCriticalResource`|<span data-ttu-id="b63a0-108">重大でないコードの領域で、(スレッド、メモリのブロックまたはロック) などのリソースの割り当ての試行中にエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="b63a0-108">A failure occurred during an attempt to allocate a resource (such as a thread, a block of memory, or a lock) in a non-critical region of code.</span></span>|  
|`FAIL_CriticalResource`|<span data-ttu-id="b63a0-109">コードのクリティカル領域で、(スレッド、メモリのブロックまたはロック) などのリソースの割り当ての試行中にエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="b63a0-109">A failure occurred during an attempt to allocate a resource (such as a thread, a block of memory, or a lock) in a critical region of code.</span></span>|  
|`FAIL_FatalRuntime`|<span data-ttu-id="b63a0-110">共通言語ランタイム (CLR) は、プロセスでマネージ コードを実行することはありません。</span><span class="sxs-lookup"><span data-stu-id="b63a0-110">The common language runtime (CLR) is no longer able to run managed code in the process.</span></span> <span data-ttu-id="b63a0-111">今後は、ホスティング関数を呼び出すには、HOST_E_CLRNOTAVAILABLE の HRESULT 値が返されます。</span><span class="sxs-lookup"><span data-stu-id="b63a0-111">Henceforth, calls to any hosting functions return an HRESULT value of HOST_E_CLRNOTAVAILABLE.</span></span>|  
|`FAIL_OrphanedLock`|<span data-ttu-id="b63a0-112">スレッドがから戻ったときにロックを解放できませんでしたが、<xref:System.AppDomain>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="b63a0-112">A thread has failed to release a lock upon returning from an <xref:System.AppDomain> object.</span></span> <span data-ttu-id="b63a0-113">ホストは、スレッドを中止するには、このエラーを設定できません。</span><span class="sxs-lookup"><span data-stu-id="b63a0-113">The host cannot set this failure to cause a thread to abort.</span></span>|  
|`FAIL_StackOverflow`|<span data-ttu-id="b63a0-114">スタック オーバーフローが発生しました。</span><span class="sxs-lookup"><span data-stu-id="b63a0-114">A stack overflow has occurred.</span></span>|  
|`FAIL_AccessViolation`|<span data-ttu-id="b63a0-115">読み取りまたは書き込み保護されているメモリを試行されました。</span><span class="sxs-lookup"><span data-stu-id="b63a0-115">An attempt was made to read or write protected memory.</span></span> <span data-ttu-id="b63a0-116">.NET Framework 4 ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="b63a0-116">Not supported in the .NET Framework 4.</span></span>|  
|`FAIL_CodeContract`|<span data-ttu-id="b63a0-117">コード コントラクトのエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="b63a0-117">A code contract failure occurred.</span></span> <span data-ttu-id="b63a0-118">参照してください[コード コントラクト](../../../../docs/framework/debug-trace-profile/code-contracts.md)します。</span><span class="sxs-lookup"><span data-stu-id="b63a0-118">See [Code Contracts](../../../../docs/framework/debug-trace-profile/code-contracts.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b63a0-119">Remarks</span><span class="sxs-lookup"><span data-stu-id="b63a0-119">Remarks</span></span>  
 <span data-ttu-id="b63a0-120">参照してください、 [iclrpolicymanager::setactiononfailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md)メソッドの一覧については[EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)値が、ホストを使用してエラー状態のポリシーのアクションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="b63a0-120">See the [ICLRPolicyManager::SetActionOnFailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) method for a list of [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values the host can use to specify the policy actions for failure conditions.</span></span> <span data-ttu-id="b63a0-121">コードの重要および重大でないリージョンの詳細については、次を参照してください。 [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)します。</span><span class="sxs-lookup"><span data-stu-id="b63a0-121">For more information about critical and non-critical regions of code, see [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b63a0-122">必要条件</span><span class="sxs-lookup"><span data-stu-id="b63a0-122">Requirements</span></span>  
 <span data-ttu-id="b63a0-123">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b63a0-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b63a0-124">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b63a0-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b63a0-125">**ライブラリ:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b63a0-125">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b63a0-126">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b63a0-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b63a0-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="b63a0-127">See also</span></span>

- [<span data-ttu-id="b63a0-128">ICLRPolicyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b63a0-128">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="b63a0-129">SetActionOnFailure メソッド</span><span class="sxs-lookup"><span data-stu-id="b63a0-129">SetActionOnFailure Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md)
- [<span data-ttu-id="b63a0-130">IHostPolicyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b63a0-130">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
- [<span data-ttu-id="b63a0-131">ホスティングの列挙型</span><span class="sxs-lookup"><span data-stu-id="b63a0-131">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
