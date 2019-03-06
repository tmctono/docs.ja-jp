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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ba0cabfe9e96ace255235f1aa7d2b80452c4d72e
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57482887"
---
# <a name="iclrsyncmanagerdeleterwlockowneriterator-method"></a><span data-ttu-id="fa5e1-102">ICLRSyncManager::DeleteRWLockOwnerIterator メソッド</span><span class="sxs-lookup"><span data-stu-id="fa5e1-102">ICLRSyncManager::DeleteRWLockOwnerIterator Method</span></span>
<span data-ttu-id="fa5e1-103">共通言語ランタイム (CLR) がへの呼び出しによって作成された反復子を破棄することを要求[iclrsyncmanager::createrwlockowneriterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="fa5e1-103">Requests that the common language runtime (CLR) destroy an iterator that was created by a call to [ICLRSyncManager::CreateRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa5e1-104">構文</span><span class="sxs-lookup"><span data-stu-id="fa5e1-104">Syntax</span></span>  
  
```  
HRESULT DeleteRWLockOwnerIterator (  
    [in] SIZE_T  Iterator  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fa5e1-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="fa5e1-105">Parameters</span></span>  
 `Iterator`  
 <span data-ttu-id="fa5e1-106">[in]呼び出しを使用して作成された反復子`CreateRWLockOwnerIterator`します。</span><span class="sxs-lookup"><span data-stu-id="fa5e1-106">[in] The iterator that was created by using a call to `CreateRWLockOwnerIterator`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fa5e1-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="fa5e1-107">Return Value</span></span>  
  
|<span data-ttu-id="fa5e1-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fa5e1-108">HRESULT</span></span>|<span data-ttu-id="fa5e1-109">説明</span><span class="sxs-lookup"><span data-stu-id="fa5e1-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fa5e1-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="fa5e1-110">S_OK</span></span>|<span data-ttu-id="fa5e1-111">`DeleteRWLockOwnerIterator` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="fa5e1-111">`DeleteRWLockOwnerIterator` returned successfully.</span></span>|  
|<span data-ttu-id="fa5e1-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="fa5e1-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="fa5e1-113">CLR では、プロセスに読み込まれていないまたは状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="fa5e1-113">The CLR has not been loaded into a process, or is in a state in which it cannot run managed code or successfully process the call.</span></span>|  
|<span data-ttu-id="fa5e1-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="fa5e1-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="fa5e1-115">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="fa5e1-115">The call timed out.</span></span>|  
|<span data-ttu-id="fa5e1-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="fa5e1-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="fa5e1-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="fa5e1-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="fa5e1-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="fa5e1-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="fa5e1-119">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="fa5e1-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="fa5e1-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="fa5e1-120">E_FAIL</span></span>|<span data-ttu-id="fa5e1-121">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="fa5e1-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="fa5e1-122">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="fa5e1-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="fa5e1-123">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="fa5e1-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fa5e1-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="fa5e1-124">Remarks</span></span>  
 <span data-ttu-id="fa5e1-125">ホストは、このメソッドを呼び出すことができますと`CreateRWLockOwnerIterator`そのスレッドの実装の同期を維持します。</span><span class="sxs-lookup"><span data-stu-id="fa5e1-125">The host can call this method and `CreateRWLockOwnerIterator` to ensure that its threading implementation remains synchronized.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa5e1-126">必要条件</span><span class="sxs-lookup"><span data-stu-id="fa5e1-126">Requirements</span></span>  
 <span data-ttu-id="fa5e1-127">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa5e1-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa5e1-128">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="fa5e1-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fa5e1-129">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="fa5e1-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fa5e1-130">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa5e1-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa5e1-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="fa5e1-131">See also</span></span>
- [<span data-ttu-id="fa5e1-132">ICLRSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fa5e1-132">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="fa5e1-133">IHostSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fa5e1-133">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
