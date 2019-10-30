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
ms.openlocfilehash: 91483d5bdf1eb8e6b03d7691e2a95074e3789317
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134879"
---
# <a name="igchost-interface"></a><span data-ttu-id="8b989-102">IGCHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8b989-102">IGCHost Interface</span></span>
<span data-ttu-id="8b989-103">ガベージコレクションシステムに関する情報を取得し、ガベージコレクションのいくつかの側面を制御するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="8b989-103">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8b989-104">.NET Framework 4.5 以降では、 [IGCHost2:: SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md)メソッドを使用してガベージコレクションセグメントのサイズとガベージコレクションシステムのジェネレーション0の最大サイズを、`DWORD` の制限を超える値に設定できます。これは、 [SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/igchost-setgcstartuplimits-method.md)メソッドによって適用されます。</span><span class="sxs-lookup"><span data-stu-id="8b989-104">Starting with the .NET Framework 4.5, you can use the [IGCHost2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) method to set the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0 to values greater than the `DWORD` limit that is imposed by the [SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/igchost-setgcstartuplimits-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8b989-105">このインターフェイスは、専門家による使用のみを目的としています。</span><span class="sxs-lookup"><span data-stu-id="8b989-105">This interface is for expert usage only.</span></span> <span data-ttu-id="8b989-106">不適切に使用した場合、アプリケーションのパフォーマンスに影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8b989-106">It can affect the performance of an application if used improperly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8b989-107">メソッド</span><span class="sxs-lookup"><span data-stu-id="8b989-107">Methods</span></span>  
  
|<span data-ttu-id="8b989-108">メソッド</span><span class="sxs-lookup"><span data-stu-id="8b989-108">Method</span></span>|<span data-ttu-id="8b989-109">説明</span><span class="sxs-lookup"><span data-stu-id="8b989-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8b989-110">Collect メソッド</span><span class="sxs-lookup"><span data-stu-id="8b989-110">Collect Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-collect-method.md)|<span data-ttu-id="8b989-111">現在のガベージコレクションの状態に関係なく、指定したジェネレーションに対して強制的にコレクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="8b989-111">Forces a collection to occur for the given generation, regardless of the state of the current garbage collection.</span></span>|  
|[<span data-ttu-id="8b989-112">GetStats メソッド</span><span class="sxs-lookup"><span data-stu-id="8b989-112">GetStats Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-getstats-method.md)|<span data-ttu-id="8b989-113">ガベージコレクションシステムの現在の状態の統計を取得します。</span><span class="sxs-lookup"><span data-stu-id="8b989-113">Gets the statistics for the current state of the garbage collection system.</span></span>|  
|[<span data-ttu-id="8b989-114">GetThreadStats メソッド</span><span class="sxs-lookup"><span data-stu-id="8b989-114">GetThreadStats Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-getthreadstats-method.md)|<span data-ttu-id="8b989-115">ガベージコレクションのスレッドごとの統計を取得します。</span><span class="sxs-lookup"><span data-stu-id="8b989-115">Gets the per-thread statistics for garbage collection.</span></span>|  
|[<span data-ttu-id="8b989-116">SetGCStartupLimits メソッド</span><span class="sxs-lookup"><span data-stu-id="8b989-116">SetGCStartupLimits Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-setgcstartuplimits-method.md)|<span data-ttu-id="8b989-117">ジェネレーション0のセグメントサイズと最大サイズを設定します。</span><span class="sxs-lookup"><span data-stu-id="8b989-117">Sets the segment size and the maximum size for generation 0.</span></span>|  
|[<span data-ttu-id="8b989-118">SetVirtualMemLimit メソッド</span><span class="sxs-lookup"><span data-stu-id="8b989-118">SetVirtualMemLimit Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-setvirtualmemlimit-method.md)|<span data-ttu-id="8b989-119">ランタイムの仮想メモリの最大サイズを設定します。</span><span class="sxs-lookup"><span data-stu-id="8b989-119">Sets the maximum size of the runtime's virtual memory.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8b989-120">［要件］</span><span class="sxs-lookup"><span data-stu-id="8b989-120">Requirements</span></span>  
 <span data-ttu-id="8b989-121">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b989-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b989-122">**ヘッダー:** GCHost、GCHost</span><span class="sxs-lookup"><span data-stu-id="8b989-122">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="8b989-123">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="8b989-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8b989-124">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b989-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b989-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="8b989-125">See also</span></span>

- [<span data-ttu-id="8b989-126">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8b989-126">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="8b989-127">CorRuntimeHost コクラス</span><span class="sxs-lookup"><span data-stu-id="8b989-127">CorRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
