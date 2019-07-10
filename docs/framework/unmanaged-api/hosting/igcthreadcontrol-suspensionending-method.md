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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cc91ff0676fcec5d614f9d6fa4850eb2c81086b4
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779498"
---
# <a name="igcthreadcontrolsuspensionending-method"></a><span data-ttu-id="91ec9-102">IGCThreadControl::SuspensionEnding メソッド</span><span class="sxs-lookup"><span data-stu-id="91ec9-102">IGCThreadControl::SuspensionEnding Method</span></span>
<span data-ttu-id="91ec9-103">ランタイムがガベージ コレクションまたはその他の中断の後のスレッドを再開することをホストに通知します。</span><span class="sxs-lookup"><span data-stu-id="91ec9-103">Notifies the host that the runtime is resuming threads after a garbage collection or other suspension.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91ec9-104">構文</span><span class="sxs-lookup"><span data-stu-id="91ec9-104">Syntax</span></span>  
  
```cpp  
HRESULT SuspensionEnding (  
    [in] DWORD Generation  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="91ec9-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="91ec9-105">Parameters</span></span>  
 `Generation`  
 <span data-ttu-id="91ec9-106">[in]ガベージ コレクションが実行されて生成されます。</span><span class="sxs-lookup"><span data-stu-id="91ec9-106">[in] The generation on which a garbage collection has been performed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="91ec9-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="91ec9-107">Remarks</span></span>  
 <span data-ttu-id="91ec9-108">中にすべてのスレッドを再スケジュールしないで、`SuspensionEnding`コールバック。</span><span class="sxs-lookup"><span data-stu-id="91ec9-108">Do not reschedule any threads during the `SuspensionEnding` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="91ec9-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="91ec9-109">Requirements</span></span>  
 <span data-ttu-id="91ec9-110">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="91ec9-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="91ec9-111">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="91ec9-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="91ec9-112">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="91ec9-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="91ec9-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="91ec9-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91ec9-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="91ec9-114">See also</span></span>

- [<span data-ttu-id="91ec9-115">IGCThreadControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="91ec9-115">IGCThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md)
