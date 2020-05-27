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
ms.openlocfilehash: 50ffb33456f942a71089f9bc44daa07f6b77ab21
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/22/2020
ms.locfileid: "83805299"
---
# <a name="idebuggerthreadcontrolreleaseallruntimethreads-method"></a><span data-ttu-id="08997-102">IDebuggerThreadControl::ReleaseAllRuntimeThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="08997-102">IDebuggerThreadControl::ReleaseAllRuntimeThreads Method</span></span>
<span data-ttu-id="08997-103">デバッグサービスがブロックされているすべてのスレッドを解放しようとしていることをホストに通知します。</span><span class="sxs-lookup"><span data-stu-id="08997-103">Notifies the host that the debugging services are about to release all threads that are blocked.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08997-104">構文</span><span class="sxs-lookup"><span data-stu-id="08997-104">Syntax</span></span>  
  
```cpp  
HRESULT ReleaseAllRuntimeThreads ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="08997-105">解説</span><span class="sxs-lookup"><span data-stu-id="08997-105">Remarks</span></span>  
 <span data-ttu-id="08997-106">メソッドは、 `ReleaseAllRuntimeThreads` ランタイムスレッドでは呼び出されません。</span><span class="sxs-lookup"><span data-stu-id="08997-106">The `ReleaseAllRuntimeThreads` method will never be called on a runtime thread.</span></span> <span data-ttu-id="08997-107">ホストにランタイムスレッドがブロックされている場合は、この時点で解放する必要があります。</span><span class="sxs-lookup"><span data-stu-id="08997-107">If the host has a runtime thread blocked, it should release it now.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08997-108">要件</span><span class="sxs-lookup"><span data-stu-id="08997-108">Requirements</span></span>  
 <span data-ttu-id="08997-109">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="08997-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08997-110">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="08997-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="08997-111">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="08997-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="08997-112">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08997-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08997-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="08997-113">See also</span></span>

- [<span data-ttu-id="08997-114">IDebuggerThreadControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="08997-114">IDebuggerThreadControl Interface</span></span>](idebuggerthreadcontrol-interface.md)
