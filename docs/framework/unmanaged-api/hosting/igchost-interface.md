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
ms.openlocfilehash: 1d3f588bfc9799ed4591114b28d081ab417678b1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69914797"
---
# <a name="igchost-interface"></a><span data-ttu-id="a5571-102">IGCHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a5571-102">IGCHost Interface</span></span>
<span data-ttu-id="a5571-103">ガベージコレクションシステムに関する情報を取得し、ガベージコレクションのいくつかの側面を制御するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="a5571-103">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a5571-104">.NET Framework 4.5 以降では、 [IGCHost2:: SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md)メソッドを使用してガベージコレクションセグメントのサイズを設定できます。ガベージコレクションシステムのジェネレーション0の最大サイズは、 `DWORD`[SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/igchost-setgcstartuplimits-method.md)メソッドによって課される制限。</span><span class="sxs-lookup"><span data-stu-id="a5571-104">Starting with the .NET Framework 4.5, you can use the [IGCHost2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) method to set the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0 to values greater than the `DWORD` limit that is imposed by the [SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/igchost-setgcstartuplimits-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a5571-105">このインターフェイスは、専門家による使用のみを目的としています。</span><span class="sxs-lookup"><span data-stu-id="a5571-105">This interface is for expert usage only.</span></span> <span data-ttu-id="a5571-106">不適切に使用した場合、アプリケーションのパフォーマンスに影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a5571-106">It can affect the performance of an application if used improperly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a5571-107">メソッド</span><span class="sxs-lookup"><span data-stu-id="a5571-107">Methods</span></span>  
  
|<span data-ttu-id="a5571-108">メソッド</span><span class="sxs-lookup"><span data-stu-id="a5571-108">Method</span></span>|<span data-ttu-id="a5571-109">説明</span><span class="sxs-lookup"><span data-stu-id="a5571-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a5571-110">Collect メソッド</span><span class="sxs-lookup"><span data-stu-id="a5571-110">Collect Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-collect-method.md)|<span data-ttu-id="a5571-111">現在のガベージコレクションの状態に関係なく、指定したジェネレーションに対して強制的にコレクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="a5571-111">Forces a collection to occur for the given generation, regardless of the state of the current garbage collection.</span></span>|  
|[<span data-ttu-id="a5571-112">GetStats メソッド</span><span class="sxs-lookup"><span data-stu-id="a5571-112">GetStats Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-getstats-method.md)|<span data-ttu-id="a5571-113">ガベージコレクションシステムの現在の状態の統計を取得します。</span><span class="sxs-lookup"><span data-stu-id="a5571-113">Gets the statistics for the current state of the garbage collection system.</span></span>|  
|[<span data-ttu-id="a5571-114">GetThreadStats メソッド</span><span class="sxs-lookup"><span data-stu-id="a5571-114">GetThreadStats Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-getthreadstats-method.md)|<span data-ttu-id="a5571-115">ガベージコレクションのスレッドごとの統計を取得します。</span><span class="sxs-lookup"><span data-stu-id="a5571-115">Gets the per-thread statistics for garbage collection.</span></span>|  
|[<span data-ttu-id="a5571-116">SetGCStartupLimits メソッド</span><span class="sxs-lookup"><span data-stu-id="a5571-116">SetGCStartupLimits Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-setgcstartuplimits-method.md)|<span data-ttu-id="a5571-117">ジェネレーション0のセグメントサイズと最大サイズを設定します。</span><span class="sxs-lookup"><span data-stu-id="a5571-117">Sets the segment size and the maximum size for generation 0.</span></span>|  
|[<span data-ttu-id="a5571-118">SetVirtualMemLimit メソッド</span><span class="sxs-lookup"><span data-stu-id="a5571-118">SetVirtualMemLimit Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-setvirtualmemlimit-method.md)|<span data-ttu-id="a5571-119">ランタイムの仮想メモリの最大サイズを設定します。</span><span class="sxs-lookup"><span data-stu-id="a5571-119">Sets the maximum size of the runtime's virtual memory.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a5571-120">必要条件</span><span class="sxs-lookup"><span data-stu-id="a5571-120">Requirements</span></span>  
 <span data-ttu-id="a5571-121">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5571-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5571-122">**ヘッダー:** GCHost、GCHost</span><span class="sxs-lookup"><span data-stu-id="a5571-122">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="a5571-123">**ライブラリ**Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="a5571-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a5571-124">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a5571-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5571-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="a5571-125">See also</span></span>

- [<span data-ttu-id="a5571-126">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a5571-126">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="a5571-127">CorRuntimeHost コクラス</span><span class="sxs-lookup"><span data-stu-id="a5571-127">CorRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
