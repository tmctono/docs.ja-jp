---
title: IHostGCManager インターフェイス
ms.date: 03/30/2017
api_name:
- IHostGCManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostGCManager
helpviewer_keywords:
- IHostGCManager interface [.NET Framework hosting]
ms.assetid: 820330a4-244c-4f67-ab5e-f24b0b3c2080
topic_type:
- apiref
ms.openlocfilehash: 428e4cf8997713b08e40d9376c34ae5eee8cfa32
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804854"
---
# <a name="ihostgcmanager-interface"></a><span data-ttu-id="1e7fc-102">IHostGCManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1e7fc-102">IHostGCManager Interface</span></span>
<span data-ttu-id="1e7fc-103">共通言語ランタイム (CLR) によって実装されるガベージコレクション機構でイベントのホストに通知するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="1e7fc-103">Provides methods that notify the host of events in the garbage collection mechanism implemented by the common language runtime (CLR).</span></span>  
  
## <a name="members"></a><span data-ttu-id="1e7fc-104">メンバー</span><span class="sxs-lookup"><span data-stu-id="1e7fc-104">Members</span></span>  
  
|<span data-ttu-id="1e7fc-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="1e7fc-105">Member</span></span>|<span data-ttu-id="1e7fc-106">説明</span><span class="sxs-lookup"><span data-stu-id="1e7fc-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1e7fc-107">SuspensionEnding メソッド</span><span class="sxs-lookup"><span data-stu-id="1e7fc-107">SuspensionEnding Method</span></span>](ihostgcmanager-suspensionending-method.md)|<span data-ttu-id="1e7fc-108">CLR がガベージコレクションのために中断されたスレッドでタスクの実行を再開していることをホストに通知します。</span><span class="sxs-lookup"><span data-stu-id="1e7fc-108">Notifies the host that the CLR is resuming execution of tasks on threads that had been suspended for a garbage collection.</span></span>|  
|[<span data-ttu-id="1e7fc-109">SuspensionStarting メソッド</span><span class="sxs-lookup"><span data-stu-id="1e7fc-109">SuspensionStarting Method</span></span>](ihostgcmanager-suspensionstarting-method.md)|<span data-ttu-id="1e7fc-110">ガベージコレクションを実行するために、CLR がタスクの実行を中断していることをホストに通知します。</span><span class="sxs-lookup"><span data-stu-id="1e7fc-110">Notifies the host that the CLR is suspending execution of tasks, to perform a garbage collection.</span></span>|  
|[<span data-ttu-id="1e7fc-111">ThreadIsBlockingForSuspension メソッド</span><span class="sxs-lookup"><span data-stu-id="1e7fc-111">ThreadIsBlockingForSuspension Method</span></span>](ihostgcmanager-threadisblockingforsuspension-method.md)|<span data-ttu-id="1e7fc-112">メソッド呼び出しが行われたスレッドがガベージコレクションに対してブロックされようとしていることをホストに通知します。</span><span class="sxs-lookup"><span data-stu-id="1e7fc-112">Notifies the host that the thread from which the method call was made is about to block for a garbage collection.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1e7fc-113">要件</span><span class="sxs-lookup"><span data-stu-id="1e7fc-113">Requirements</span></span>  
 <span data-ttu-id="1e7fc-114">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1e7fc-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1e7fc-115">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="1e7fc-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1e7fc-116">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="1e7fc-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1e7fc-117">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1e7fc-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e7fc-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="1e7fc-118">See also</span></span>

- [<span data-ttu-id="1e7fc-119">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1e7fc-119">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="1e7fc-120">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1e7fc-120">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="1e7fc-121">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1e7fc-121">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="1e7fc-122">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1e7fc-122">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="1e7fc-123">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1e7fc-123">Hosting Interfaces</span></span>](hosting-interfaces.md)
