---
title: IHostAutoEvent インターフェイス
ms.date: 03/30/2017
api_name:
- IHostAutoEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAutoEvent
helpviewer_keywords:
- IHostAutoEvent interface [.NET Framework hosting]
ms.assetid: 6c1d15c1-a80a-4ee9-b1e4-6e859db6575a
topic_type:
- apiref
ms.openlocfilehash: 2b191243ea03adcfecaadbd3a5871e1773b28bb1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124461"
---
# <a name="ihostautoevent-interface"></a><span data-ttu-id="8c4a3-102">IHostAutoEvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8c4a3-102">IHostAutoEvent Interface</span></span>
<span data-ttu-id="8c4a3-103">自動リセットイベントのホストの実装の表現を提供します。</span><span class="sxs-lookup"><span data-stu-id="8c4a3-103">Provides a representation of the host's implementation of an auto-reset event.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8c4a3-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="8c4a3-104">Methods</span></span>  
  
|<span data-ttu-id="8c4a3-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="8c4a3-105">Method</span></span>|<span data-ttu-id="8c4a3-106">説明</span><span class="sxs-lookup"><span data-stu-id="8c4a3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8c4a3-107">Set メソッド</span><span class="sxs-lookup"><span data-stu-id="8c4a3-107">Set Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-set-method.md)|<span data-ttu-id="8c4a3-108">現在の `IHostAutoEvent` インスタンスをシグナル状態に設定します。</span><span class="sxs-lookup"><span data-stu-id="8c4a3-108">Sets the current `IHostAutoEvent` instance to a signaled state.</span></span>|  
|[<span data-ttu-id="8c4a3-109">Wait メソッド</span><span class="sxs-lookup"><span data-stu-id="8c4a3-109">Wait Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-wait-method.md)|<span data-ttu-id="8c4a3-110">イベントが所有されるか、指定した時間が経過するまで、現在の `IHostAutoEvent` インスタンスを待機させます。</span><span class="sxs-lookup"><span data-stu-id="8c4a3-110">Causes the current `IHostAutoEvent` instance to wait until the event is owned or a specified amount of time elapses.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8c4a3-111">［要件］</span><span class="sxs-lookup"><span data-stu-id="8c4a3-111">Requirements</span></span>  
 <span data-ttu-id="8c4a3-112">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8c4a3-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c4a3-113">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="8c4a3-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8c4a3-114">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="8c4a3-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8c4a3-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8c4a3-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c4a3-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="8c4a3-116">See also</span></span>

- [<span data-ttu-id="8c4a3-117">ICLRSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8c4a3-117">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="8c4a3-118">IHostManualEvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8c4a3-118">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="8c4a3-119">IHostSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8c4a3-119">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
- [<span data-ttu-id="8c4a3-120">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8c4a3-120">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
