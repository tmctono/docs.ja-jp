---
title: IHostCrst::TryEnter メソッド
ms.date: 03/30/2017
api_name:
- IHostCrst.TryEnter
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostCrst::TryEnter
helpviewer_keywords:
- IHostCrst::TryEnter method [.NET Framework hosting]
- TryEnter method [.NET Framework hosting]
ms.assetid: a922fa98-beab-4f09-a342-cc94fc65687f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d0b4074d9dab8ad46468930373ad44b0c72bd690
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67763743"
---
# <a name="ihostcrsttryenter-method"></a><span data-ttu-id="5f449-102">IHostCrst::TryEnter メソッド</span><span class="sxs-lookup"><span data-stu-id="5f449-102">IHostCrst::TryEnter Method</span></span>
<span data-ttu-id="5f449-103">現在によって表される、クリティカル セクションを入力しようとしています。 [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)インスタンス。</span><span class="sxs-lookup"><span data-stu-id="5f449-103">Attempts to enter the critical section represented by the current [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f449-104">構文</span><span class="sxs-lookup"><span data-stu-id="5f449-104">Syntax</span></span>  
  
```cpp  
HRESULT TryEnter (  
    [in]  DWORD  option,  
    [out] BOOL   *pbSucceeded  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5f449-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5f449-105">Parameters</span></span>  
 `option`  
 <span data-ttu-id="5f449-106">[in]1 つ、 [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md)場合、ホストが実行するアクションを示す値、操作がブロックされます。</span><span class="sxs-lookup"><span data-stu-id="5f449-106">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) values, indicating what action the host should take if the operation blocks.</span></span>  
  
 `pbSucceeded`  
 <span data-ttu-id="5f449-107">[out]`true`入力以外の場合、クリティカル セクションが表示できる場合は`false`します。</span><span class="sxs-lookup"><span data-stu-id="5f449-107">[out] `true` if the critical section can be entered; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5f449-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="5f449-108">Return Value</span></span>  
  
|<span data-ttu-id="5f449-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5f449-109">HRESULT</span></span>|<span data-ttu-id="5f449-110">説明</span><span class="sxs-lookup"><span data-stu-id="5f449-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5f449-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="5f449-111">S_OK</span></span>|<span data-ttu-id="5f449-112">`TryEnter` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="5f449-112">`TryEnter` returned successfully.</span></span>|  
|<span data-ttu-id="5f449-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5f449-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5f449-114">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="5f449-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5f449-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5f449-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5f449-116">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="5f449-116">The call timed out.</span></span>|  
|<span data-ttu-id="5f449-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5f449-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5f449-118">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="5f449-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5f449-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5f449-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5f449-120">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="5f449-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5f449-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5f449-121">E_FAIL</span></span>|<span data-ttu-id="5f449-122">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="5f449-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5f449-123">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="5f449-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5f449-124">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="5f449-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5f449-125">Remarks</span><span class="sxs-lookup"><span data-stu-id="5f449-125">Remarks</span></span>  
 <span data-ttu-id="5f449-126">`TryEnter` すぐに返しを呼び出し元のスレッドがクリティカル セクションを入力するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="5f449-126">`TryEnter` returns immediately and indicates whether the calling thread entered the critical section.</span></span> <span data-ttu-id="5f449-127">このメソッドは、Wind32 をミラー化`TryEnterCriticalSection`関数。</span><span class="sxs-lookup"><span data-stu-id="5f449-127">This method mirrors the Wind32 `TryEnterCriticalSection` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f449-128">必要条件</span><span class="sxs-lookup"><span data-stu-id="5f449-128">Requirements</span></span>  
 <span data-ttu-id="5f449-129">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5f449-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f449-130">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5f449-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5f449-131">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="5f449-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5f449-132">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f449-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f449-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="5f449-133">See also</span></span>

- [<span data-ttu-id="5f449-134">ICLRSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5f449-134">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="5f449-135">IHostCrst インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5f449-135">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)
- [<span data-ttu-id="5f449-136">IHostSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5f449-136">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
