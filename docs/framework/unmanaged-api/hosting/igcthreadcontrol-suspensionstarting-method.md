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
ms.openlocfilehash: 2acabe66e3b6b5652df20e31a9d2294c2396b54b
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/22/2020
ms.locfileid: "83805094"
---
# <a name="igcthreadcontrolsuspensionstarting-method"></a><span data-ttu-id="42fe1-102">IGCThreadControl::SuspensionStarting メソッド</span><span class="sxs-lookup"><span data-stu-id="42fe1-102">IGCThreadControl::SuspensionStarting Method</span></span>
<span data-ttu-id="42fe1-103">ランタイムがガベージコレクションまたは他の中断のためにスレッドの中断を開始していることをホストに通知します。</span><span class="sxs-lookup"><span data-stu-id="42fe1-103">Notifies the host that the runtime is beginning a thread suspension for a garbage collection or other suspension.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42fe1-104">構文</span><span class="sxs-lookup"><span data-stu-id="42fe1-104">Syntax</span></span>  
  
```cpp  
HRESULT SuspensionStarting ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="42fe1-105">解説</span><span class="sxs-lookup"><span data-stu-id="42fe1-105">Remarks</span></span>  
 <span data-ttu-id="42fe1-106">コールバック中にスレッドを再スケジュールしないでください `SuspensionStarting` 。</span><span class="sxs-lookup"><span data-stu-id="42fe1-106">Do not reschedule any threads during the `SuspensionStarting` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42fe1-107">要件</span><span class="sxs-lookup"><span data-stu-id="42fe1-107">Requirements</span></span>  
 <span data-ttu-id="42fe1-108">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="42fe1-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42fe1-109">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="42fe1-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="42fe1-110">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="42fe1-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="42fe1-111">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42fe1-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42fe1-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="42fe1-112">See also</span></span>

- [<span data-ttu-id="42fe1-113">IGCThreadControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="42fe1-113">IGCThreadControl Interface</span></span>](igcthreadcontrol-interface.md)
