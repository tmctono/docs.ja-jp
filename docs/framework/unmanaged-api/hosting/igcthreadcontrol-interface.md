---
title: IGCThreadControl インターフェイス
ms.date: 03/30/2017
api_name:
- IGCThreadControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IGCThreadControl
helpviewer_keywords:
- IGCThreadControl interface [.NET Framework hosting]
ms.assetid: 3ff04d75-85ac-4df9-886d-dbaa037c0552
topic_type:
- apiref
ms.openlocfilehash: 3aba31f60af25144b9f01aa9ca8cc633d4c1a438
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134799"
---
# <a name="igcthreadcontrol-interface"></a><span data-ttu-id="b7e06-102">IGCThreadControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b7e06-102">IGCThreadControl Interface</span></span>
<span data-ttu-id="b7e06-103">ガベージコレクションに対してブロックされるスレッドのスケジュール設定に参加するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="b7e06-103">Provides methods for participating in the scheduling of threads that would otherwise be blocked for a garbage collection.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b7e06-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="b7e06-104">Methods</span></span>  
  
|<span data-ttu-id="b7e06-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="b7e06-105">Method</span></span>|<span data-ttu-id="b7e06-106">説明</span><span class="sxs-lookup"><span data-stu-id="b7e06-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b7e06-107">SuspensionEnding メソッド</span><span class="sxs-lookup"><span data-stu-id="b7e06-107">SuspensionEnding Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-suspensionending-method.md)|<span data-ttu-id="b7e06-108">ランタイムがガベージコレクションまたはその他の中断後にスレッドを再開していることをホストに通知します。</span><span class="sxs-lookup"><span data-stu-id="b7e06-108">Notifies the host that the runtime is resuming threads after a garbage collection or other suspension.</span></span>|  
|[<span data-ttu-id="b7e06-109">SuspensionStarting メソッド</span><span class="sxs-lookup"><span data-stu-id="b7e06-109">SuspensionStarting Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-suspensionstarting-method.md)|<span data-ttu-id="b7e06-110">ランタイムがガベージコレクションまたは他の中断のためにスレッドの中断を開始していることをホストに通知します。</span><span class="sxs-lookup"><span data-stu-id="b7e06-110">Notifies the host that the runtime is beginning a thread suspension for a garbage collection or other suspension.</span></span>|  
|[<span data-ttu-id="b7e06-111">ThreadIsBlockingForSuspension メソッド</span><span class="sxs-lookup"><span data-stu-id="b7e06-111">ThreadIsBlockingForSuspension Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-threadisblockingforsuspension-method.md)|<span data-ttu-id="b7e06-112">呼び出しを行っているスレッドがブロックしようとしていることをホストに通知します。ガベージコレクションやその他の中断が考えられます。</span><span class="sxs-lookup"><span data-stu-id="b7e06-112">Notifies the host that the thread making the call is about to block, perhaps for a garbage collection or other suspension.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b7e06-113">［要件］</span><span class="sxs-lookup"><span data-stu-id="b7e06-113">Requirements</span></span>  
 <span data-ttu-id="b7e06-114">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b7e06-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7e06-115">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="b7e06-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b7e06-116">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="b7e06-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b7e06-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7e06-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7e06-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="b7e06-118">See also</span></span>

- [<span data-ttu-id="b7e06-119">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b7e06-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
