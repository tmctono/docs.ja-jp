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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61948552"
---
# <a name="iclrmemorynotificationcallback-interface"></a><span data-ttu-id="c2585-102">ICLRMemoryNotificationCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c2585-102">ICLRMemoryNotificationCallback Interface</span></span>
<span data-ttu-id="c2585-103">ホストが、Win32 のと同様の手法を使用してメモリ不足の状態を報告できるように`CreateMemoryResourceNotification`関数。</span><span class="sxs-lookup"><span data-stu-id="c2585-103">Allows the host to report memory pressure conditions using an approach similar to that of the Win32 `CreateMemoryResourceNotification` function.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c2585-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="c2585-104">Methods</span></span>  
  
|<span data-ttu-id="c2585-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="c2585-105">Method</span></span>|<span data-ttu-id="c2585-106">説明</span><span class="sxs-lookup"><span data-stu-id="c2585-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c2585-107">OnMemoryNotification メソッド</span><span class="sxs-lookup"><span data-stu-id="c2585-107">OnMemoryNotification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md)|<span data-ttu-id="c2585-108">コンピューターのメモリ負荷の共通言語ランタイム (CLR) に通知します。</span><span class="sxs-lookup"><span data-stu-id="c2585-108">Notifies the common language runtime (CLR) of the memory load on the computer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c2585-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="c2585-109">Remarks</span></span>  
 <span data-ttu-id="c2585-110">ホストが使用して、 `ICLRMemoryNotificationCallback` CLR がメモリ リソースを解放することを要求するインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="c2585-110">The host uses the `ICLRMemoryNotificationCallback` interface to request that the CLR free memory resources.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2585-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="c2585-111">Requirements</span></span>  
 <span data-ttu-id="c2585-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2585-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2585-113">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c2585-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c2585-114">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="c2585-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c2585-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2585-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2585-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="c2585-116">See also</span></span>

- [<span data-ttu-id="c2585-117">IHostMemoryManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c2585-117">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="c2585-118">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c2585-118">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
