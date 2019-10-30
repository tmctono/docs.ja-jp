---
title: IDebuggerThreadControl インターフェイス
ms.date: 03/30/2017
api_name:
- IDebuggerThreadControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IDebuggerThreadControl
helpviewer_keywords:
- IDebuggerThreadControl interface [.NET Framework hosting]
ms.assetid: 0a270c42-a7d1-45f1-a64d-fa3e84d14532
topic_type:
- apiref
ms.openlocfilehash: a65f9f0f29a43cf3d26b4b2bc5f6f594f0557009
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133159"
---
# <a name="idebuggerthreadcontrol-interface"></a><span data-ttu-id="5b05d-102">IDebuggerThreadControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5b05d-102">IDebuggerThreadControl Interface</span></span>
<span data-ttu-id="5b05d-103">デバッグサービスによるスレッドのブロックおよびブロック解除についてホストに通知するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="5b05d-103">Provides methods for notifying the host about the blocking and unblocking of threads by the debugging services.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5b05d-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="5b05d-104">Methods</span></span>  
  
|<span data-ttu-id="5b05d-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="5b05d-105">Method</span></span>|<span data-ttu-id="5b05d-106">説明</span><span class="sxs-lookup"><span data-stu-id="5b05d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5b05d-107">ThreadIsBlockingForDebugger メソッド</span><span class="sxs-lookup"><span data-stu-id="5b05d-107">ThreadIsBlockingForDebugger Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-threadisblockingfordebugger-method.md)|<span data-ttu-id="5b05d-108">このコールバックを送信しているスレッドがデバッグサービス内でブロックされようとしていることをホストに通知します。</span><span class="sxs-lookup"><span data-stu-id="5b05d-108">Notifies the host that the thread that is sending this callback is about to block within the debugging services.</span></span>|  
|[<span data-ttu-id="5b05d-109">ReleaseAllRuntimeThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="5b05d-109">ReleaseAllRuntimeThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-releaseallruntimethreads-method.md)|<span data-ttu-id="5b05d-110">デバッグサービスがブロックされているすべてのスレッドを解放しようとしていることをホストに通知します。</span><span class="sxs-lookup"><span data-stu-id="5b05d-110">Notifies the host that the debugging services are about to release all threads that are blocked.</span></span>|  
|[<span data-ttu-id="5b05d-111">StartBlockingForDebugger メソッド</span><span class="sxs-lookup"><span data-stu-id="5b05d-111">StartBlockingForDebugger Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-startblockingfordebugger-method.md)|<span data-ttu-id="5b05d-112">デバッグサービスがすべてのスレッドのブロックを開始しようとしていることをホストに通知します。</span><span class="sxs-lookup"><span data-stu-id="5b05d-112">Notifies the host that the debugging services are about to start blocking all threads.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5b05d-113">［要件］</span><span class="sxs-lookup"><span data-stu-id="5b05d-113">Requirements</span></span>  
 <span data-ttu-id="5b05d-114">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5b05d-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b05d-115">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="5b05d-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5b05d-116">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="5b05d-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5b05d-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b05d-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b05d-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="5b05d-118">See also</span></span>

- [<span data-ttu-id="5b05d-119">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5b05d-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
