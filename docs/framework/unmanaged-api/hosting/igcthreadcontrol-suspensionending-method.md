---
title: IGCThreadControl::SuspensionEnding メソッド
ms.date: 03/30/2017
api_name:
- IGCThreadControl.SuspensionEnding
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SuspensionEnding
helpviewer_keywords:
- IGCThreadControl::SuspensionEnding method [.NET Framework hosting]
- SuspensionEnding method, IGCThreadControl interface [.NET Framework hosting]
ms.assetid: 70814265-c734-4ddc-9502-fe8b28d2b414
topic_type:
- apiref
ms.openlocfilehash: 8300daf0d39745ceda80f6c56da7e3c459a97468
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/22/2020
ms.locfileid: "83805116"
---
# <a name="igcthreadcontrolsuspensionending-method"></a><span data-ttu-id="210af-102">IGCThreadControl::SuspensionEnding メソッド</span><span class="sxs-lookup"><span data-stu-id="210af-102">IGCThreadControl::SuspensionEnding Method</span></span>
<span data-ttu-id="210af-103">ランタイムがガベージコレクションまたはその他の中断後にスレッドを再開していることをホストに通知します。</span><span class="sxs-lookup"><span data-stu-id="210af-103">Notifies the host that the runtime is resuming threads after a garbage collection or other suspension.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="210af-104">構文</span><span class="sxs-lookup"><span data-stu-id="210af-104">Syntax</span></span>  
  
```cpp  
HRESULT SuspensionEnding (  
    [in] DWORD Generation  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="210af-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="210af-105">Parameters</span></span>  
 `Generation`  
 <span data-ttu-id="210af-106">からガベージコレクションが実行された生成。</span><span class="sxs-lookup"><span data-stu-id="210af-106">[in] The generation on which a garbage collection has been performed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="210af-107">解説</span><span class="sxs-lookup"><span data-stu-id="210af-107">Remarks</span></span>  
 <span data-ttu-id="210af-108">コールバック中にスレッドを再スケジュールしないでください `SuspensionEnding` 。</span><span class="sxs-lookup"><span data-stu-id="210af-108">Do not reschedule any threads during the `SuspensionEnding` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="210af-109">要件</span><span class="sxs-lookup"><span data-stu-id="210af-109">Requirements</span></span>  
 <span data-ttu-id="210af-110">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="210af-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="210af-111">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="210af-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="210af-112">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="210af-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="210af-113">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="210af-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="210af-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="210af-114">See also</span></span>

- [<span data-ttu-id="210af-115">IGCThreadControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="210af-115">IGCThreadControl Interface</span></span>](igcthreadcontrol-interface.md)
