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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7a551d3cc6ab3dd3887f232018f8201de4036d1b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59096837"
---
# <a name="idebuggerthreadcontrol-interface"></a><span data-ttu-id="644c0-102">IDebuggerThreadControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="644c0-102">IDebuggerThreadControl Interface</span></span>
<span data-ttu-id="644c0-103">デバッグ サービスによるスレッドのブロックおよびブロックについて、ホストを通知するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="644c0-103">Provides methods for notifying the host about the blocking and unblocking of threads by the debugging services.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="644c0-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="644c0-104">Methods</span></span>  
  
|<span data-ttu-id="644c0-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="644c0-105">Method</span></span>|<span data-ttu-id="644c0-106">説明</span><span class="sxs-lookup"><span data-stu-id="644c0-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="644c0-107">ThreadIsBlockingForDebugger メソッド</span><span class="sxs-lookup"><span data-stu-id="644c0-107">ThreadIsBlockingForDebugger Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-threadisblockingfordebugger-method.md)|<span data-ttu-id="644c0-108">このコールバックを送信しているスレッドは、ホストに通知デバッグ サービス内でブロックします。</span><span class="sxs-lookup"><span data-stu-id="644c0-108">Notifies the host that the thread that is sending this callback is about to block within the debugging services.</span></span>|  
|[<span data-ttu-id="644c0-109">ReleaseAllRuntimeThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="644c0-109">ReleaseAllRuntimeThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-releaseallruntimethreads-method.md)|<span data-ttu-id="644c0-110">デバッグ サービスがブロックされているすべてのスレッドを解放しようとしていることをホストに通知します。</span><span class="sxs-lookup"><span data-stu-id="644c0-110">Notifies the host that the debugging services are about to release all threads that are blocked.</span></span>|  
|[<span data-ttu-id="644c0-111">StartBlockingForDebugger メソッド</span><span class="sxs-lookup"><span data-stu-id="644c0-111">StartBlockingForDebugger Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-startblockingfordebugger-method.md)|<span data-ttu-id="644c0-112">デバッグ サービスがすべてのスレッドのブロックを開始しようとしていることをホストに通知します。</span><span class="sxs-lookup"><span data-stu-id="644c0-112">Notifies the host that the debugging services are about to start blocking all threads.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="644c0-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="644c0-113">Requirements</span></span>  
 <span data-ttu-id="644c0-114">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="644c0-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="644c0-115">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="644c0-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="644c0-116">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="644c0-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="644c0-117">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="644c0-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="644c0-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="644c0-118">See also</span></span>

- [<span data-ttu-id="644c0-119">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="644c0-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
