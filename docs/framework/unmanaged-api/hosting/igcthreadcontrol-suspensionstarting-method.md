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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7cb58593a30b855c9fabf55a6ca0a50886dc371f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779490"
---
# <a name="igcthreadcontrolsuspensionstarting-method"></a><span data-ttu-id="45392-102">IGCThreadControl::SuspensionStarting メソッド</span><span class="sxs-lookup"><span data-stu-id="45392-102">IGCThreadControl::SuspensionStarting Method</span></span>
<span data-ttu-id="45392-103">ランタイムがガベージ コレクションのスレッドの中断またはその他の中断を開始していることをホストに通知します。</span><span class="sxs-lookup"><span data-stu-id="45392-103">Notifies the host that the runtime is beginning a thread suspension for a garbage collection or other suspension.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45392-104">構文</span><span class="sxs-lookup"><span data-stu-id="45392-104">Syntax</span></span>  
  
```cpp  
HRESULT SuspensionStarting ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="45392-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="45392-105">Remarks</span></span>  
 <span data-ttu-id="45392-106">中にすべてのスレッドを再スケジュールしないで、`SuspensionStarting`コールバック。</span><span class="sxs-lookup"><span data-stu-id="45392-106">Do not reschedule any threads during the `SuspensionStarting` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="45392-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="45392-107">Requirements</span></span>  
 <span data-ttu-id="45392-108">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="45392-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="45392-109">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="45392-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="45392-110">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="45392-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="45392-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="45392-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45392-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="45392-112">See also</span></span>

- [<span data-ttu-id="45392-113">IGCThreadControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="45392-113">IGCThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md)
