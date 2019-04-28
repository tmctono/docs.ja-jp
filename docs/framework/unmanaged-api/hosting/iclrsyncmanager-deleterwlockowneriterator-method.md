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
ms.openlocfilehash: 82988d25926a4e61d91a98e7cd5995dacde4e5b7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61763700"
---
# <a name="iclrsyncmanagerdeleterwlockowneriterator-method"></a><span data-ttu-id="61bd8-102">ICLRSyncManager::DeleteRWLockOwnerIterator メソッド</span><span class="sxs-lookup"><span data-stu-id="61bd8-102">ICLRSyncManager::DeleteRWLockOwnerIterator Method</span></span>
<span data-ttu-id="61bd8-103">共通言語ランタイム (CLR) がへの呼び出しによって作成された反復子を破棄することを要求[iclrsyncmanager::createrwlockowneriterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="61bd8-103">Requests that the common language runtime (CLR) destroy an iterator that was created by a call to [ICLRSyncManager::CreateRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61bd8-104">構文</span><span class="sxs-lookup"><span data-stu-id="61bd8-104">Syntax</span></span>  
  
```  
HRESULT DeleteRWLockOwnerIterator (  
    [in] SIZE_T  Iterator  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="61bd8-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="61bd8-105">Parameters</span></span>  
 `Iterator`  
 <span data-ttu-id="61bd8-106">[in]呼び出しを使用して作成された反復子`CreateRWLockOwnerIterator`します。</span><span class="sxs-lookup"><span data-stu-id="61bd8-106">[in] The iterator that was created by using a call to `CreateRWLockOwnerIterator`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="61bd8-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="61bd8-107">Return Value</span></span>  
  
|<span data-ttu-id="61bd8-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="61bd8-108">HRESULT</span></span>|<span data-ttu-id="61bd8-109">説明</span><span class="sxs-lookup"><span data-stu-id="61bd8-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="61bd8-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="61bd8-110">S_OK</span></span>|<span data-ttu-id="61bd8-111">`DeleteRWLockOwnerIterator` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="61bd8-111">`DeleteRWLockOwnerIterator` returned successfully.</span></span>|  
|<span data-ttu-id="61bd8-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="61bd8-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="61bd8-113">CLR では、プロセスに読み込まれていないまたは状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="61bd8-113">The CLR has not been loaded into a process, or is in a state in which it cannot run managed code or successfully process the call.</span></span>|  
|<span data-ttu-id="61bd8-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="61bd8-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="61bd8-115">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="61bd8-115">The call timed out.</span></span>|  
|<span data-ttu-id="61bd8-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="61bd8-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="61bd8-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="61bd8-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="61bd8-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="61bd8-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="61bd8-119">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="61bd8-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="61bd8-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="61bd8-120">E_FAIL</span></span>|<span data-ttu-id="61bd8-121">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="61bd8-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="61bd8-122">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="61bd8-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="61bd8-123">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="61bd8-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="61bd8-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="61bd8-124">Remarks</span></span>  
 <span data-ttu-id="61bd8-125">ホストは、このメソッドを呼び出すことができますと`CreateRWLockOwnerIterator`そのスレッドの実装の同期を維持します。</span><span class="sxs-lookup"><span data-stu-id="61bd8-125">The host can call this method and `CreateRWLockOwnerIterator` to ensure that its threading implementation remains synchronized.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="61bd8-126">必要条件</span><span class="sxs-lookup"><span data-stu-id="61bd8-126">Requirements</span></span>  
 <span data-ttu-id="61bd8-127">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="61bd8-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61bd8-128">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="61bd8-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="61bd8-129">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="61bd8-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="61bd8-130">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="61bd8-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61bd8-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="61bd8-131">See also</span></span>

- [<span data-ttu-id="61bd8-132">ICLRSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="61bd8-132">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="61bd8-133">IHostSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="61bd8-133">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
