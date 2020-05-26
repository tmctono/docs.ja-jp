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
ms.openlocfilehash: 878dba37728734a777d2f95226b60bfbe9aae16a
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/22/2020
ms.locfileid: "83805264"
---
# <a name="idebuggerthreadcontrolstartblockingfordebugger-method"></a><span data-ttu-id="b8dd5-102">IDebuggerThreadControl::StartBlockingForDebugger メソッド</span><span class="sxs-lookup"><span data-stu-id="b8dd5-102">IDebuggerThreadControl::StartBlockingForDebugger Method</span></span>
<span data-ttu-id="b8dd5-103">デバッグサービスがすべてのスレッドのブロックを開始しようとしていることをホストに通知します。</span><span class="sxs-lookup"><span data-stu-id="b8dd5-103">Notifies the host that the debugging services are about to start blocking all threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8dd5-104">構文</span><span class="sxs-lookup"><span data-stu-id="b8dd5-104">Syntax</span></span>  
  
```cpp  
HRESULT StartBlockingForDebugger (  
    [in] DWORD dwUnused  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b8dd5-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b8dd5-105">Parameters</span></span>  
 `dwUnused`  
 <span data-ttu-id="b8dd5-106">から将来使用するために予約されています。</span><span class="sxs-lookup"><span data-stu-id="b8dd5-106">[in] Reserved for future use.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b8dd5-107">解説</span><span class="sxs-lookup"><span data-stu-id="b8dd5-107">Remarks</span></span>  
 <span data-ttu-id="b8dd5-108">`StartBlockingForDebugger`ランタイムスレッドでメソッドを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="b8dd5-108">The `StartBlockingForDebugger` method could be called on a runtime thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8dd5-109">要件</span><span class="sxs-lookup"><span data-stu-id="b8dd5-109">Requirements</span></span>  
 <span data-ttu-id="b8dd5-110">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b8dd5-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8dd5-111">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="b8dd5-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b8dd5-112">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="b8dd5-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b8dd5-113">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8dd5-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8dd5-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="b8dd5-114">See also</span></span>

- [<span data-ttu-id="b8dd5-115">IDebuggerThreadControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b8dd5-115">IDebuggerThreadControl Interface</span></span>](idebuggerthreadcontrol-interface.md)
