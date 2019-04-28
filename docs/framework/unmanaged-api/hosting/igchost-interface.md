---
title: IGCHost インターフェイス
ms.date: 03/30/2017
api_name:
- IGCHost
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IGCHost
helpviewer_keywords:
- IGCHost interface [.NET Framework hosting]
ms.assetid: 9ad70ffd-6963-4ab2-8c84-3d86c3fb8deb
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3202aa25261863dae953e3edac36f3406fa001d8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61699754"
---
# <a name="igchost-interface"></a><span data-ttu-id="72a8a-102">IGCHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="72a8a-102">IGCHost Interface</span></span>
<span data-ttu-id="72a8a-103">ガベージ コレクション システムに関する情報を取得するため、ガベージ コレクションの一部の側面を制御するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="72a8a-103">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="72a8a-104">以降では、 [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)]、使用することができます、 [igchost 2::setgcstartuplimitsex](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md)ガベージ コレクション セグメントのサイズと、ガベージ コレクション システムのジェネレーション 0 の最大サイズ値に設定するよりも大きいメソッド、`DWORD`はによって課される制限、 [SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/igchost-setgcstartuplimits-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="72a8a-104">Starting with the [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], you can use the [IGCHost2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) method to set the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0 to values greater than the `DWORD` limit that is imposed by the [SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/igchost-setgcstartuplimits-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="72a8a-105">インターフェイスは、上級者のみです。</span><span class="sxs-lookup"><span data-stu-id="72a8a-105">This interface is for expert usage only.</span></span> <span data-ttu-id="72a8a-106">これは不適切に使用されている場合、アプリケーションのパフォーマンスに影響することができます。</span><span class="sxs-lookup"><span data-stu-id="72a8a-106">It can affect the performance of an application if used improperly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="72a8a-107">メソッド</span><span class="sxs-lookup"><span data-stu-id="72a8a-107">Methods</span></span>  
  
|<span data-ttu-id="72a8a-108">メソッド</span><span class="sxs-lookup"><span data-stu-id="72a8a-108">Method</span></span>|<span data-ttu-id="72a8a-109">説明</span><span class="sxs-lookup"><span data-stu-id="72a8a-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="72a8a-110">Collect メソッド</span><span class="sxs-lookup"><span data-stu-id="72a8a-110">Collect Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-collect-method.md)|<span data-ttu-id="72a8a-111">コレクションの現在のガベージ コレクションの状態に関係なく、特定のジェネレーションの実行を強制します。</span><span class="sxs-lookup"><span data-stu-id="72a8a-111">Forces a collection to occur for the given generation, regardless of the state of the current garbage collection.</span></span>|  
|[<span data-ttu-id="72a8a-112">GetStats メソッド</span><span class="sxs-lookup"><span data-stu-id="72a8a-112">GetStats Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-getstats-method.md)|<span data-ttu-id="72a8a-113">ガベージ コレクション システムの現在の状態の統計情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="72a8a-113">Gets the statistics for the current state of the garbage collection system.</span></span>|  
|[<span data-ttu-id="72a8a-114">GetThreadStats メソッド</span><span class="sxs-lookup"><span data-stu-id="72a8a-114">GetThreadStats Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-getthreadstats-method.md)|<span data-ttu-id="72a8a-115">ガベージ コレクションのスレッドごとの統計情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="72a8a-115">Gets the per-thread statistics for garbage collection.</span></span>|  
|[<span data-ttu-id="72a8a-116">SetGCStartupLimits メソッド</span><span class="sxs-lookup"><span data-stu-id="72a8a-116">SetGCStartupLimits Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-setgcstartuplimits-method.md)|<span data-ttu-id="72a8a-117">ジェネレーション 0 のセグメントのサイズと最大サイズを設定します。</span><span class="sxs-lookup"><span data-stu-id="72a8a-117">Sets the segment size and the maximum size for generation 0.</span></span>|  
|[<span data-ttu-id="72a8a-118">SetVirtualMemLimit メソッド</span><span class="sxs-lookup"><span data-stu-id="72a8a-118">SetVirtualMemLimit Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-setvirtualmemlimit-method.md)|<span data-ttu-id="72a8a-119">ランタイムの仮想メモリの最大サイズを設定します。</span><span class="sxs-lookup"><span data-stu-id="72a8a-119">Sets the maximum size of the runtime's virtual memory.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="72a8a-120">必要条件</span><span class="sxs-lookup"><span data-stu-id="72a8a-120">Requirements</span></span>  
 <span data-ttu-id="72a8a-121">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="72a8a-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72a8a-122">**ヘッダー:** GCHost.idl、GCHost.h</span><span class="sxs-lookup"><span data-stu-id="72a8a-122">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="72a8a-123">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="72a8a-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="72a8a-124">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="72a8a-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72a8a-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="72a8a-125">See also</span></span>

- [<span data-ttu-id="72a8a-126">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="72a8a-126">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="72a8a-127">CorRuntimeHost コクラス</span><span class="sxs-lookup"><span data-stu-id="72a8a-127">CorRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
