---
title: ICLRMemoryNotificationCallback インターフェイス
ms.date: 03/30/2017
api_name:
- ICLRMemoryNotificationCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMemoryNotificationCallback
helpviewer_keywords:
- ICLRMemoryNotificationCallback interface [.NET Framework hosting]
ms.assetid: 873639e2-4837-4568-83b3-4493e67e4174
topic_type:
- apiref
ms.openlocfilehash: e980356ad592e137df7d08dadd77431b0e295380
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141001"
---
# <a name="iclrmemorynotificationcallback-interface"></a><span data-ttu-id="96d42-102">ICLRMemoryNotificationCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="96d42-102">ICLRMemoryNotificationCallback Interface</span></span>
<span data-ttu-id="96d42-103">Win32 `CreateMemoryResourceNotification` 関数と同様の方法を使用して、ホストがメモリ不足状態を報告できるようにします。</span><span class="sxs-lookup"><span data-stu-id="96d42-103">Allows the host to report memory pressure conditions using an approach similar to that of the Win32 `CreateMemoryResourceNotification` function.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="96d42-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="96d42-104">Methods</span></span>  
  
|<span data-ttu-id="96d42-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="96d42-105">Method</span></span>|<span data-ttu-id="96d42-106">説明</span><span class="sxs-lookup"><span data-stu-id="96d42-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="96d42-107">OnMemoryNotification メソッド</span><span class="sxs-lookup"><span data-stu-id="96d42-107">OnMemoryNotification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md)|<span data-ttu-id="96d42-108">コンピューターのメモリ負荷の共通言語ランタイム (CLR) に通知します。</span><span class="sxs-lookup"><span data-stu-id="96d42-108">Notifies the common language runtime (CLR) of the memory load on the computer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="96d42-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="96d42-109">Remarks</span></span>  
 <span data-ttu-id="96d42-110">ホストは、`ICLRMemoryNotificationCallback` インターフェイスを使用して、CLR のメモリリソースを解放するように要求します。</span><span class="sxs-lookup"><span data-stu-id="96d42-110">The host uses the `ICLRMemoryNotificationCallback` interface to request that the CLR free memory resources.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="96d42-111">［要件］</span><span class="sxs-lookup"><span data-stu-id="96d42-111">Requirements</span></span>  
 <span data-ttu-id="96d42-112">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="96d42-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="96d42-113">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="96d42-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="96d42-114">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="96d42-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="96d42-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96d42-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96d42-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="96d42-116">See also</span></span>

- [<span data-ttu-id="96d42-117">IHostMemoryManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="96d42-117">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="96d42-118">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="96d42-118">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
