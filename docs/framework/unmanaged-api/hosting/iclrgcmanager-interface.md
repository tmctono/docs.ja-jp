---
title: ICLRGCManager インターフェイス
ms.date: 03/30/2017
api_name:
- ICLRGCManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRGCManager
helpviewer_keywords:
- ICLRGCManager interface [.NET Framework hosting]
ms.assetid: fb511c9b-3fe4-41b0-822a-6ba4a079d1f5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b9519f7c2df5cf078bac6be038275527d7741edb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59152166"
---
# <a name="iclrgcmanager-interface"></a><span data-ttu-id="d3b32-102">ICLRGCManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d3b32-102">ICLRGCManager Interface</span></span>
<span data-ttu-id="d3b32-103">ホストが共通言語ランタイムのガベージ コレクション システムと対話できるようにするメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="d3b32-103">Provides methods that allow a host to interact with the common language runtime's garbage collection system.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d3b32-104">以降では、 [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)]、使用することができます、 [iclrgcmanager 2::setgcstartuplimitsex](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md)ガベージ コレクション セグメントのサイズと、ガベージ コレクション システムのジェネレーション 0 の最大サイズ値に設定する大きいメソッド`DWORD`はによって課される制限、 [SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-setgcstartuplimits-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="d3b32-104">Starting with the [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], you can use the [ICLRGCManager2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) method to set the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0 to values greater than the `DWORD` limit that is imposed by the [SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-setgcstartuplimits-method.md) method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d3b32-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="d3b32-105">Methods</span></span>  
  
|<span data-ttu-id="d3b32-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="d3b32-106">Method</span></span>|<span data-ttu-id="d3b32-107">説明</span><span class="sxs-lookup"><span data-stu-id="d3b32-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d3b32-108">Collect メソッド</span><span class="sxs-lookup"><span data-stu-id="d3b32-108">Collect Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-collect-method.md)|<span data-ttu-id="d3b32-109">指定したジェネレーションのガベージ コレクションを強制します。</span><span class="sxs-lookup"><span data-stu-id="d3b32-109">Forces a garbage collection for the specified generation.</span></span>|  
|[<span data-ttu-id="d3b32-110">GetStats メソッド</span><span class="sxs-lookup"><span data-stu-id="d3b32-110">GetStats Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md)|<span data-ttu-id="d3b32-111">ガベージ コレクション システムに関する現在の統計情報のセットを取得します。</span><span class="sxs-lookup"><span data-stu-id="d3b32-111">Gets a set of current statistics about the garbage collection system.</span></span>|  
|[<span data-ttu-id="d3b32-112">SetGCStartupLimits メソッド</span><span class="sxs-lookup"><span data-stu-id="d3b32-112">SetGCStartupLimits Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-setgcstartuplimits-method.md)|<span data-ttu-id="d3b32-113">ガベージ コレクション セグメントのサイズと、ガベージ コレクション システムのジェネレーション 0 の最大サイズを設定します。</span><span class="sxs-lookup"><span data-stu-id="d3b32-113">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d3b32-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="d3b32-114">Remarks</span></span>  
 <span data-ttu-id="d3b32-115">共通言語ランタイム (CLR) で、管理対象のガベージ コレクションのメカニズムを実装する<xref:System.GC>型。</span><span class="sxs-lookup"><span data-stu-id="d3b32-115">The common language runtime (CLR) implements its garbage collection mechanism with the managed <xref:System.GC> type.</span></span> <span data-ttu-id="d3b32-116">ガベージ コレクションのシステムの詳細については、次を参照してください。[ガベージ コレクション](../../../../docs/standard/garbage-collection/index.md)します。</span><span class="sxs-lookup"><span data-stu-id="d3b32-116">For more information about the garbage collection system, see [Garbage Collection](../../../../docs/standard/garbage-collection/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d3b32-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="d3b32-117">Requirements</span></span>  
 <span data-ttu-id="d3b32-118">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d3b32-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3b32-119">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d3b32-119">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d3b32-120">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="d3b32-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="d3b32-121">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="d3b32-121">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d3b32-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="d3b32-122">See also</span></span>

- [<span data-ttu-id="d3b32-123">Automatic Memory Management</span><span class="sxs-lookup"><span data-stu-id="d3b32-123">Automatic Memory Management</span></span>](../../../../docs/standard/automatic-memory-management.md)
- [<span data-ttu-id="d3b32-124">COR_GC_STATS 構造体</span><span class="sxs-lookup"><span data-stu-id="d3b32-124">COR_GC_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)
- [<span data-ttu-id="d3b32-125">ICLRControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d3b32-125">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="d3b32-126">CLR ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d3b32-126">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)
- [<span data-ttu-id="d3b32-127">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d3b32-127">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="d3b32-128">ホスト</span><span class="sxs-lookup"><span data-stu-id="d3b32-128">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
