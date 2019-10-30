---
title: IGCThreadControl::SuspensionStarting メソッド
ms.date: 03/30/2017
api_name:
- IGCThreadControl.SuspensionStarting
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SuspensionStarting
helpviewer_keywords:
- IGCThreadControl::SuspensionStarting method [.NET Framework hosting]
- SuspensionStarting method, IGCThreadControl interface [.NET Framework hosting]
ms.assetid: 0af312af-98e9-415e-b182-42e80a1aee51
topic_type:
- apiref
ms.openlocfilehash: 1e1d63ab28276f69e5b3a762520db8f8300d05bc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134758"
---
# <a name="igcthreadcontrolsuspensionstarting-method"></a><span data-ttu-id="6aa05-102">IGCThreadControl::SuspensionStarting メソッド</span><span class="sxs-lookup"><span data-stu-id="6aa05-102">IGCThreadControl::SuspensionStarting Method</span></span>
<span data-ttu-id="6aa05-103">ランタイムがガベージコレクションまたは他の中断のためにスレッドの中断を開始していることをホストに通知します。</span><span class="sxs-lookup"><span data-stu-id="6aa05-103">Notifies the host that the runtime is beginning a thread suspension for a garbage collection or other suspension.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6aa05-104">構文</span><span class="sxs-lookup"><span data-stu-id="6aa05-104">Syntax</span></span>  
  
```cpp  
HRESULT SuspensionStarting ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="6aa05-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="6aa05-105">Remarks</span></span>  
 <span data-ttu-id="6aa05-106">`SuspensionStarting` コールバック中にスレッドを再スケジュールしないでください。</span><span class="sxs-lookup"><span data-stu-id="6aa05-106">Do not reschedule any threads during the `SuspensionStarting` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6aa05-107">［要件］</span><span class="sxs-lookup"><span data-stu-id="6aa05-107">Requirements</span></span>  
 <span data-ttu-id="6aa05-108">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6aa05-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6aa05-109">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="6aa05-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6aa05-110">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="6aa05-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6aa05-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6aa05-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6aa05-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="6aa05-112">See also</span></span>

- [<span data-ttu-id="6aa05-113">IGCThreadControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6aa05-113">IGCThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md)
