---
title: ICLRProbingAssemblyEnum インターフェイス
ms.date: 03/30/2017
api_name:
- ICLRProbingAssemblyEnum
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRProbingAssemblyEnum
helpviewer_keywords:
- ICLRProbingAssemblyEnum interface [.NET Framework hosting]
ms.assetid: e7d3ccab-b0f0-4872-8935-0ed72920171b
topic_type:
- apiref
ms.openlocfilehash: e1459c1604f3f8f043fd9b61533235ab7861c910
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120562"
---
# <a name="iclrprobingassemblyenum-interface"></a><span data-ttu-id="d67ae-102">ICLRProbingAssemblyEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d67ae-102">ICLRProbingAssemblyEnum Interface</span></span>
<span data-ttu-id="d67ae-103">共通言語ランタイム (CLR) の内部にあるアセンブリの id 情報を使用して、ホストがアセンブリのプローブ id を取得できるようにするメソッドを提供します。このメソッドは、その id を作成または理解する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="d67ae-103">Provides methods that enable the host to get the probing identities of an assembly by using the assembly's identity information that is internal to the common language runtime (CLR), without needing to create or understand that identity.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d67ae-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="d67ae-104">Methods</span></span>  
  
|<span data-ttu-id="d67ae-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="d67ae-105">Method</span></span>|<span data-ttu-id="d67ae-106">説明</span><span class="sxs-lookup"><span data-stu-id="d67ae-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d67ae-107">Get メソッド</span><span class="sxs-lookup"><span data-stu-id="d67ae-107">Get Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-get-method.md)|<span data-ttu-id="d67ae-108">指定したインデックス位置にあるアセンブリ id を取得します。</span><span class="sxs-lookup"><span data-stu-id="d67ae-108">Gets the assembly identity at the specified index.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d67ae-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="d67ae-109">Remarks</span></span>  
 <span data-ttu-id="d67ae-110">[ICLRAssemblyIdentityManager:: GetProbingAssembliesFromReference](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md)などのメソッドは、`ICLRProbingAssemblyEnum` インスタンスを返します。</span><span class="sxs-lookup"><span data-stu-id="d67ae-110">Methods such as [ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md) return an `ICLRProbingAssemblyEnum` instance.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d67ae-111">［要件］</span><span class="sxs-lookup"><span data-stu-id="d67ae-111">Requirements</span></span>  
 <span data-ttu-id="d67ae-112">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d67ae-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d67ae-113">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="d67ae-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d67ae-114">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="d67ae-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d67ae-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d67ae-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d67ae-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="d67ae-116">See also</span></span>

- [<span data-ttu-id="d67ae-117">ICLRAssemblyIdentityManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d67ae-117">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="d67ae-118">ICLRAssemblyReferenceList インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d67ae-118">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="d67ae-119">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d67ae-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
