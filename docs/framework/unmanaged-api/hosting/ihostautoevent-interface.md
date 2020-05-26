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
ms.openlocfilehash: a24939ac0b0808546ef3615fae4909c6c3cf8a2e
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804993"
---
# <a name="ihostautoevent-interface"></a><span data-ttu-id="11785-102">IHostAutoEvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="11785-102">IHostAutoEvent Interface</span></span>
<span data-ttu-id="11785-103">自動リセットイベントのホストの実装の表現を提供します。</span><span class="sxs-lookup"><span data-stu-id="11785-103">Provides a representation of the host's implementation of an auto-reset event.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="11785-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="11785-104">Methods</span></span>  
  
|<span data-ttu-id="11785-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="11785-105">Method</span></span>|<span data-ttu-id="11785-106">説明</span><span class="sxs-lookup"><span data-stu-id="11785-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="11785-107">Set メソッド</span><span class="sxs-lookup"><span data-stu-id="11785-107">Set Method</span></span>](ihostautoevent-set-method.md)|<span data-ttu-id="11785-108">現在の `IHostAutoEvent` インスタンスをシグナル状態に設定します。</span><span class="sxs-lookup"><span data-stu-id="11785-108">Sets the current `IHostAutoEvent` instance to a signaled state.</span></span>|  
|[<span data-ttu-id="11785-109">Wait メソッド</span><span class="sxs-lookup"><span data-stu-id="11785-109">Wait Method</span></span>](ihostautoevent-wait-method.md)|<span data-ttu-id="11785-110">`IHostAutoEvent`イベントが所有されるか、指定した時間が経過するまで、現在のインスタンスを待機させます。</span><span class="sxs-lookup"><span data-stu-id="11785-110">Causes the current `IHostAutoEvent` instance to wait until the event is owned or a specified amount of time elapses.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="11785-111">要件</span><span class="sxs-lookup"><span data-stu-id="11785-111">Requirements</span></span>  
 <span data-ttu-id="11785-112">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="11785-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11785-113">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="11785-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="11785-114">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="11785-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="11785-115">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11785-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11785-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="11785-116">See also</span></span>

- [<span data-ttu-id="11785-117">ICLRSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="11785-117">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="11785-118">IHostManualEvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="11785-118">IHostManualEvent Interface</span></span>](ihostmanualevent-interface.md)
- [<span data-ttu-id="11785-119">IHostSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="11785-119">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
- [<span data-ttu-id="11785-120">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="11785-120">Hosting Interfaces</span></span>](hosting-interfaces.md)
