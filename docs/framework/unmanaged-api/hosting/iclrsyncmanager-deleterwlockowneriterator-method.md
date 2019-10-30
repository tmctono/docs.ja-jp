---
title: ICLRSyncManager::DeleteRWLockOwnerIterator メソッド
ms.date: 03/30/2017
api_name:
- ICLRSyncManager.DeleteRWLockOwnerIterator
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRSyncManager::DeleteRWLockOwnerIterator
helpviewer_keywords:
- ICLRSyncManager::DeleteRWLockOwnerIterator method [.NET Framework hosting]
- DeleteRWLockOwnerIterator method [.NET Framework hosting]
ms.assetid: fcfd340a-b7d6-44e4-8167-2c05b789d483
topic_type:
- apiref
ms.openlocfilehash: fb02b5c941e15d172140565e8efb625234947cd7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130580"
---
# <a name="iclrsyncmanagerdeleterwlockowneriterator-method"></a><span data-ttu-id="d31cd-102">ICLRSyncManager::DeleteRWLockOwnerIterator メソッド</span><span class="sxs-lookup"><span data-stu-id="d31cd-102">ICLRSyncManager::DeleteRWLockOwnerIterator Method</span></span>
<span data-ttu-id="d31cd-103">[ICLRSyncManager:: CreateRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md)の呼び出しによって作成された反復子を、共通言語ランタイム (CLR) が破棄することを要求します。</span><span class="sxs-lookup"><span data-stu-id="d31cd-103">Requests that the common language runtime (CLR) destroy an iterator that was created by a call to [ICLRSyncManager::CreateRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d31cd-104">構文</span><span class="sxs-lookup"><span data-stu-id="d31cd-104">Syntax</span></span>  
  
```cpp  
HRESULT DeleteRWLockOwnerIterator (  
    [in] SIZE_T  Iterator  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d31cd-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d31cd-105">Parameters</span></span>  
 `Iterator`  
 <span data-ttu-id="d31cd-106">から`CreateRWLockOwnerIterator`の呼び出しを使用して作成された反復子。</span><span class="sxs-lookup"><span data-stu-id="d31cd-106">[in] The iterator that was created by using a call to `CreateRWLockOwnerIterator`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d31cd-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="d31cd-107">Return Value</span></span>  
  
|<span data-ttu-id="d31cd-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d31cd-108">HRESULT</span></span>|<span data-ttu-id="d31cd-109">説明</span><span class="sxs-lookup"><span data-stu-id="d31cd-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d31cd-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="d31cd-110">S_OK</span></span>|<span data-ttu-id="d31cd-111">`DeleteRWLockOwnerIterator` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="d31cd-111">`DeleteRWLockOwnerIterator` returned successfully.</span></span>|  
|<span data-ttu-id="d31cd-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d31cd-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d31cd-113">CLR がプロセスに読み込まれていないか、マネージコードを実行できないか、または呼び出しを正常に処理できない状態になっています。</span><span class="sxs-lookup"><span data-stu-id="d31cd-113">The CLR has not been loaded into a process, or is in a state in which it cannot run managed code or successfully process the call.</span></span>|  
|<span data-ttu-id="d31cd-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d31cd-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d31cd-115">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="d31cd-115">The call timed out.</span></span>|  
|<span data-ttu-id="d31cd-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d31cd-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d31cd-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="d31cd-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d31cd-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d31cd-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d31cd-119">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="d31cd-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d31cd-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d31cd-120">E_FAIL</span></span>|<span data-ttu-id="d31cd-121">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="d31cd-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d31cd-122">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="d31cd-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d31cd-123">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="d31cd-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d31cd-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="d31cd-124">Remarks</span></span>  
 <span data-ttu-id="d31cd-125">ホストはこのメソッドを呼び出して `CreateRWLockOwnerIterator` し、そのスレッド実装が同期された状態を維持することができます。</span><span class="sxs-lookup"><span data-stu-id="d31cd-125">The host can call this method and `CreateRWLockOwnerIterator` to ensure that its threading implementation remains synchronized.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d31cd-126">［要件］</span><span class="sxs-lookup"><span data-stu-id="d31cd-126">Requirements</span></span>  
 <span data-ttu-id="d31cd-127">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d31cd-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d31cd-128">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="d31cd-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d31cd-129">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="d31cd-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d31cd-130">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d31cd-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d31cd-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="d31cd-131">See also</span></span>

- [<span data-ttu-id="d31cd-132">ICLRSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d31cd-132">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="d31cd-133">IHostSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d31cd-133">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
