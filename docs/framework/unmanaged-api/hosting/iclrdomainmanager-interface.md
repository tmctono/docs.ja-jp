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
ms.openlocfilehash: aa874205cf14232e7a69ed2215086e33c0beab4d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129338"
---
# <a name="iclrdomainmanager-interface"></a><span data-ttu-id="e61c0-102">ICLRDomainManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e61c0-102">ICLRDomainManager Interface</span></span>
<span data-ttu-id="e61c0-103">既定のアプリケーションドメインを初期化し、初期化プロパティを指定するために使用されるアプリケーションドメインマネージャーをホストが指定できるようにします。</span><span class="sxs-lookup"><span data-stu-id="e61c0-103">Enables the host to specify the application domain manager that will be used to initialize the default application domain, and to specify initialization properties.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e61c0-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="e61c0-104">Methods</span></span>  
  
|<span data-ttu-id="e61c0-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="e61c0-105">Method</span></span>|<span data-ttu-id="e61c0-106">説明</span><span class="sxs-lookup"><span data-stu-id="e61c0-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e61c0-107">SetAppDomainManagerType メソッド</span><span class="sxs-lookup"><span data-stu-id="e61c0-107">SetAppDomainManagerType Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md)|<span data-ttu-id="e61c0-108">既定のアプリケーションドメインを初期化するために使用されるアプリケーションドメインマネージャーの <xref:System.AppDomainManager?displayProperty=nameWithType> クラスから派生した型を指定します。</span><span class="sxs-lookup"><span data-stu-id="e61c0-108">Specifies the type, derived from the <xref:System.AppDomainManager?displayProperty=nameWithType> class, of the application domain manager that will be used to initialize the default application domain.</span></span>|  
|[<span data-ttu-id="e61c0-109">SetPropertiesForDefaultAppDomain メソッド</span><span class="sxs-lookup"><span data-stu-id="e61c0-109">SetPropertiesForDefaultAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setpropertiesfordefaultappdomain-method.md)|<span data-ttu-id="e61c0-110">既定のアプリケーションドメインを初期化するために使用されるプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="e61c0-110">Sets properties that will be used to initialize the default application domain.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e61c0-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="e61c0-111">Remarks</span></span>  
 <span data-ttu-id="e61c0-112">このインターフェイスのインスタンスを取得するには、 [ICLRControl:: GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md)メソッドを呼び出して、manager 型の IID `IID_ICLRDomainManager`を使用します。</span><span class="sxs-lookup"><span data-stu-id="e61c0-112">To get an instance of this interface, call the [ICLRControl::GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) method with the manager type IID `IID_ICLRDomainManager`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e61c0-113">［要件］</span><span class="sxs-lookup"><span data-stu-id="e61c0-113">Requirements</span></span>  
 <span data-ttu-id="e61c0-114">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e61c0-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e61c0-115">**ヘッダー:** メタホスト .h</span><span class="sxs-lookup"><span data-stu-id="e61c0-115">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="e61c0-116">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="e61c0-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e61c0-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e61c0-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e61c0-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="e61c0-118">See also</span></span>

- [<span data-ttu-id="e61c0-119">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e61c0-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="e61c0-120">ホスティング</span><span class="sxs-lookup"><span data-stu-id="e61c0-120">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
