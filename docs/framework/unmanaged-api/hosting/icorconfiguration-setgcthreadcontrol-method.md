---
title: ICorConfiguration::SetGCThreadControl メソッド
ms.date: 03/30/2017
api_name:
- ICorConfiguration.SetGCThreadControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SetGCThreadControl
helpviewer_keywords:
- ICorConfiguration::SetGCThreadControl method [.NET Framework hosting]
- SetGCThreadControl method [.NET Framework hosting]
ms.assetid: 72e38e61-3d56-4ae3-b8f6-0ab7922aaf11
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 93b52e0faef0fa3cc22283d6b46c5fe5153c3eb2
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779865"
---
# <a name="icorconfigurationsetgcthreadcontrol-method"></a><span data-ttu-id="0d4a5-102">ICorConfiguration::SetGCThreadControl メソッド</span><span class="sxs-lookup"><span data-stu-id="0d4a5-102">ICorConfiguration::SetGCThreadControl Method</span></span>
<span data-ttu-id="0d4a5-103">それ以外の場合、ガベージ コレクションのブロックされる非ランタイム タスクのスレッドをスケジュールするためのコールバック インターフェイスを設定します。</span><span class="sxs-lookup"><span data-stu-id="0d4a5-103">Sets the callback interface for scheduling threads for non-runtime tasks that would otherwise be blocked for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d4a5-104">構文</span><span class="sxs-lookup"><span data-stu-id="0d4a5-104">Syntax</span></span>  
  
```cpp  
HRESULT SetGCThreadControl (  
    [in] IGCThreadControl* pGCThreadControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0d4a5-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0d4a5-105">Parameters</span></span>  
 `pGCThreadControl`  
 <span data-ttu-id="0d4a5-106">[in]ポインター、 [IGCThreadControl](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md)非ランタイム タスクのスレッドの中断に関するホストに通知するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="0d4a5-106">[in] A pointer to an [IGCThreadControl](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md) object that notifies the host about the suspension of threads for non-runtime tasks.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0d4a5-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="0d4a5-107">Remarks</span></span>  
 <span data-ttu-id="0d4a5-108">内でホストを選択できます、 [igcthreadcontrol::threadisblockingforsuspension](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-threadisblockingforsuspension-method.md)コールバック スレッドのスケジュールを変更するかどうか。</span><span class="sxs-lookup"><span data-stu-id="0d4a5-108">The host may choose within the [IGCThreadControl::ThreadIsBlockingForSuspension](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-threadisblockingforsuspension-method.md) callback whether to reschedule a thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d4a5-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="0d4a5-109">Requirements</span></span>  
 <span data-ttu-id="0d4a5-110">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0d4a5-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d4a5-111">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0d4a5-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0d4a5-112">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="0d4a5-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0d4a5-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d4a5-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d4a5-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="0d4a5-114">See also</span></span>

- [<span data-ttu-id="0d4a5-115">ICorConfiguration インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0d4a5-115">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)
