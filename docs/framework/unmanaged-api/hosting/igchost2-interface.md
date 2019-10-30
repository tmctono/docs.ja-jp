---
title: IGCHost2 インターフェイス
ms.date: 03/30/2017
api_name:
- IGCHost2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IGCHost2
helpviewer_keywords:
- IGCHost2 interface [.NET Framework hosting]
ms.assetid: e5323fa4-18ac-424d-859d-a65a550d08d9
topic_type:
- apiref
ms.openlocfilehash: 43c16415c91521194e0d88be84dd176c3fdadad1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134837"
---
# <a name="igchost2-interface"></a><span data-ttu-id="2455b-102">IGCHost2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2455b-102">IGCHost2 Interface</span></span>
<span data-ttu-id="2455b-103">ガベージコレクションシステムに関する情報を取得し、ガベージコレクションのいくつかの側面を制御するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="2455b-103">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2455b-104">新しい開発では、代わりに[ICLRGCManager2](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md)インターフェイスを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2455b-104">For new development, we recommend that you use the [ICLRGCManager2](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md) interface instead.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2455b-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="2455b-105">Methods</span></span>  
  
|<span data-ttu-id="2455b-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="2455b-106">Method</span></span>|<span data-ttu-id="2455b-107">説明</span><span class="sxs-lookup"><span data-stu-id="2455b-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2455b-108">SetGCStartupLimitsEx メソッド</span><span class="sxs-lookup"><span data-stu-id="2455b-108">SetGCStartupLimitsEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md)|<span data-ttu-id="2455b-109">ジェネレーション0のセグメントサイズと最大サイズを設定します。</span><span class="sxs-lookup"><span data-stu-id="2455b-109">Sets the segment size and the maximum size for generation 0.</span></span> <span data-ttu-id="2455b-110">`DWORD`より大きいジェネレーション0およびセグメントサイズを有効にします。</span><span class="sxs-lookup"><span data-stu-id="2455b-110">Enables generation 0 and segment sizes larger than `DWORD`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2455b-111">［要件］</span><span class="sxs-lookup"><span data-stu-id="2455b-111">Requirements</span></span>  
 <span data-ttu-id="2455b-112">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2455b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2455b-113">**ヘッダー:** GCHost、GCHost</span><span class="sxs-lookup"><span data-stu-id="2455b-113">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="2455b-114">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="2455b-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2455b-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2455b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2455b-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="2455b-116">See also</span></span>

- [<span data-ttu-id="2455b-117">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2455b-117">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="2455b-118">CLR ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2455b-118">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)
- [<span data-ttu-id="2455b-119">CorRuntimeHost コクラス</span><span class="sxs-lookup"><span data-stu-id="2455b-119">CorRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
