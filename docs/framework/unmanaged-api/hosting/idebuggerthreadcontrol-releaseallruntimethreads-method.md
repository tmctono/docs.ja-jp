---
title: IDebuggerThreadControl::ReleaseAllRuntimeThreads メソッド
ms.date: 03/30/2017
api_name:
- IDebuggerThreadControl.ReleaseAllRuntimeThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ReleaseAllRuntimeThreads
helpviewer_keywords:
- ReleaseAllRuntimeThreads method [.NET Framework hosting]
- IDebuggerThreadControl::ReleaseAllRuntimeThreads method [.NET Framework hosting]
ms.assetid: 1a2995ff-5f02-4b49-84dc-3a5f9cfd7d55
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 136dab5c05c310d85a5e18bcdc6da0de901d3ace
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61699865"
---
# <a name="idebuggerthreadcontrolreleaseallruntimethreads-method"></a><span data-ttu-id="59a48-102">IDebuggerThreadControl::ReleaseAllRuntimeThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="59a48-102">IDebuggerThreadControl::ReleaseAllRuntimeThreads Method</span></span>
<span data-ttu-id="59a48-103">デバッグ サービスがブロックされているすべてのスレッドを解放しようとしていることをホストに通知します。</span><span class="sxs-lookup"><span data-stu-id="59a48-103">Notifies the host that the debugging services are about to release all threads that are blocked.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59a48-104">構文</span><span class="sxs-lookup"><span data-stu-id="59a48-104">Syntax</span></span>  
  
```  
HRESULT ReleaseAllRuntimeThreads ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="59a48-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="59a48-105">Remarks</span></span>  
 <span data-ttu-id="59a48-106">`ReleaseAllRuntimeThreads`メソッドはランタイムのスレッドで呼び出されません。</span><span class="sxs-lookup"><span data-stu-id="59a48-106">The `ReleaseAllRuntimeThreads` method will never be called on a runtime thread.</span></span> <span data-ttu-id="59a48-107">ホストにブロックされているランタイムのスレッドがある場合は、今すぐリリースにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="59a48-107">If the host has a runtime thread blocked, it should release it now.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="59a48-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="59a48-108">Requirements</span></span>  
 <span data-ttu-id="59a48-109">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="59a48-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="59a48-110">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="59a48-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="59a48-111">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="59a48-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="59a48-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="59a48-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59a48-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="59a48-113">See also</span></span>

- [<span data-ttu-id="59a48-114">IDebuggerThreadControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="59a48-114">IDebuggerThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)
