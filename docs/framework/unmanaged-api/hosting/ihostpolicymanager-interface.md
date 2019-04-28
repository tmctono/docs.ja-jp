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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cf9d903b4e44ea7a185ad8b3b71b7a5da2f2bda3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61760117"
---
# <a name="ihostpolicymanager-interface"></a><span data-ttu-id="23f88-102">IHostPolicyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="23f88-102">IHostPolicyManager Interface</span></span>
<span data-ttu-id="23f88-103">ホストの場合、共通言語ランタイム (CLR) を実行するアクションの中止、タイムアウト、またはエラーを通知するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="23f88-103">Provides methods that notify the host of the actions the common language runtime (CLR) performs in case of aborts, timeouts, or failures.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="23f88-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="23f88-104">Methods</span></span>  
  
|<span data-ttu-id="23f88-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="23f88-105">Method</span></span>|<span data-ttu-id="23f88-106">説明</span><span class="sxs-lookup"><span data-stu-id="23f88-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="23f88-107">OnDefaultAction メソッド</span><span class="sxs-lookup"><span data-stu-id="23f88-107">OnDefaultAction Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-ondefaultaction-method.md)|<span data-ttu-id="23f88-108">CLR はへの呼び出しで指定された既定のアクションを実行するホストに通知します[iclrpolicymanager::setdefaultaction](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md)スレッドへの応答で中止または<xref:System.AppDomain>をアンロードします。</span><span class="sxs-lookup"><span data-stu-id="23f88-108">Notifies the host that the CLR is about to take the default action specified by a call to [ICLRPolicyManager::SetDefaultAction](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md) in response to a thread abort or <xref:System.AppDomain> unload.</span></span>|  
|[<span data-ttu-id="23f88-109">OnFailure メソッド</span><span class="sxs-lookup"><span data-stu-id="23f88-109">OnFailure Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-onfailure-method.md)|<span data-ttu-id="23f88-110">CLR はへの呼び出しで指定されたアクションを実行するホストに通知します[iclrpolicymanager::setactiononfailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md)リソース割り当てまたは解放の失敗に応答します。</span><span class="sxs-lookup"><span data-stu-id="23f88-110">Notifies the host that the CLR is about to take the action specified by a call to [ICLRPolicyManager::SetActionOnFailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) in response to a resource allocation or reclamation failure.</span></span>|  
|[<span data-ttu-id="23f88-111">OnTimeout メソッド</span><span class="sxs-lookup"><span data-stu-id="23f88-111">OnTimeout Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-ontimeout-method.md)|<span data-ttu-id="23f88-112">CLR はへの呼び出しで指定されたアクションを実行するホストに通知します[iclrpolicymanager::setactionontimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md)タイムアウトへの応答。</span><span class="sxs-lookup"><span data-stu-id="23f88-112">Notifies the host that the CLR is about to take the action specified by a call to [ICLRPolicyManager::SetActionOnTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) in response to a timeout.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="23f88-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="23f88-113">Requirements</span></span>  
 <span data-ttu-id="23f88-114">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="23f88-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23f88-115">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="23f88-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="23f88-116">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="23f88-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="23f88-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="23f88-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23f88-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="23f88-118">See also</span></span>

- [<span data-ttu-id="23f88-119">EClrFailure 列挙型</span><span class="sxs-lookup"><span data-stu-id="23f88-119">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [<span data-ttu-id="23f88-120">EClrOperation 列挙型</span><span class="sxs-lookup"><span data-stu-id="23f88-120">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="23f88-121">EPolicyAction 列挙型</span><span class="sxs-lookup"><span data-stu-id="23f88-121">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="23f88-122">ICLRPolicyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="23f88-122">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="23f88-123">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="23f88-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
