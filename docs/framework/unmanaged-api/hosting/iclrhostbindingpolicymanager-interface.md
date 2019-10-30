---
title: ICLRHostBindingPolicyManager インターフェイス
ms.date: 03/30/2017
api_name:
- ICLRHostBindingPolicyManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostBindingPolicyManager
helpviewer_keywords:
- ICLRHostBindingPolicyManager interface [.NET Framework hosting]
ms.assetid: f9da168b-366b-4b2b-bdb9-330b6bad5a6b
topic_type:
- apiref
ms.openlocfilehash: 9ed317a451e6e35aeac3bc1b83f78d1400ea5c07
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136437"
---
# <a name="iclrhostbindingpolicymanager-interface"></a><span data-ttu-id="08096-102">ICLRHostBindingPolicyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="08096-102">ICLRHostBindingPolicyManager Interface</span></span>
<span data-ttu-id="08096-103">ホストが現在のバインドポリシーを評価し、指定されたアセンブリのポリシー変更を伝達するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="08096-103">Provides methods for the host to evaluate current binding policy and communicate policy changes for a specified assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="08096-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="08096-104">Methods</span></span>  
  
|<span data-ttu-id="08096-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="08096-105">Method</span></span>|<span data-ttu-id="08096-106">説明</span><span class="sxs-lookup"><span data-stu-id="08096-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="08096-107">EvaluatePolicy メソッド</span><span class="sxs-lookup"><span data-stu-id="08096-107">EvaluatePolicy Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-evaluatepolicy-method.md)|<span data-ttu-id="08096-108">ホストの代わりにバインドポリシーを評価します。</span><span class="sxs-lookup"><span data-stu-id="08096-108">Evaluates binding policy on behalf of the host.</span></span>|  
|[<span data-ttu-id="08096-109">ModifyApplicationPolicy メソッド</span><span class="sxs-lookup"><span data-stu-id="08096-109">ModifyApplicationPolicy Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md)|<span data-ttu-id="08096-110">指定したアセンブリのバインディングポリシーを変更し、新しいバージョンのポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="08096-110">Modifies the binding policy for the specified assembly, and creates a new version of the policy.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="08096-111">［要件］</span><span class="sxs-lookup"><span data-stu-id="08096-111">Requirements</span></span>  
 <span data-ttu-id="08096-112">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="08096-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08096-113">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="08096-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="08096-114">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="08096-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="08096-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08096-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08096-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="08096-116">See also</span></span>

- [<span data-ttu-id="08096-117">ICLRAssemblyIdentityManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="08096-117">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="08096-118">IHostAssemblyStore インターフェイス</span><span class="sxs-lookup"><span data-stu-id="08096-118">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
- [<span data-ttu-id="08096-119">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="08096-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
