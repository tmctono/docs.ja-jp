---
title: ICLRIoCompletionManager インターフェイス
ms.date: 03/30/2017
api_name:
- ICLRIoCompletionManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRIoCompletionManager
helpviewer_keywords:
- ICLRIoCompletionManager interface [.NET Framework hosting]
ms.assetid: c6c3ace6-e5e7-4450-8cc5-a9a48208c493
topic_type:
- apiref
ms.openlocfilehash: 822b51531b7afc1c824c74b9580d9208e347e13b
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703553"
---
# <a name="iclriocompletionmanager-interface"></a><span data-ttu-id="98060-102">ICLRIoCompletionManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="98060-102">ICLRIoCompletionManager Interface</span></span>
<span data-ttu-id="98060-103">ホストが、指定された i/o 要求のステータスの共通言語ランタイム (CLR) に通知するためのコールバックメソッドを実装します。</span><span class="sxs-lookup"><span data-stu-id="98060-103">Implements a callback method that allows the host to notify the common language runtime (CLR) of the status of specified I/O requests.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="98060-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="98060-104">Methods</span></span>  
  
|<span data-ttu-id="98060-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="98060-105">Method</span></span>|<span data-ttu-id="98060-106">説明</span><span class="sxs-lookup"><span data-stu-id="98060-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="98060-107">OnComplete メソッド</span><span class="sxs-lookup"><span data-stu-id="98060-107">OnComplete Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md)|<span data-ttu-id="98060-108">[Ihohooの](ihostiocompletionmanager-bind-method.md)呼び出しを使用して作成された i/o 要求の状態を CLR に通知します:: Bind メソッド。</span><span class="sxs-lookup"><span data-stu-id="98060-108">Notifies the CLR of the status of an I/O request that was made by using a call to the [IHostIoCompletionManager::Bind](ihostiocompletionmanager-bind-method.md) method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="98060-109">解説</span><span class="sxs-lookup"><span data-stu-id="98060-109">Remarks</span></span>  
 <span data-ttu-id="98060-110">ホストは、 [Ihohoocompletion manager](ihostiocompletionmanager-interface.md)インターフェイスを使用して i/o 完了の抽象化を実装します。</span><span class="sxs-lookup"><span data-stu-id="98060-110">The host implements the I/O completion abstraction by using the [IHostIoCompletionManager](ihostiocompletionmanager-interface.md) interface.</span></span> <span data-ttu-id="98060-111">CLR はこのインターフェイスを介して i/o 要求を行い、ホストはインターフェイスを使用して、そのような要求の結果をランタイムに通知し `ICLRIoCompletionManager` ます。</span><span class="sxs-lookup"><span data-stu-id="98060-111">The CLR makes I/O requests through this interface, and the host notifies the runtime of the outcome of such requests by using the `ICLRIoCompletionManager` interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="98060-112">要件</span><span class="sxs-lookup"><span data-stu-id="98060-112">Requirements</span></span>  
 <span data-ttu-id="98060-113">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="98060-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98060-114">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="98060-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="98060-115">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="98060-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="98060-116">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98060-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98060-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="98060-117">See also</span></span>

- [<span data-ttu-id="98060-118">IHostIoCompletionManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="98060-118">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)
- [<span data-ttu-id="98060-119">IHostThreadPoolManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="98060-119">IHostThreadPoolManager Interface</span></span>](ihostthreadpoolmanager-interface.md)
- [<span data-ttu-id="98060-120">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="98060-120">Hosting Interfaces</span></span>](hosting-interfaces.md)
