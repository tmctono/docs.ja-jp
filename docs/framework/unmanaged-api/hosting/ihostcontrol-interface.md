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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 014e5c9951091046ae07374794743e82affcd5ad
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59122266"
---
# <a name="ihostcontrol-interface"></a><span data-ttu-id="0ac68-102">IHostControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0ac68-102">IHostControl Interface</span></span>
<span data-ttu-id="0ac68-103">アセンブリの読み込みを設定して、ホストがサポートするホスト インターフェイスを決定するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="0ac68-103">Provides methods for configuring the loading of assemblies, and for determining which hosting interfaces the host supports.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0ac68-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="0ac68-104">Methods</span></span>  
  
|<span data-ttu-id="0ac68-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="0ac68-105">Method</span></span>|<span data-ttu-id="0ac68-106">説明</span><span class="sxs-lookup"><span data-stu-id="0ac68-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0ac68-107">GetHostManager メソッド</span><span class="sxs-lookup"><span data-stu-id="0ac68-107">GetHostManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md)|<span data-ttu-id="0ac68-108">指定したホストのインターフェイスの実装にインターフェイス ポインターを取得します。`IID`します。</span><span class="sxs-lookup"><span data-stu-id="0ac68-108">Gets an interface pointer to the host's implementation of the interface with the specified `IID`.</span></span>|  
|[<span data-ttu-id="0ac68-109">SetAppDomainManager メソッド</span><span class="sxs-lookup"><span data-stu-id="0ac68-109">SetAppDomainManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-setappdomainmanager-method.md)|<span data-ttu-id="0ac68-110">アプリケーション ドメインが作成されたことをホストに通知します。</span><span class="sxs-lookup"><span data-stu-id="0ac68-110">Notifies the host that an application domain has been created.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0ac68-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="0ac68-111">Requirements</span></span>  
 <span data-ttu-id="0ac68-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0ac68-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ac68-113">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0ac68-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0ac68-114">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="0ac68-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="0ac68-115">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="0ac68-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0ac68-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="0ac68-116">See also</span></span>

- <xref:System.AppDomainManager>
- [<span data-ttu-id="0ac68-117">ICLRRuntimeHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0ac68-117">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
- [<span data-ttu-id="0ac68-118">ICLRControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0ac68-118">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="0ac68-119">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0ac68-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
