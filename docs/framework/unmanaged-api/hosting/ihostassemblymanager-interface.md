---
title: IHostAssemblyManager インターフェイス
ms.date: 03/30/2017
api_name:
- IHostAssemblyManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyManager
helpviewer_keywords:
- IHostAssemblyManager interface [.NET Framework hosting]
ms.assetid: dfec05bb-3cd7-4bd5-b396-a4f097c3a636
topic_type:
- apiref
ms.openlocfilehash: d9feeaf5f85d6f84a13e74a893b82c97fdaf023c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124505"
---
# <a name="ihostassemblymanager-interface"></a><span data-ttu-id="5c3ca-102">IHostAssemblyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5c3ca-102">IHostAssemblyManager Interface</span></span>
<span data-ttu-id="5c3ca-103">共通言語ランタイム (CLR) またはホストによって読み込まれる必要があるアセンブリのセットをホストが指定できるようにするメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="5c3ca-103">Provides methods that allow a host to specify sets of assemblies that should be loaded by the common language runtime (CLR) or by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5c3ca-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="5c3ca-104">Methods</span></span>  
  
|<span data-ttu-id="5c3ca-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="5c3ca-105">Method</span></span>|<span data-ttu-id="5c3ca-106">説明</span><span class="sxs-lookup"><span data-stu-id="5c3ca-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5c3ca-107">GetAssemblyStore メソッド</span><span class="sxs-lookup"><span data-stu-id="5c3ca-107">GetAssemblyStore Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getassemblystore-method.md)|<span data-ttu-id="5c3ca-108">ホストによって読み込まれたアセンブリの一覧を表す[IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)へのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="5c3ca-108">Gets an interface pointer to an [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md) that represents the list of assemblies loaded by the host.</span></span>|  
|[<span data-ttu-id="5c3ca-109">GetNonHostStoreAssemblies メソッド</span><span class="sxs-lookup"><span data-stu-id="5c3ca-109">GetNonHostStoreAssemblies Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md)|<span data-ttu-id="5c3ca-110">ホストが CLR を読み込むことを想定しているアセンブリの一覧を表す[ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)へのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="5c3ca-110">Gets an interface pointer to an [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) that represents the list of assemblies that the host expects the CLR to load.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5c3ca-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="5c3ca-111">Remarks</span></span>  
 <span data-ttu-id="5c3ca-112">ホストは、`IHostAssemblyManager` または `IHostAssemblyStore`を実装する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="5c3ca-112">The host is not required to implement `IHostAssemblyManager` or `IHostAssemblyStore`.</span></span> <span data-ttu-id="5c3ca-113">ホストが `IHostAssemblyManager`を実装している場合は、`IHostAssemblyStore`も実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c3ca-113">If the host does implement `IHostAssemblyManager`, it must also implement `IHostAssemblyStore`.</span></span>  
  
 <span data-ttu-id="5c3ca-114">ランタイムは、初期化時に IID_IHostAssemblyManager の `IID` で[IHostControl:: GetHostManager](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md)を呼び出すことによって、`IHostAssemblyManager` を照会します。</span><span class="sxs-lookup"><span data-stu-id="5c3ca-114">The runtime queries for an `IHostAssemblyManager` by calling [IHostControl::GetHostManager](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md) upon initialization with an `IID` of IID_IHostAssemblyManager.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c3ca-115">［要件］</span><span class="sxs-lookup"><span data-stu-id="5c3ca-115">Requirements</span></span>  
 <span data-ttu-id="5c3ca-116">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c3ca-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c3ca-117">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="5c3ca-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5c3ca-118">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="5c3ca-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5c3ca-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c3ca-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c3ca-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="5c3ca-120">See also</span></span>

- [<span data-ttu-id="5c3ca-121">ICLRAssemblyReferenceList インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5c3ca-121">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="5c3ca-122">IHostAssemblyStore インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5c3ca-122">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
- [<span data-ttu-id="5c3ca-123">IHostControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5c3ca-123">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
- [<span data-ttu-id="5c3ca-124">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5c3ca-124">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
