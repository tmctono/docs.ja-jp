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
ms.openlocfilehash: b63d4269a8d48ee49016a4c51d63bf81bdba8da2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141020"
---
# <a name="iclriocompletionmanager-interface"></a><span data-ttu-id="1bd24-102">ICLRIoCompletionManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1bd24-102">ICLRIoCompletionManager Interface</span></span>
<span data-ttu-id="1bd24-103">ホストが、指定された i/o 要求のステータスの共通言語ランタイム (CLR) に通知するためのコールバックメソッドを実装します。</span><span class="sxs-lookup"><span data-stu-id="1bd24-103">Implements a callback method that allows the host to notify the common language runtime (CLR) of the status of specified I/O requests.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1bd24-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="1bd24-104">Methods</span></span>  
  
|<span data-ttu-id="1bd24-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="1bd24-105">Method</span></span>|<span data-ttu-id="1bd24-106">説明</span><span class="sxs-lookup"><span data-stu-id="1bd24-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1bd24-107">OnComplete メソッド</span><span class="sxs-lookup"><span data-stu-id="1bd24-107">OnComplete Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md)|<span data-ttu-id="1bd24-108">[Ihohooの](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md)呼び出しを使用して作成された i/o 要求の状態を CLR に通知します:: Bind メソッド。</span><span class="sxs-lookup"><span data-stu-id="1bd24-108">Notifies the CLR of the status of an I/O request that was made by using a call to the [IHostIoCompletionManager::Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1bd24-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="1bd24-109">Remarks</span></span>  
 <span data-ttu-id="1bd24-110">ホストは、 [Ihohoocompletion manager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)インターフェイスを使用して i/o 完了の抽象化を実装します。</span><span class="sxs-lookup"><span data-stu-id="1bd24-110">The host implements the I/O completion abstraction by using the [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md) interface.</span></span> <span data-ttu-id="1bd24-111">CLR は、このインターフェイスを介して i/o 要求を行います。ホストは、`ICLRIoCompletionManager` インターフェイスを使用して、そのような要求の結果をランタイムに通知します。</span><span class="sxs-lookup"><span data-stu-id="1bd24-111">The CLR makes I/O requests through this interface, and the host notifies the runtime of the outcome of such requests by using the `ICLRIoCompletionManager` interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1bd24-112">［要件］</span><span class="sxs-lookup"><span data-stu-id="1bd24-112">Requirements</span></span>  
 <span data-ttu-id="1bd24-113">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1bd24-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1bd24-114">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="1bd24-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1bd24-115">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="1bd24-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1bd24-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1bd24-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bd24-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="1bd24-117">See also</span></span>

- [<span data-ttu-id="1bd24-118">IHostIoCompletionManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1bd24-118">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
- [<span data-ttu-id="1bd24-119">IHostThreadPoolManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1bd24-119">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
- [<span data-ttu-id="1bd24-120">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1bd24-120">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
