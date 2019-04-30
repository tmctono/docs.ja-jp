---
title: ICLRControl インターフェイス
ms.date: 03/30/2017
api_name:
- ICLRControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRControl
helpviewer_keywords:
- ICLRControl interface [.NET Framework hosting]
ms.assetid: a24fd905-1fa6-45a0-ad65-e9e2ee58861e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f70e7958cc9ac198738ed72732fe7b6563c89067
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61970067"
---
# <a name="iclrcontrol-interface"></a><span data-ttu-id="09def-102">ICLRControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="09def-102">ICLRControl Interface</span></span>
<span data-ttu-id="09def-103">ホストへの参照を取得できるように、共通言語ランタイム (CLR) の要素を構成するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="09def-103">Provides methods that allow a host to get references to, and configure aspects of, the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="09def-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="09def-104">Methods</span></span>  
  
|<span data-ttu-id="09def-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="09def-105">Method</span></span>|<span data-ttu-id="09def-106">説明</span><span class="sxs-lookup"><span data-stu-id="09def-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="09def-107">GetCLRManager メソッド</span><span class="sxs-lookup"><span data-stu-id="09def-107">GetCLRManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md)|<span data-ttu-id="09def-108">ホストは、CLR の構成に使用できる、マネージャーの種類のいずれかのインスタンスへのインターフェイス ポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="09def-108">Gets an interface pointer to an instance of any of the manager types the host can use to configure the CLR.</span></span>|  
|[<span data-ttu-id="09def-109">SetAppDomainManagerType メソッド</span><span class="sxs-lookup"><span data-stu-id="09def-109">SetAppDomainManagerType Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)|<span data-ttu-id="09def-110">派生した型を設定<xref:System.AppDomainManager>アプリケーション ドメイン マネージャーの型として。</span><span class="sxs-lookup"><span data-stu-id="09def-110">Sets a type derived from <xref:System.AppDomainManager> as the type for application domain managers.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="09def-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="09def-111">Requirements</span></span>  
 <span data-ttu-id="09def-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="09def-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09def-113">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="09def-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="09def-114">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="09def-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="09def-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09def-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09def-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="09def-116">See also</span></span>

- [<span data-ttu-id="09def-117">ICLRAssemblyIdentityManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="09def-117">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="09def-118">ICLRDebugManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="09def-118">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)
- [<span data-ttu-id="09def-119">ICLRGCManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="09def-119">ICLRGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)
- [<span data-ttu-id="09def-120">ICLRHostBindingPolicyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="09def-120">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
- [<span data-ttu-id="09def-121">ICLRHostProtectionManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="09def-121">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)
- [<span data-ttu-id="09def-122">ICLROnEventManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="09def-122">ICLROnEventManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)
- [<span data-ttu-id="09def-123">ICLRPolicyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="09def-123">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="09def-124">IHostControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="09def-124">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
- [<span data-ttu-id="09def-125">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="09def-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
