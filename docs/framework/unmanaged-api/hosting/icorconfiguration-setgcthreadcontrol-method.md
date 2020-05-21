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
ms.openlocfilehash: 7874424150e0f4e1818ad9c72e31fd584e016829
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762397"
---
# <a name="icorconfigurationsetgcthreadcontrol-method"></a><span data-ttu-id="5b6d9-102">ICorConfiguration::SetGCThreadControl メソッド</span><span class="sxs-lookup"><span data-stu-id="5b6d9-102">ICorConfiguration::SetGCThreadControl Method</span></span>
<span data-ttu-id="5b6d9-103">ガベージコレクションに対してブロックされる非ランタイムタスクのスレッドをスケジュールするためのコールバックインターフェイスを設定します。</span><span class="sxs-lookup"><span data-stu-id="5b6d9-103">Sets the callback interface for scheduling threads for non-runtime tasks that would otherwise be blocked for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b6d9-104">構文</span><span class="sxs-lookup"><span data-stu-id="5b6d9-104">Syntax</span></span>  
  
```cpp  
HRESULT SetGCThreadControl (  
    [in] IGCThreadControl* pGCThreadControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5b6d9-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5b6d9-105">Parameters</span></span>  
 `pGCThreadControl`  
 <span data-ttu-id="5b6d9-106">から非ランタイムタスクのスレッドの中断をホストに通知する[Igcthreadcontrol](igcthreadcontrol-interface.md)オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="5b6d9-106">[in] A pointer to an [IGCThreadControl](igcthreadcontrol-interface.md) object that notifies the host about the suspension of threads for non-runtime tasks.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5b6d9-107">解説</span><span class="sxs-lookup"><span data-stu-id="5b6d9-107">Remarks</span></span>  
 <span data-ttu-id="5b6d9-108">ホストは、スレッドを再スケジュールするかどうかにかかわらず、 [Igcthreadcontrol:: ThreadIsBlockingForSuspension](igcthreadcontrol-threadisblockingforsuspension-method.md)コールバック内で選択できます。</span><span class="sxs-lookup"><span data-stu-id="5b6d9-108">The host may choose within the [IGCThreadControl::ThreadIsBlockingForSuspension](igcthreadcontrol-threadisblockingforsuspension-method.md) callback whether to reschedule a thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b6d9-109">要件</span><span class="sxs-lookup"><span data-stu-id="5b6d9-109">Requirements</span></span>  
 <span data-ttu-id="5b6d9-110">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5b6d9-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b6d9-111">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="5b6d9-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5b6d9-112">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="5b6d9-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5b6d9-113">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b6d9-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b6d9-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="5b6d9-114">See also</span></span>

- [<span data-ttu-id="5b6d9-115">ICorConfiguration インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5b6d9-115">ICorConfiguration Interface</span></span>](icorconfiguration-interface.md)
