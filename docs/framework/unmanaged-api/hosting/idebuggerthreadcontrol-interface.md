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
ms.openlocfilehash: 82c6113f4df3334500128df22f7e9ce8d4bf151f
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/22/2020
ms.locfileid: "83805287"
---
# <a name="idebuggerthreadcontrol-interface"></a><span data-ttu-id="9ac89-102">IDebuggerThreadControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9ac89-102">IDebuggerThreadControl Interface</span></span>
<span data-ttu-id="9ac89-103">デバッグサービスによるスレッドのブロックおよびブロック解除についてホストに通知するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="9ac89-103">Provides methods for notifying the host about the blocking and unblocking of threads by the debugging services.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9ac89-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="9ac89-104">Methods</span></span>  
  
|<span data-ttu-id="9ac89-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="9ac89-105">Method</span></span>|<span data-ttu-id="9ac89-106">説明</span><span class="sxs-lookup"><span data-stu-id="9ac89-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9ac89-107">ThreadIsBlockingForDebugger メソッド</span><span class="sxs-lookup"><span data-stu-id="9ac89-107">ThreadIsBlockingForDebugger Method</span></span>](idebuggerthreadcontrol-threadisblockingfordebugger-method.md)|<span data-ttu-id="9ac89-108">このコールバックを送信しているスレッドがデバッグサービス内でブロックされようとしていることをホストに通知します。</span><span class="sxs-lookup"><span data-stu-id="9ac89-108">Notifies the host that the thread that is sending this callback is about to block within the debugging services.</span></span>|  
|[<span data-ttu-id="9ac89-109">ReleaseAllRuntimeThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="9ac89-109">ReleaseAllRuntimeThreads Method</span></span>](idebuggerthreadcontrol-releaseallruntimethreads-method.md)|<span data-ttu-id="9ac89-110">デバッグサービスがブロックされているすべてのスレッドを解放しようとしていることをホストに通知します。</span><span class="sxs-lookup"><span data-stu-id="9ac89-110">Notifies the host that the debugging services are about to release all threads that are blocked.</span></span>|  
|[<span data-ttu-id="9ac89-111">StartBlockingForDebugger メソッド</span><span class="sxs-lookup"><span data-stu-id="9ac89-111">StartBlockingForDebugger Method</span></span>](idebuggerthreadcontrol-startblockingfordebugger-method.md)|<span data-ttu-id="9ac89-112">デバッグサービスがすべてのスレッドのブロックを開始しようとしていることをホストに通知します。</span><span class="sxs-lookup"><span data-stu-id="9ac89-112">Notifies the host that the debugging services are about to start blocking all threads.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9ac89-113">要件</span><span class="sxs-lookup"><span data-stu-id="9ac89-113">Requirements</span></span>  
 <span data-ttu-id="9ac89-114">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9ac89-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ac89-115">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="9ac89-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9ac89-116">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="9ac89-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9ac89-117">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ac89-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ac89-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="9ac89-118">See also</span></span>

- [<span data-ttu-id="9ac89-119">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9ac89-119">Hosting Interfaces</span></span>](hosting-interfaces.md)
