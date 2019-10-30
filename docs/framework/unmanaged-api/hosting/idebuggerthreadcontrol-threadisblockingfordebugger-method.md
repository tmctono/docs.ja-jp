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
ms.openlocfilehash: 067d4e844055206543e5c7fb409296b0d0a7a549
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134937"
---
# <a name="idebuggerthreadcontrolthreadisblockingfordebugger-method"></a><span data-ttu-id="315a0-102">IDebuggerThreadControl::ThreadIsBlockingForDebugger メソッド</span><span class="sxs-lookup"><span data-stu-id="315a0-102">IDebuggerThreadControl::ThreadIsBlockingForDebugger Method</span></span>
<span data-ttu-id="315a0-103">このコールバックを送信しているスレッドがデバッグサービス内でブロックされようとしていることをホストに通知します。</span><span class="sxs-lookup"><span data-stu-id="315a0-103">Notifies the host that the thread that is sending this callback is about to block within the debugging services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="315a0-104">構文</span><span class="sxs-lookup"><span data-stu-id="315a0-104">Syntax</span></span>  
  
```cpp  
HRESULT ThreadIsBlockingForDebugger ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="315a0-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="315a0-105">Remarks</span></span>  
 <span data-ttu-id="315a0-106">`ThreadIsBlockingForDebugger` メソッドは常にランタイムスレッドで呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="315a0-106">The `ThreadIsBlockingForDebugger` method will always be called on a runtime thread.</span></span>  
  
 <span data-ttu-id="315a0-107">`ThreadIsBlockingForDebugger` メソッドは、スレッドがブロックされている間に、ホストに別のアクションを実行する機会を与えます。</span><span class="sxs-lookup"><span data-stu-id="315a0-107">The `ThreadIsBlockingForDebugger` method gives the host an opportunity to perform another action while the thread blocks.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="315a0-108">［要件］</span><span class="sxs-lookup"><span data-stu-id="315a0-108">Requirements</span></span>  
 <span data-ttu-id="315a0-109">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="315a0-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="315a0-110">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="315a0-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="315a0-111">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="315a0-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="315a0-112">**.Net Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="315a0-112">**NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="315a0-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="315a0-113">See also</span></span>

- [<span data-ttu-id="315a0-114">IDebuggerThreadControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="315a0-114">IDebuggerThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)
