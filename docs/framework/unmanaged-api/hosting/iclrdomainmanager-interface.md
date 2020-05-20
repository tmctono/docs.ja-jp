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
ms.openlocfilehash: dda243ccbf18f396c1bcc03358997ea0f06c42a8
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615710"
---
# <a name="iclrdomainmanager-interface"></a><span data-ttu-id="c8408-102">ICLRDomainManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c8408-102">ICLRDomainManager Interface</span></span>
<span data-ttu-id="c8408-103">既定のアプリケーションドメインを初期化し、初期化プロパティを指定するために使用されるアプリケーションドメインマネージャーをホストが指定できるようにします。</span><span class="sxs-lookup"><span data-stu-id="c8408-103">Enables the host to specify the application domain manager that will be used to initialize the default application domain, and to specify initialization properties.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c8408-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="c8408-104">Methods</span></span>  
  
|<span data-ttu-id="c8408-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="c8408-105">Method</span></span>|<span data-ttu-id="c8408-106">説明</span><span class="sxs-lookup"><span data-stu-id="c8408-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c8408-107">SetAppDomainManagerType メソッド</span><span class="sxs-lookup"><span data-stu-id="c8408-107">SetAppDomainManagerType Method</span></span>](iclrdomainmanager-setappdomainmanagertype-method.md)|<span data-ttu-id="c8408-108"><xref:System.AppDomainManager?displayProperty=nameWithType>既定のアプリケーションドメインを初期化するために使用されるアプリケーションドメインマネージャーのクラスから派生した型を指定します。</span><span class="sxs-lookup"><span data-stu-id="c8408-108">Specifies the type, derived from the <xref:System.AppDomainManager?displayProperty=nameWithType> class, of the application domain manager that will be used to initialize the default application domain.</span></span>|  
|[<span data-ttu-id="c8408-109">SetPropertiesForDefaultAppDomain メソッド</span><span class="sxs-lookup"><span data-stu-id="c8408-109">SetPropertiesForDefaultAppDomain Method</span></span>](iclrdomainmanager-setpropertiesfordefaultappdomain-method.md)|<span data-ttu-id="c8408-110">既定のアプリケーションドメインを初期化するために使用されるプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="c8408-110">Sets properties that will be used to initialize the default application domain.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c8408-111">解説</span><span class="sxs-lookup"><span data-stu-id="c8408-111">Remarks</span></span>  
 <span data-ttu-id="c8408-112">このインターフェイスのインスタンスを取得するには、マネージャーの型 IID で[ICLRControl:: GetCLRManager](iclrcontrol-getclrmanager-method.md)メソッドを呼び出し `IID_ICLRDomainManager` ます。</span><span class="sxs-lookup"><span data-stu-id="c8408-112">To get an instance of this interface, call the [ICLRControl::GetCLRManager](iclrcontrol-getclrmanager-method.md) method with the manager type IID `IID_ICLRDomainManager`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8408-113">要件</span><span class="sxs-lookup"><span data-stu-id="c8408-113">Requirements</span></span>  
 <span data-ttu-id="c8408-114">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8408-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8408-115">**ヘッダー:** メタホスト .h</span><span class="sxs-lookup"><span data-stu-id="c8408-115">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="c8408-116">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="c8408-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c8408-117">**.NET Framework のバージョン:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c8408-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8408-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="c8408-118">See also</span></span>

- [<span data-ttu-id="c8408-119">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c8408-119">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="c8408-120">ホスティング</span><span class="sxs-lookup"><span data-stu-id="c8408-120">Hosting</span></span>](index.md)
