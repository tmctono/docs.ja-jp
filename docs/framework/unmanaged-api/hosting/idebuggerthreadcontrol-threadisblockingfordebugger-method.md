---
title: IDebuggerThreadControl::ThreadIsBlockingForDebugger メソッド
ms.date: 03/30/2017
api_name:
- IDebuggerThreadControl.ThreadIsBlockingForDebugger
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ThreadIsBlockingForDebugger
helpviewer_keywords:
- ThreadIsBlockingForDebugger method [.NET Framework hosting]
- IDebuggerThreadControl::ThreadIsBlockingForDebugger method [.NET Framework hosting]
ms.assetid: d4d7cb2d-69da-48b3-879a-1a8a68c9bfa8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 47ff178cc9ab798593848e56fc7bba8ac82ae295
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59154233"
---
# <a name="idebuggerthreadcontrolthreadisblockingfordebugger-method"></a><span data-ttu-id="c36ad-102">IDebuggerThreadControl::ThreadIsBlockingForDebugger メソッド</span><span class="sxs-lookup"><span data-stu-id="c36ad-102">IDebuggerThreadControl::ThreadIsBlockingForDebugger Method</span></span>
<span data-ttu-id="c36ad-103">このコールバックを送信しているスレッドは、ホストに通知デバッグ サービス内でブロックします。</span><span class="sxs-lookup"><span data-stu-id="c36ad-103">Notifies the host that the thread that is sending this callback is about to block within the debugging services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c36ad-104">構文</span><span class="sxs-lookup"><span data-stu-id="c36ad-104">Syntax</span></span>  
  
```  
HRESULT ThreadIsBlockingForDebugger ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="c36ad-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="c36ad-105">Remarks</span></span>  
 <span data-ttu-id="c36ad-106">`ThreadIsBlockingForDebugger`メソッドはランタイムのスレッドで常に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="c36ad-106">The `ThreadIsBlockingForDebugger` method will always be called on a runtime thread.</span></span>  
  
 <span data-ttu-id="c36ad-107">`ThreadIsBlockingForDebugger`メソッドに、ホスト、スレッドがブロックの中に別の操作を実行する機会が与えられます。</span><span class="sxs-lookup"><span data-stu-id="c36ad-107">The `ThreadIsBlockingForDebugger` method gives the host an opportunity to perform another action while the thread blocks.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c36ad-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="c36ad-108">Requirements</span></span>  
 <span data-ttu-id="c36ad-109">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c36ad-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c36ad-110">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c36ad-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c36ad-111">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="c36ad-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="c36ad-112">NET Framework のバージョン:</span><span class="sxs-lookup"><span data-stu-id="c36ad-112">NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c36ad-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="c36ad-113">See also</span></span>

- [<span data-ttu-id="c36ad-114">IDebuggerThreadControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c36ad-114">IDebuggerThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)
