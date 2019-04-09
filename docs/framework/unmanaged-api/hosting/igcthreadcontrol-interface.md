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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5c00f401bedc1a2810c4e9b3046a45e53a79f1ea
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59134265"
---
# <a name="igcthreadcontrol-interface"></a><span data-ttu-id="b4d98-102">IGCThreadControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b4d98-102">IGCThreadControl Interface</span></span>
<span data-ttu-id="b4d98-103">それ以外の場合、ガベージ コレクションのブロックされるスレッドのスケジューリングに参加するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="b4d98-103">Provides methods for participating in the scheduling of threads that would otherwise be blocked for a garbage collection.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b4d98-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="b4d98-104">Methods</span></span>  
  
|<span data-ttu-id="b4d98-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="b4d98-105">Method</span></span>|<span data-ttu-id="b4d98-106">説明</span><span class="sxs-lookup"><span data-stu-id="b4d98-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b4d98-107">SuspensionEnding メソッド</span><span class="sxs-lookup"><span data-stu-id="b4d98-107">SuspensionEnding Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-suspensionending-method.md)|<span data-ttu-id="b4d98-108">ランタイムがガベージ コレクションまたはその他の中断の後のスレッドを再開することをホストに通知します。</span><span class="sxs-lookup"><span data-stu-id="b4d98-108">Notifies the host that the runtime is resuming threads after a garbage collection or other suspension.</span></span>|  
|[<span data-ttu-id="b4d98-109">SuspensionStarting メソッド</span><span class="sxs-lookup"><span data-stu-id="b4d98-109">SuspensionStarting Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-suspensionstarting-method.md)|<span data-ttu-id="b4d98-110">ランタイムがガベージ コレクションのスレッドの中断またはその他の中断を開始していることをホストに通知します。</span><span class="sxs-lookup"><span data-stu-id="b4d98-110">Notifies the host that the runtime is beginning a thread suspension for a garbage collection or other suspension.</span></span>|  
|[<span data-ttu-id="b4d98-111">ThreadIsBlockingForSuspension メソッド</span><span class="sxs-lookup"><span data-stu-id="b4d98-111">ThreadIsBlockingForSuspension Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-threadisblockingforsuspension-method.md)|<span data-ttu-id="b4d98-112">ガベージ コレクションまたはその他の中断のためにブロックする直前の呼び出しを行っているスレッドが、ホストに通知します。</span><span class="sxs-lookup"><span data-stu-id="b4d98-112">Notifies the host that the thread making the call is about to block, perhaps for a garbage collection or other suspension.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b4d98-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="b4d98-113">Requirements</span></span>  
 <span data-ttu-id="b4d98-114">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b4d98-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4d98-115">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b4d98-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b4d98-116">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="b4d98-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="b4d98-117">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="b4d98-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b4d98-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="b4d98-118">See also</span></span>

- [<span data-ttu-id="b4d98-119">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b4d98-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
