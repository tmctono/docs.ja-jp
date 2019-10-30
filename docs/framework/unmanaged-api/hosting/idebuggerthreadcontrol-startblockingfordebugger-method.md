---
title: IDebuggerThreadControl::StartBlockingForDebugger メソッド
ms.date: 03/30/2017
api_name:
- IDebuggerThreadControl.StartBlockingForDebugger
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- StartBlockingForDebugger
helpviewer_keywords:
- IDebuggerThreadControl::StartBlockingForDebugger method [.NET Framework hosting]
- StartBlockingForDebugger method [.NET Framework hosting]
ms.assetid: 5c8f11b4-35d3-4c39-9bbd-58b896ba5ba6
topic_type:
- apiref
ms.openlocfilehash: 72f7bee79e74c69acff90861ceada8a91afe2157
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134912"
---
# <a name="idebuggerthreadcontrolstartblockingfordebugger-method"></a><span data-ttu-id="f3645-102">IDebuggerThreadControl::StartBlockingForDebugger メソッド</span><span class="sxs-lookup"><span data-stu-id="f3645-102">IDebuggerThreadControl::StartBlockingForDebugger Method</span></span>
<span data-ttu-id="f3645-103">デバッグサービスがすべてのスレッドのブロックを開始しようとしていることをホストに通知します。</span><span class="sxs-lookup"><span data-stu-id="f3645-103">Notifies the host that the debugging services are about to start blocking all threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3645-104">構文</span><span class="sxs-lookup"><span data-stu-id="f3645-104">Syntax</span></span>  
  
```cpp  
HRESULT StartBlockingForDebugger (  
    [in] DWORD dwUnused  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f3645-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f3645-105">Parameters</span></span>  
 `dwUnused`  
 <span data-ttu-id="f3645-106">から将来使用するために予約されています。</span><span class="sxs-lookup"><span data-stu-id="f3645-106">[in] Reserved for future use.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f3645-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="f3645-107">Remarks</span></span>  
 <span data-ttu-id="f3645-108">ランタイムスレッドで `StartBlockingForDebugger` メソッドを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="f3645-108">The `StartBlockingForDebugger` method could be called on a runtime thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f3645-109">［要件］</span><span class="sxs-lookup"><span data-stu-id="f3645-109">Requirements</span></span>  
 <span data-ttu-id="f3645-110">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3645-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3645-111">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="f3645-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f3645-112">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="f3645-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f3645-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3645-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3645-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="f3645-114">See also</span></span>

- [<span data-ttu-id="f3645-115">IDebuggerThreadControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f3645-115">IDebuggerThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)
