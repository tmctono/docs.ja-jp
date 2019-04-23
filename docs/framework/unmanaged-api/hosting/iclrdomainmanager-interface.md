---
title: ICLRDomainManager インターフェイス
ms.date: 03/30/2017
api_name:
- ICLRDomainManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDomainManager
helpviewer_keywords:
- ICLRDomainManager interface [.NET Framework hosting]
ms.assetid: f08b2390-d872-4521-a815-e9c237c4c45d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ce53149b92ca40ad50ecbefaf4701940e8567ae5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59103925"
---
# <a name="iclrdomainmanager-interface"></a><span data-ttu-id="a557c-102">ICLRDomainManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a557c-102">ICLRDomainManager Interface</span></span>
<span data-ttu-id="a557c-103">初期化プロパティを指定して、既定のアプリケーション ドメインを初期化するために使用されるアプリケーション ドメイン マネージャーを指定するホストを有効にします。</span><span class="sxs-lookup"><span data-stu-id="a557c-103">Enables the host to specify the application domain manager that will be used to initialize the default application domain, and to specify initialization properties.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a557c-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="a557c-104">Methods</span></span>  
  
|<span data-ttu-id="a557c-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="a557c-105">Method</span></span>|<span data-ttu-id="a557c-106">説明</span><span class="sxs-lookup"><span data-stu-id="a557c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a557c-107">SetAppDomainManagerType メソッド</span><span class="sxs-lookup"><span data-stu-id="a557c-107">SetAppDomainManagerType Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md)|<span data-ttu-id="a557c-108">派生した、型を指定します、<xref:System.AppDomainManager?displayProperty=nameWithType>の既定のアプリケーション ドメインを初期化するために使用されるアプリケーション ドメイン マネージャーのクラス。</span><span class="sxs-lookup"><span data-stu-id="a557c-108">Specifies the type, derived from the <xref:System.AppDomainManager?displayProperty=nameWithType> class, of the application domain manager that will be used to initialize the default application domain.</span></span>|  
|[<span data-ttu-id="a557c-109">SetPropertiesForDefaultAppDomain メソッド</span><span class="sxs-lookup"><span data-stu-id="a557c-109">SetPropertiesForDefaultAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setpropertiesfordefaultappdomain-method.md)|<span data-ttu-id="a557c-110">既定のアプリケーション ドメインを初期化するために使用されるプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="a557c-110">Sets properties that will be used to initialize the default application domain.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a557c-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="a557c-111">Remarks</span></span>  
 <span data-ttu-id="a557c-112">このインターフェイスのインスタンスを取得する、 [iclrcontrol::getclrmanager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) IID マネージャーの種類を持つメソッド`IID_ICLRDomainManager`します。</span><span class="sxs-lookup"><span data-stu-id="a557c-112">To get an instance of this interface, call the [ICLRControl::GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) method with the manager type IID `IID_ICLRDomainManager`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a557c-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="a557c-113">Requirements</span></span>  
 <span data-ttu-id="a557c-114">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a557c-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a557c-115">**ヘッダー:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="a557c-115">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="a557c-116">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="a557c-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a557c-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a557c-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a557c-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="a557c-118">See also</span></span>

- [<span data-ttu-id="a557c-119">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a557c-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="a557c-120">ホスティング</span><span class="sxs-lookup"><span data-stu-id="a557c-120">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
