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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1cb314f2afce0cbbf1c5fb185f516a30ad8313af
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780518"
---
# <a name="idebuggerthreadcontrolstartblockingfordebugger-method"></a><span data-ttu-id="77755-102">IDebuggerThreadControl::StartBlockingForDebugger メソッド</span><span class="sxs-lookup"><span data-stu-id="77755-102">IDebuggerThreadControl::StartBlockingForDebugger Method</span></span>
<span data-ttu-id="77755-103">デバッグ サービスがすべてのスレッドのブロックを開始しようとしていることをホストに通知します。</span><span class="sxs-lookup"><span data-stu-id="77755-103">Notifies the host that the debugging services are about to start blocking all threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77755-104">構文</span><span class="sxs-lookup"><span data-stu-id="77755-104">Syntax</span></span>  
  
```cpp  
HRESULT StartBlockingForDebugger (  
    [in] DWORD dwUnused  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="77755-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="77755-105">Parameters</span></span>  
 `dwUnused`  
 <span data-ttu-id="77755-106">[in]将来使用するために予約されています。</span><span class="sxs-lookup"><span data-stu-id="77755-106">[in] Reserved for future use.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="77755-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="77755-107">Remarks</span></span>  
 <span data-ttu-id="77755-108">`StartBlockingForDebugger`ランタイムのスレッドでメソッドを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="77755-108">The `StartBlockingForDebugger` method could be called on a runtime thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="77755-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="77755-109">Requirements</span></span>  
 <span data-ttu-id="77755-110">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="77755-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77755-111">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="77755-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="77755-112">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="77755-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="77755-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77755-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77755-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="77755-114">See also</span></span>

- [<span data-ttu-id="77755-115">IDebuggerThreadControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="77755-115">IDebuggerThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)
