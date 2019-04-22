---
title: IGCThreadControl::ThreadIsBlockingForSuspension メソッド
ms.date: 03/30/2017
api_name:
- IGCThreadControl.ThreadIsBlockingForSuspension
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ThreadIsBlockingForSuspension
helpviewer_keywords:
- IGCThreadControl::ThreadIsBlockingForSuspension method [.NET Framework hosting]
- ThreadIsBlockingForSuspension method [.NET Framework hosting]
ms.assetid: ed5b5b58-7db7-46b5-9e2c-278db7159cee
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7cd6c1dff30bce8857b9fb4092670667109932c3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59094085"
---
# <a name="igcthreadcontrolthreadisblockingforsuspension-method"></a><span data-ttu-id="0af58-102">IGCThreadControl::ThreadIsBlockingForSuspension メソッド</span><span class="sxs-lookup"><span data-stu-id="0af58-102">IGCThreadControl::ThreadIsBlockingForSuspension Method</span></span>
<span data-ttu-id="0af58-103">ガベージ コレクションまたはその他の中断のためにブロックするには、約呼び出しを行っているスレッドであることをホストに通知します。</span><span class="sxs-lookup"><span data-stu-id="0af58-103">Notifies the host that the thread that is making the call is about to block, perhaps for a garbage collection or other suspension.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0af58-104">構文</span><span class="sxs-lookup"><span data-stu-id="0af58-104">Syntax</span></span>  
  
```  
HRESULT ThreadIsBlockingForSuspension ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="0af58-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="0af58-105">Remarks</span></span>  
 <span data-ttu-id="0af58-106">内でホストを選択できます、`ThreadIsBlockingForSuspension`コールバック スレッドのスケジュールを変更するかどうか。</span><span class="sxs-lookup"><span data-stu-id="0af58-106">The host may choose within the `ThreadIsBlockingForSuspension` callback whether to reschedule a thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0af58-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="0af58-107">Requirements</span></span>  
 <span data-ttu-id="0af58-108">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0af58-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0af58-109">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0af58-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0af58-110">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="0af58-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0af58-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0af58-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0af58-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="0af58-112">See also</span></span>

- [<span data-ttu-id="0af58-113">IGCThreadControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0af58-113">IGCThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md)
