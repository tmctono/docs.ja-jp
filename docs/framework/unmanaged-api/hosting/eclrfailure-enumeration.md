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
ms.openlocfilehash: 7d935bff023d806cf8cfb6d87bde0f82666b51b5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131126"
---
# <a name="eclrfailure-enumeration"></a><span data-ttu-id="849cf-102">EClrFailure 列挙型</span><span class="sxs-lookup"><span data-stu-id="849cf-102">EClrFailure Enumeration</span></span>
<span data-ttu-id="849cf-103">ホストがポリシーアクションを設定できるエラーのセットについて説明します。</span><span class="sxs-lookup"><span data-stu-id="849cf-103">Describes the set of failures for which a host can set policy actions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="849cf-104">構文</span><span class="sxs-lookup"><span data-stu-id="849cf-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="849cf-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="849cf-105">Members</span></span>  
  
|<span data-ttu-id="849cf-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="849cf-106">Member</span></span>|<span data-ttu-id="849cf-107">説明</span><span class="sxs-lookup"><span data-stu-id="849cf-107">Description</span></span>|  
|------------|-----------------|  
|`FAIL_NonCriticalResource`|<span data-ttu-id="849cf-108">クリティカルでないコード領域に、リソース (スレッド、メモリブロック、ロックなど) を割り当てようとしたときにエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="849cf-108">A failure occurred during an attempt to allocate a resource (such as a thread, a block of memory, or a lock) in a non-critical region of code.</span></span>|  
|`FAIL_CriticalResource`|<span data-ttu-id="849cf-109">コードの重要な領域に、リソース (スレッド、メモリブロック、ロックなど) を割り当てようとしたときにエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="849cf-109">A failure occurred during an attempt to allocate a resource (such as a thread, a block of memory, or a lock) in a critical region of code.</span></span>|  
|`FAIL_FatalRuntime`|<span data-ttu-id="849cf-110">共通言語ランタイム (CLR) は、プロセスでマネージコードを実行できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="849cf-110">The common language runtime (CLR) is no longer able to run managed code in the process.</span></span> <span data-ttu-id="849cf-111">その後、任意のホスト関数の呼び出しは、HOST_E_CLRNOTAVAILABLE の HRESULT 値を返します。</span><span class="sxs-lookup"><span data-stu-id="849cf-111">Henceforth, calls to any hosting functions return an HRESULT value of HOST_E_CLRNOTAVAILABLE.</span></span>|  
|`FAIL_OrphanedLock`|<span data-ttu-id="849cf-112">スレッドは、<xref:System.AppDomain> オブジェクトから戻るときにロックを解放できませんでした。</span><span class="sxs-lookup"><span data-stu-id="849cf-112">A thread has failed to release a lock upon returning from an <xref:System.AppDomain> object.</span></span> <span data-ttu-id="849cf-113">ホストは、このエラーを設定してスレッドを中止することはできません。</span><span class="sxs-lookup"><span data-stu-id="849cf-113">The host cannot set this failure to cause a thread to abort.</span></span>|  
|`FAIL_StackOverflow`|<span data-ttu-id="849cf-114">スタックオーバーフローが発生しました。</span><span class="sxs-lookup"><span data-stu-id="849cf-114">A stack overflow has occurred.</span></span>|  
|`FAIL_AccessViolation`|<span data-ttu-id="849cf-115">保護されたメモリの読み取りまたは書き込みが試行されました。</span><span class="sxs-lookup"><span data-stu-id="849cf-115">An attempt was made to read or write protected memory.</span></span> <span data-ttu-id="849cf-116">.NET Framework 4 ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="849cf-116">Not supported in the .NET Framework 4.</span></span>|  
|`FAIL_CodeContract`|<span data-ttu-id="849cf-117">コードコントラクトエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="849cf-117">A code contract failure occurred.</span></span> <span data-ttu-id="849cf-118">「[コードコントラクト](../../../../docs/framework/debug-trace-profile/code-contracts.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="849cf-118">See [Code Contracts](../../../../docs/framework/debug-trace-profile/code-contracts.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="849cf-119">Remarks</span><span class="sxs-lookup"><span data-stu-id="849cf-119">Remarks</span></span>  
 <span data-ttu-id="849cf-120">エラー条件のポリシーアクションを指定するためにホストで使用できる[Epolicyaction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)値の一覧については、 [ICLRPolicyManager:: SetActionOnFailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md)メソッドを参照してください。</span><span class="sxs-lookup"><span data-stu-id="849cf-120">See the [ICLRPolicyManager::SetActionOnFailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) method for a list of [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values the host can use to specify the policy actions for failure conditions.</span></span> <span data-ttu-id="849cf-121">クリティカルな、またはクリティカルでないコード領域の詳細については、「 [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="849cf-121">For more information about critical and non-critical regions of code, see [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="849cf-122">［要件］</span><span class="sxs-lookup"><span data-stu-id="849cf-122">Requirements</span></span>  
 <span data-ttu-id="849cf-123">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="849cf-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="849cf-124">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="849cf-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="849cf-125">**ライブラリ:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="849cf-125">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="849cf-126">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="849cf-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="849cf-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="849cf-127">See also</span></span>

- [<span data-ttu-id="849cf-128">ICLRPolicyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="849cf-128">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="849cf-129">SetActionOnFailure メソッド</span><span class="sxs-lookup"><span data-stu-id="849cf-129">SetActionOnFailure Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md)
- [<span data-ttu-id="849cf-130">IHostPolicyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="849cf-130">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
- [<span data-ttu-id="849cf-131">ホスティングの列挙型</span><span class="sxs-lookup"><span data-stu-id="849cf-131">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
