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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61973065"
---
# <a name="ihostmanualevent-interface"></a><span data-ttu-id="d5f39-102">IHostManualEvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d5f39-102">IHostManualEvent Interface</span></span>
<span data-ttu-id="d5f39-103">手動リセット イベントの表現のホストの実装を提供します。</span><span class="sxs-lookup"><span data-stu-id="d5f39-103">Provides the host's implementation of a representation of a manual reset event.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d5f39-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="d5f39-104">Methods</span></span>  
  
|<span data-ttu-id="d5f39-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="d5f39-105">Method</span></span>|<span data-ttu-id="d5f39-106">説明</span><span class="sxs-lookup"><span data-stu-id="d5f39-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d5f39-107">Reset メソッド</span><span class="sxs-lookup"><span data-stu-id="d5f39-107">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-reset-method.md)|<span data-ttu-id="d5f39-108">現在のリセット`IHostManualEvent`インスタンスを非シグナル状態にします。</span><span class="sxs-lookup"><span data-stu-id="d5f39-108">Resets the current `IHostManualEvent` instance to a non-signaled state.</span></span>|  
|[<span data-ttu-id="d5f39-109">Set メソッド</span><span class="sxs-lookup"><span data-stu-id="d5f39-109">Set Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-set-method.md)|<span data-ttu-id="d5f39-110">現在の設定`IHostManualEvent`インスタンスがシグナル状態にします。</span><span class="sxs-lookup"><span data-stu-id="d5f39-110">Sets the current `IHostManualEvent` instance to a signaled state.</span></span>|  
|[<span data-ttu-id="d5f39-111">Wait メソッド</span><span class="sxs-lookup"><span data-stu-id="d5f39-111">Wait Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-wait-method.md)|<span data-ttu-id="d5f39-112">現在`IHostManualEvent`、所有者になるまで待機するインスタンスまたは一定の時間が経過するとします。</span><span class="sxs-lookup"><span data-stu-id="d5f39-112">Causes the current `IHostManualEvent` instance to wait until it is owned, or a specified amount of time elapses.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d5f39-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="d5f39-113">Requirements</span></span>  
 <span data-ttu-id="d5f39-114">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d5f39-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5f39-115">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d5f39-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d5f39-116">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="d5f39-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d5f39-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5f39-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5f39-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="d5f39-118">See also</span></span>

- [<span data-ttu-id="d5f39-119">ICLRSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d5f39-119">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="d5f39-120">IHostAutoEvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d5f39-120">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="d5f39-121">IHostSemaphore インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d5f39-121">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="d5f39-122">IHostSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d5f39-122">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
- [<span data-ttu-id="d5f39-123">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d5f39-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
