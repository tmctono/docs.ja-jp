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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 21ce9cbd007858c0f39e12622eff819154ab83f0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69928617"
---
# <a name="igchost2-interface"></a><span data-ttu-id="0b10f-102">IGCHost2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0b10f-102">IGCHost2 Interface</span></span>
<span data-ttu-id="0b10f-103">ガベージコレクションシステムに関する情報を取得し、ガベージコレクションのいくつかの側面を制御するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="0b10f-103">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0b10f-104">新しい開発では、代わりに[ICLRGCManager2](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md)インターフェイスを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0b10f-104">For new development, we recommend that you use the [ICLRGCManager2](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md) interface instead.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0b10f-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="0b10f-105">Methods</span></span>  
  
|<span data-ttu-id="0b10f-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="0b10f-106">Method</span></span>|<span data-ttu-id="0b10f-107">説明</span><span class="sxs-lookup"><span data-stu-id="0b10f-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0b10f-108">SetGCStartupLimitsEx メソッド</span><span class="sxs-lookup"><span data-stu-id="0b10f-108">SetGCStartupLimitsEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md)|<span data-ttu-id="0b10f-109">ジェネレーション0のセグメントサイズと最大サイズを設定します。</span><span class="sxs-lookup"><span data-stu-id="0b10f-109">Sets the segment size and the maximum size for generation 0.</span></span> <span data-ttu-id="0b10f-110">より`DWORD`大きいジェネレーション0およびセグメントサイズを有効にします。</span><span class="sxs-lookup"><span data-stu-id="0b10f-110">Enables generation 0 and segment sizes larger than `DWORD`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0b10f-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="0b10f-111">Requirements</span></span>  
 <span data-ttu-id="0b10f-112">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0b10f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0b10f-113">**ヘッダー:** GCHost、GCHost</span><span class="sxs-lookup"><span data-stu-id="0b10f-113">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="0b10f-114">**ライブラリ**Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="0b10f-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0b10f-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0b10f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b10f-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="0b10f-116">See also</span></span>

- [<span data-ttu-id="0b10f-117">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0b10f-117">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="0b10f-118">CLR ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0b10f-118">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)
- [<span data-ttu-id="0b10f-119">CorRuntimeHost コクラス</span><span class="sxs-lookup"><span data-stu-id="0b10f-119">CorRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
