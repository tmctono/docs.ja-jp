---
title: IHostControl インターフェイス
ms.date: 03/30/2017
api_name:
- IHostControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostControl
helpviewer_keywords:
- IHostControl interface [.NET Framework hosting]
ms.assetid: a4ae0d1f-ade9-4b0a-a122-93ed11a5e6b3
topic_type:
- apiref
ms.openlocfilehash: 444a78705c61d5a53764f55185ef1a907830bd71
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73195880"
---
# <a name="ihostcontrol-interface"></a><span data-ttu-id="a8ae6-102">IHostControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a8ae6-102">IHostControl Interface</span></span>
<span data-ttu-id="a8ae6-103">アセンブリの読み込みを構成し、ホストがサポートするホストインターフェイスを決定するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="a8ae6-103">Provides methods for configuring the loading of assemblies, and for determining which hosting interfaces the host supports.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a8ae6-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="a8ae6-104">Methods</span></span>  
  
|<span data-ttu-id="a8ae6-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="a8ae6-105">Method</span></span>|<span data-ttu-id="a8ae6-106">説明</span><span class="sxs-lookup"><span data-stu-id="a8ae6-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a8ae6-107">GetHostManager メソッド</span><span class="sxs-lookup"><span data-stu-id="a8ae6-107">GetHostManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md)|<span data-ttu-id="a8ae6-108">指定した `IID`を使用して、ホストのインターフェイス実装へのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="a8ae6-108">Gets an interface pointer to the host's implementation of the interface with the specified `IID`.</span></span>|  
|[<span data-ttu-id="a8ae6-109">SetAppDomainManager メソッド</span><span class="sxs-lookup"><span data-stu-id="a8ae6-109">SetAppDomainManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-setappdomainmanager-method.md)|<span data-ttu-id="a8ae6-110">アプリケーションドメインが作成されたことをホストに通知します。</span><span class="sxs-lookup"><span data-stu-id="a8ae6-110">Notifies the host that an application domain has been created.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a8ae6-111">［要件］</span><span class="sxs-lookup"><span data-stu-id="a8ae6-111">Requirements</span></span>  
 <span data-ttu-id="a8ae6-112">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a8ae6-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8ae6-113">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="a8ae6-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a8ae6-114">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="a8ae6-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a8ae6-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8ae6-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8ae6-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="a8ae6-116">See also</span></span>

- <xref:System.AppDomainManager>
- [<span data-ttu-id="a8ae6-117">ICLRRuntimeHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a8ae6-117">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
- [<span data-ttu-id="a8ae6-118">ICLRControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a8ae6-118">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="a8ae6-119">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a8ae6-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
