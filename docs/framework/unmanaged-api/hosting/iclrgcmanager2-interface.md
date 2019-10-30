---
title: ICLRGCManager2 インターフェイス
ms.date: 03/30/2017
api_name:
- ICLRGCManager2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRGCManager2
helpviewer_keywords:
- ICLRGCManager2 interface [.NET Framework hosting]
ms.assetid: 4b5ffd7b-9ad7-41cd-9bba-34030ae3da7e
topic_type:
- apiref
ms.openlocfilehash: 72ffd7b47795ee8e46f8fbff07559133843793e6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141161"
---
# <a name="iclrgcmanager2-interface"></a><span data-ttu-id="f3666-102">ICLRGCManager2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f3666-102">ICLRGCManager2 Interface</span></span>
<span data-ttu-id="f3666-103">ホストが共通言語ランタイムのガベージコレクションシステムと対話できるようにするメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="f3666-103">Provides methods that allow a host to interact with the common language runtime's garbage collection system.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f3666-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="f3666-104">Methods</span></span>  
  
|<span data-ttu-id="f3666-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="f3666-105">Method</span></span>|<span data-ttu-id="f3666-106">説明</span><span class="sxs-lookup"><span data-stu-id="f3666-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f3666-107">SetGCStartupLimitsEx メソッド</span><span class="sxs-lookup"><span data-stu-id="f3666-107">SetGCStartupLimitsEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md)|<span data-ttu-id="f3666-108">ガベージコレクションセグメントのサイズとガベージコレクションシステムのジェネレーション0の最大サイズを設定します。</span><span class="sxs-lookup"><span data-stu-id="f3666-108">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span> <span data-ttu-id="f3666-109">`DWORD`より大きいジェネレーション0およびセグメントサイズを有効にします。</span><span class="sxs-lookup"><span data-stu-id="f3666-109">Enables generation 0 and segment sizes larger than `DWORD`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f3666-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="f3666-110">Remarks</span></span>  
 <span data-ttu-id="f3666-111">このインターフェイスは、 [ICLRGCManager インターフェイス](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)から継承されます。</span><span class="sxs-lookup"><span data-stu-id="f3666-111">This interface inherits from the [ICLRGCManager Interface](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md).</span></span>  
  
 <span data-ttu-id="f3666-112">共通言語ランタイム (CLR) は、マネージ <xref:System.GC> 型を使用して、そのガベージコレクション機構を実装します。</span><span class="sxs-lookup"><span data-stu-id="f3666-112">The common language runtime (CLR) implements its garbage collection mechanism with the managed <xref:System.GC> type.</span></span> <span data-ttu-id="f3666-113">ガベージコレクションシステムの詳細については、「[ガベージコレクション](../../../standard/garbage-collection/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3666-113">For more information about the garbage collection system, see [Garbage Collection](../../../standard/garbage-collection/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f3666-114">［要件］</span><span class="sxs-lookup"><span data-stu-id="f3666-114">Requirements</span></span>  
 <span data-ttu-id="f3666-115">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3666-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3666-116">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="f3666-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f3666-117">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="f3666-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f3666-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3666-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3666-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="f3666-119">See also</span></span>

- [<span data-ttu-id="f3666-120">自動メモリ管理</span><span class="sxs-lookup"><span data-stu-id="f3666-120">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="f3666-121">COR_GC_STATS 構造体</span><span class="sxs-lookup"><span data-stu-id="f3666-121">COR_GC_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)
- [<span data-ttu-id="f3666-122">ICLRControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f3666-122">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="f3666-123">.NET Framework 4 および 4.5 で追加された CLR ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f3666-123">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [<span data-ttu-id="f3666-124">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f3666-124">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="f3666-125">ホスティング</span><span class="sxs-lookup"><span data-stu-id="f3666-125">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
