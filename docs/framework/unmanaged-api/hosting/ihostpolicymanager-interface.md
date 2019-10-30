---
title: IHostPolicyManager インターフェイス
ms.date: 03/30/2017
api_name:
- IHostPolicyManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostPolicyManager
helpviewer_keywords:
- IHostPolicyManager interface [.NET Framework hosting]
ms.assetid: 8c4aa124-5e00-46d9-b1e8-57ba6574bb0d
topic_type:
- apiref
ms.openlocfilehash: 6ba7b7adc104db528293d77c3591370c6ce02c25
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128597"
---
# <a name="ihostpolicymanager-interface"></a><span data-ttu-id="3a402-102">IHostPolicyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3a402-102">IHostPolicyManager Interface</span></span>
<span data-ttu-id="3a402-103">中止、タイムアウト、またはエラーが発生した場合に共通言語ランタイム (CLR) が実行するアクションをホストに通知するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="3a402-103">Provides methods that notify the host of the actions the common language runtime (CLR) performs in case of aborts, timeouts, or failures.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3a402-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="3a402-104">Methods</span></span>  
  
|<span data-ttu-id="3a402-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="3a402-105">Method</span></span>|<span data-ttu-id="3a402-106">説明</span><span class="sxs-lookup"><span data-stu-id="3a402-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3a402-107">OnDefaultAction メソッド</span><span class="sxs-lookup"><span data-stu-id="3a402-107">OnDefaultAction Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-ondefaultaction-method.md)|<span data-ttu-id="3a402-108">CLR が、スレッドの中止または <xref:System.AppDomain> のアンロードに応答して、 [ICLRPolicyManager:: SetDefaultAction](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md)の呼び出しによって指定された既定のアクションを実行しようとしていることをホストに通知します。</span><span class="sxs-lookup"><span data-stu-id="3a402-108">Notifies the host that the CLR is about to take the default action specified by a call to [ICLRPolicyManager::SetDefaultAction](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md) in response to a thread abort or <xref:System.AppDomain> unload.</span></span>|  
|[<span data-ttu-id="3a402-109">OnFailure メソッド</span><span class="sxs-lookup"><span data-stu-id="3a402-109">OnFailure Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-onfailure-method.md)|<span data-ttu-id="3a402-110">リソース割り当てまたは再利用エラーに応答して、CLR が[ICLRPolicyManager:: SetActionOnFailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md)の呼び出しによって指定されたアクションを実行しようとしていることをホストに通知します。</span><span class="sxs-lookup"><span data-stu-id="3a402-110">Notifies the host that the CLR is about to take the action specified by a call to [ICLRPolicyManager::SetActionOnFailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) in response to a resource allocation or reclamation failure.</span></span>|  
|[<span data-ttu-id="3a402-111">OnTimeout メソッド</span><span class="sxs-lookup"><span data-stu-id="3a402-111">OnTimeout Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-ontimeout-method.md)|<span data-ttu-id="3a402-112">タイムアウトに応答して[ICLRPolicyManager:: SetActionOnTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md)への呼び出しによって指定されたアクションを CLR が実行しようとしていることをホストに通知します。</span><span class="sxs-lookup"><span data-stu-id="3a402-112">Notifies the host that the CLR is about to take the action specified by a call to [ICLRPolicyManager::SetActionOnTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) in response to a timeout.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3a402-113">［要件］</span><span class="sxs-lookup"><span data-stu-id="3a402-113">Requirements</span></span>  
 <span data-ttu-id="3a402-114">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a402-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a402-115">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="3a402-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3a402-116">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="3a402-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3a402-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3a402-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a402-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="3a402-118">See also</span></span>

- [<span data-ttu-id="3a402-119">EClrFailure 列挙型</span><span class="sxs-lookup"><span data-stu-id="3a402-119">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [<span data-ttu-id="3a402-120">EClrOperation 列挙型</span><span class="sxs-lookup"><span data-stu-id="3a402-120">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="3a402-121">EPolicyAction 列挙型</span><span class="sxs-lookup"><span data-stu-id="3a402-121">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="3a402-122">ICLRPolicyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3a402-122">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="3a402-123">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3a402-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
