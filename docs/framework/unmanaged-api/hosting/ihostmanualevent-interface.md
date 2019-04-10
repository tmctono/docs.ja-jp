---
title: IHostManualEvent インターフェイス
ms.date: 03/30/2017
api_name:
- IHostManualEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostManualEvent
helpviewer_keywords:
- IHostManualEvent interface [.NET Framework hosting]
ms.assetid: 300c2661-b7d1-4c39-b080-9ebdef0fd523
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ad580f7cab81323e09a24dc12db39f223be3aeb4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59208632"
---
# <a name="ihostmanualevent-interface"></a><span data-ttu-id="9230c-102">IHostManualEvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9230c-102">IHostManualEvent Interface</span></span>
<span data-ttu-id="9230c-103">手動リセット イベントの表現のホストの実装を提供します。</span><span class="sxs-lookup"><span data-stu-id="9230c-103">Provides the host's implementation of a representation of a manual reset event.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9230c-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="9230c-104">Methods</span></span>  
  
|<span data-ttu-id="9230c-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="9230c-105">Method</span></span>|<span data-ttu-id="9230c-106">説明</span><span class="sxs-lookup"><span data-stu-id="9230c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9230c-107">Reset メソッド</span><span class="sxs-lookup"><span data-stu-id="9230c-107">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-reset-method.md)|<span data-ttu-id="9230c-108">現在のリセット`IHostManualEvent`インスタンスを非シグナル状態にします。</span><span class="sxs-lookup"><span data-stu-id="9230c-108">Resets the current `IHostManualEvent` instance to a non-signaled state.</span></span>|  
|[<span data-ttu-id="9230c-109">Set メソッド</span><span class="sxs-lookup"><span data-stu-id="9230c-109">Set Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-set-method.md)|<span data-ttu-id="9230c-110">現在の設定`IHostManualEvent`インスタンスがシグナル状態にします。</span><span class="sxs-lookup"><span data-stu-id="9230c-110">Sets the current `IHostManualEvent` instance to a signaled state.</span></span>|  
|[<span data-ttu-id="9230c-111">Wait メソッド</span><span class="sxs-lookup"><span data-stu-id="9230c-111">Wait Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-wait-method.md)|<span data-ttu-id="9230c-112">現在`IHostManualEvent`、所有者になるまで待機するインスタンスまたは一定の時間が経過するとします。</span><span class="sxs-lookup"><span data-stu-id="9230c-112">Causes the current `IHostManualEvent` instance to wait until it is owned, or a specified amount of time elapses.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9230c-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="9230c-113">Requirements</span></span>  
 <span data-ttu-id="9230c-114">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9230c-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9230c-115">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9230c-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9230c-116">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="9230c-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="9230c-117">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="9230c-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9230c-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="9230c-118">See also</span></span>

- [<span data-ttu-id="9230c-119">ICLRSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9230c-119">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="9230c-120">IHostAutoEvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9230c-120">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="9230c-121">IHostSemaphore インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9230c-121">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="9230c-122">IHostSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9230c-122">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
- [<span data-ttu-id="9230c-123">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9230c-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
