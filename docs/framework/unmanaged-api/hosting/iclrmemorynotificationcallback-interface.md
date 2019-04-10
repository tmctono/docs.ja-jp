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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c98ece9d60571034f3298f15897b10c4d8fb06f4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59212155"
---
# <a name="iclrmemorynotificationcallback-interface"></a><span data-ttu-id="76fc4-102">ICLRMemoryNotificationCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="76fc4-102">ICLRMemoryNotificationCallback Interface</span></span>
<span data-ttu-id="76fc4-103">ホストが、Win32 のと同様の手法を使用してメモリ不足の状態を報告できるように`CreateMemoryResourceNotification`関数。</span><span class="sxs-lookup"><span data-stu-id="76fc4-103">Allows the host to report memory pressure conditions using an approach similar to that of the Win32 `CreateMemoryResourceNotification` function.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="76fc4-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="76fc4-104">Methods</span></span>  
  
|<span data-ttu-id="76fc4-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="76fc4-105">Method</span></span>|<span data-ttu-id="76fc4-106">説明</span><span class="sxs-lookup"><span data-stu-id="76fc4-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="76fc4-107">OnMemoryNotification メソッド</span><span class="sxs-lookup"><span data-stu-id="76fc4-107">OnMemoryNotification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md)|<span data-ttu-id="76fc4-108">コンピューターのメモリ負荷の共通言語ランタイム (CLR) に通知します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-108">Notifies the common language runtime (CLR) of the memory load on the computer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="76fc4-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="76fc4-109">Remarks</span></span>  
 <span data-ttu-id="76fc4-110">ホストが使用して、 `ICLRMemoryNotificationCallback` CLR がメモリ リソースを解放することを要求するインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="76fc4-110">The host uses the `ICLRMemoryNotificationCallback` interface to request that the CLR free memory resources.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="76fc4-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="76fc4-111">Requirements</span></span>  
 <span data-ttu-id="76fc4-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="76fc4-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="76fc4-113">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="76fc4-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="76fc4-114">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="76fc4-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="76fc4-115">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="76fc4-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="76fc4-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="76fc4-116">See also</span></span>

- [<span data-ttu-id="76fc4-117">IHostMemoryManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="76fc4-117">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="76fc4-118">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="76fc4-118">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
