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
ms.openlocfilehash: 6b6f2dbaa49c29f6614e9c39a3f408d4d1453983
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501626"
---
# <a name="igchost-interface"></a><span data-ttu-id="ff14d-102">IGCHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ff14d-102">IGCHost Interface</span></span>
<span data-ttu-id="ff14d-103">ガベージコレクションシステムに関する情報を取得し、ガベージコレクションのいくつかの側面を制御するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="ff14d-103">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ff14d-104">.NET Framework 4.5 以降では、 [IGCHost2:: SetGCStartupLimitsEx](igchost2-setgcstartuplimitsex-method.md)メソッドを使用して、ガベージコレクションセグメントのサイズと、ガベージコレクションシステムのジェネレーション0の最大サイズを、 `DWORD` [SetGCStartupLimits](igchost-setgcstartuplimits-method.md)メソッドによって設定された制限を超える値に設定できます。</span><span class="sxs-lookup"><span data-stu-id="ff14d-104">Starting with the .NET Framework 4.5, you can use the [IGCHost2::SetGCStartupLimitsEx](igchost2-setgcstartuplimitsex-method.md) method to set the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0 to values greater than the `DWORD` limit that is imposed by the [SetGCStartupLimits](igchost-setgcstartuplimits-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ff14d-105">このインターフェイスは、専門家による使用のみを目的としています。</span><span class="sxs-lookup"><span data-stu-id="ff14d-105">This interface is for expert usage only.</span></span> <span data-ttu-id="ff14d-106">不適切に使用した場合、アプリケーションのパフォーマンスに影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ff14d-106">It can affect the performance of an application if used improperly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ff14d-107">メソッド</span><span class="sxs-lookup"><span data-stu-id="ff14d-107">Methods</span></span>  
  
|<span data-ttu-id="ff14d-108">メソッド</span><span class="sxs-lookup"><span data-stu-id="ff14d-108">Method</span></span>|<span data-ttu-id="ff14d-109">説明</span><span class="sxs-lookup"><span data-stu-id="ff14d-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ff14d-110">Collect メソッド</span><span class="sxs-lookup"><span data-stu-id="ff14d-110">Collect Method</span></span>](igchost-collect-method.md)|<span data-ttu-id="ff14d-111">現在のガベージコレクションの状態に関係なく、指定したジェネレーションに対して強制的にコレクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="ff14d-111">Forces a collection to occur for the given generation, regardless of the state of the current garbage collection.</span></span>|  
|[<span data-ttu-id="ff14d-112">GetStats メソッド</span><span class="sxs-lookup"><span data-stu-id="ff14d-112">GetStats Method</span></span>](igchost-getstats-method.md)|<span data-ttu-id="ff14d-113">ガベージコレクションシステムの現在の状態の統計を取得します。</span><span class="sxs-lookup"><span data-stu-id="ff14d-113">Gets the statistics for the current state of the garbage collection system.</span></span>|  
|[<span data-ttu-id="ff14d-114">GetThreadStats メソッド</span><span class="sxs-lookup"><span data-stu-id="ff14d-114">GetThreadStats Method</span></span>](igchost-getthreadstats-method.md)|<span data-ttu-id="ff14d-115">ガベージコレクションのスレッドごとの統計を取得します。</span><span class="sxs-lookup"><span data-stu-id="ff14d-115">Gets the per-thread statistics for garbage collection.</span></span>|  
|[<span data-ttu-id="ff14d-116">SetGCStartupLimits メソッド</span><span class="sxs-lookup"><span data-stu-id="ff14d-116">SetGCStartupLimits Method</span></span>](igchost-setgcstartuplimits-method.md)|<span data-ttu-id="ff14d-117">ジェネレーション0のセグメントサイズと最大サイズを設定します。</span><span class="sxs-lookup"><span data-stu-id="ff14d-117">Sets the segment size and the maximum size for generation 0.</span></span>|  
|[<span data-ttu-id="ff14d-118">SetVirtualMemLimit メソッド</span><span class="sxs-lookup"><span data-stu-id="ff14d-118">SetVirtualMemLimit Method</span></span>](igchost-setvirtualmemlimit-method.md)|<span data-ttu-id="ff14d-119">ランタイムの仮想メモリの最大サイズを設定します。</span><span class="sxs-lookup"><span data-stu-id="ff14d-119">Sets the maximum size of the runtime's virtual memory.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ff14d-120">要件</span><span class="sxs-lookup"><span data-stu-id="ff14d-120">Requirements</span></span>  
 <span data-ttu-id="ff14d-121">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ff14d-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff14d-122">**ヘッダー:** GCHost、GCHost</span><span class="sxs-lookup"><span data-stu-id="ff14d-122">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="ff14d-123">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="ff14d-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ff14d-124">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff14d-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff14d-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="ff14d-125">See also</span></span>

- [<span data-ttu-id="ff14d-126">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ff14d-126">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="ff14d-127">CorRuntimeHost コクラス</span><span class="sxs-lookup"><span data-stu-id="ff14d-127">CorRuntimeHost Coclass</span></span>](corruntimehost-coclass.md)
