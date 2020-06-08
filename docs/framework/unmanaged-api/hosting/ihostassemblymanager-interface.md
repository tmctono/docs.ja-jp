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
ms.openlocfilehash: 4e32a36a4cf751bf7c5a2c918fde0122f21b7878
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501594"
---
# <a name="ihostassemblymanager-interface"></a><span data-ttu-id="7aa39-102">IHostAssemblyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7aa39-102">IHostAssemblyManager Interface</span></span>
<span data-ttu-id="7aa39-103">共通言語ランタイム (CLR) またはホストによって読み込まれる必要があるアセンブリのセットをホストが指定できるようにするメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="7aa39-103">Provides methods that allow a host to specify sets of assemblies that should be loaded by the common language runtime (CLR) or by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7aa39-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="7aa39-104">Methods</span></span>  
  
|<span data-ttu-id="7aa39-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="7aa39-105">Method</span></span>|<span data-ttu-id="7aa39-106">説明</span><span class="sxs-lookup"><span data-stu-id="7aa39-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7aa39-107">GetAssemblyStore メソッド</span><span class="sxs-lookup"><span data-stu-id="7aa39-107">GetAssemblyStore Method</span></span>](ihostassemblymanager-getassemblystore-method.md)|<span data-ttu-id="7aa39-108">ホストによって読み込まれたアセンブリの一覧を表す[IHostAssemblyStore](ihostassemblystore-interface.md)へのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="7aa39-108">Gets an interface pointer to an [IHostAssemblyStore](ihostassemblystore-interface.md) that represents the list of assemblies loaded by the host.</span></span>|  
|[<span data-ttu-id="7aa39-109">GetNonHostStoreAssemblies メソッド</span><span class="sxs-lookup"><span data-stu-id="7aa39-109">GetNonHostStoreAssemblies Method</span></span>](ihostassemblymanager-getnonhoststoreassemblies-method.md)|<span data-ttu-id="7aa39-110">ホストが CLR を読み込むことを想定しているアセンブリの一覧を表す[ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md)へのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="7aa39-110">Gets an interface pointer to an [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) that represents the list of assemblies that the host expects the CLR to load.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7aa39-111">解説</span><span class="sxs-lookup"><span data-stu-id="7aa39-111">Remarks</span></span>  
 <span data-ttu-id="7aa39-112">ホストがまたはを実装する必要はありません `IHostAssemblyManager` `IHostAssemblyStore` 。</span><span class="sxs-lookup"><span data-stu-id="7aa39-112">The host is not required to implement `IHostAssemblyManager` or `IHostAssemblyStore`.</span></span> <span data-ttu-id="7aa39-113">ホストがを実装している場合は `IHostAssemblyManager` 、も実装する必要があり `IHostAssemblyStore` ます。</span><span class="sxs-lookup"><span data-stu-id="7aa39-113">If the host does implement `IHostAssemblyManager`, it must also implement `IHostAssemblyStore`.</span></span>  
  
 <span data-ttu-id="7aa39-114">ランタイムは、 `IHostAssemblyManager` 初期化時に IID_IHostAssemblyManager のを使用して[IHostControl:: GetHostManager](ihostcontrol-gethostmanager-method.md)を呼び出すことにより、を照会し `IID` ます。</span><span class="sxs-lookup"><span data-stu-id="7aa39-114">The runtime queries for an `IHostAssemblyManager` by calling [IHostControl::GetHostManager](ihostcontrol-gethostmanager-method.md) upon initialization with an `IID` of IID_IHostAssemblyManager.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7aa39-115">要件</span><span class="sxs-lookup"><span data-stu-id="7aa39-115">Requirements</span></span>  
 <span data-ttu-id="7aa39-116">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7aa39-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7aa39-117">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="7aa39-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7aa39-118">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="7aa39-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7aa39-119">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7aa39-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7aa39-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="7aa39-120">See also</span></span>

- [<span data-ttu-id="7aa39-121">ICLRAssemblyReferenceList インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7aa39-121">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="7aa39-122">IHostAssemblyStore インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7aa39-122">IHostAssemblyStore Interface</span></span>](ihostassemblystore-interface.md)
- [<span data-ttu-id="7aa39-123">IHostControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7aa39-123">IHostControl Interface</span></span>](ihostcontrol-interface.md)
- [<span data-ttu-id="7aa39-124">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7aa39-124">Hosting Interfaces</span></span>](hosting-interfaces.md)
