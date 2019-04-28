---
title: ICLRGCManager::SetGCStartupLimits メソッド
ms.date: 03/30/2017
api_name:
- ICLRGCManager.SetGCStartupLimits
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRGCManager::SetGCStartupLimits
helpviewer_keywords:
- SetGCStartupLimits method, ICLRGCManager interface [.NET Framework hosting]
- ICLRGCManager::SetGCStartupLimits method [.NET Framework hosting]
ms.assetid: 1c8d9959-95b5-4131-be4a-556d97774014
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1ffbe29db96cbb6162adc3b4cc77b45dcef27a46
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61700255"
---
# <a name="iclrgcmanagersetgcstartuplimits-method"></a><span data-ttu-id="34bbc-102">ICLRGCManager::SetGCStartupLimits メソッド</span><span class="sxs-lookup"><span data-stu-id="34bbc-102">ICLRGCManager::SetGCStartupLimits Method</span></span>
<span data-ttu-id="34bbc-103">ガベージ コレクション セグメントのサイズと、ガベージ コレクション システムのジェネレーション 0 の最大サイズを設定します。</span><span class="sxs-lookup"><span data-stu-id="34bbc-103">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="34bbc-104">以降では、[!INCLUDE[net_v45](../../../../includes/net-v45-md.md)]セグメントのサイズを設定して、サイズの最大のジェネレーション 0 の値より大きい、`DWORD`を使用して、 [iclrgcmanager 2::setgcstartuplimitsex](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="34bbc-104">Starting with the [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], you can set segment size and maximum generation 0 size to values greater than `DWORD` by using the [ICLRGCManager2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34bbc-105">構文</span><span class="sxs-lookup"><span data-stu-id="34bbc-105">Syntax</span></span>  
  
```  
HRESULT SetGCStartupLimits (  
    [in] DWORD SegmentSize,   
    [in] DWORD MaxGen0Size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="34bbc-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="34bbc-106">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="34bbc-107">[in]ガベージ コレクション セグメントの指定されたサイズ。</span><span class="sxs-lookup"><span data-stu-id="34bbc-107">[in] The specified size of a garbage collection segment.</span></span>  
  
 <span data-ttu-id="34bbc-108">セグメントの最小サイズは、4 MB です。</span><span class="sxs-lookup"><span data-stu-id="34bbc-108">The minimum segment size is 4 MB.</span></span> <span data-ttu-id="34bbc-109">セグメントには、1 MB 単位で増加以上を指定できます。</span><span class="sxs-lookup"><span data-stu-id="34bbc-109">Segments can be increased in increments of 1 MB or larger.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="34bbc-110">[in]ジェネレーション 0 の指定した最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="34bbc-110">[in] The specified maximum size for generation 0.</span></span>  
  
 <span data-ttu-id="34bbc-111">ジェネレーション 0 の最小サイズは、64 KB です。</span><span class="sxs-lookup"><span data-stu-id="34bbc-111">The minimum generation 0 size is 64 KB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="34bbc-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="34bbc-112">Return Value</span></span>  
  
|<span data-ttu-id="34bbc-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="34bbc-113">HRESULT</span></span>|<span data-ttu-id="34bbc-114">説明</span><span class="sxs-lookup"><span data-stu-id="34bbc-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="34bbc-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="34bbc-115">S_OK</span></span>|<span data-ttu-id="34bbc-116">`SetGCStartupLimits` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="34bbc-116">`SetGCStartupLimits` returned successfully.</span></span>|  
|<span data-ttu-id="34bbc-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="34bbc-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="34bbc-118">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="34bbc-118">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="34bbc-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="34bbc-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="34bbc-120">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="34bbc-120">The call timed out.</span></span>|  
|<span data-ttu-id="34bbc-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="34bbc-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="34bbc-122">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="34bbc-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="34bbc-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="34bbc-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="34bbc-124">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="34bbc-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="34bbc-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="34bbc-125">E_FAIL</span></span>|<span data-ttu-id="34bbc-126">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="34bbc-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="34bbc-127">メソッドには、E_FAIL が返された、後に、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="34bbc-127">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="34bbc-128">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="34bbc-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="34bbc-129">Remarks</span><span class="sxs-lookup"><span data-stu-id="34bbc-129">Remarks</span></span>  
 <span data-ttu-id="34bbc-130">値を`SetGCStartupLimits`セットは 1 回だけ指定できます。</span><span class="sxs-lookup"><span data-stu-id="34bbc-130">The values that `SetGCStartupLimits` sets can be specified only once.</span></span> <span data-ttu-id="34bbc-131">後で呼び出し`SetGCStartupLimits`は無視されます。</span><span class="sxs-lookup"><span data-stu-id="34bbc-131">Later calls to `SetGCStartupLimits` are ignored.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34bbc-132">必要条件</span><span class="sxs-lookup"><span data-stu-id="34bbc-132">Requirements</span></span>  
 <span data-ttu-id="34bbc-133">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="34bbc-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34bbc-134">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="34bbc-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="34bbc-135">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="34bbc-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="34bbc-136">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34bbc-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34bbc-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="34bbc-137">See also</span></span>

- [<span data-ttu-id="34bbc-138">自動メモリ管理</span><span class="sxs-lookup"><span data-stu-id="34bbc-138">Automatic Memory Management</span></span>](../../../../docs/standard/automatic-memory-management.md)
- [<span data-ttu-id="34bbc-139">ガベージ コレクション</span><span class="sxs-lookup"><span data-stu-id="34bbc-139">Garbage Collection</span></span>](../../../../docs/standard/garbage-collection/index.md)
- [<span data-ttu-id="34bbc-140">ICLRControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="34bbc-140">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="34bbc-141">ICLRGCManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="34bbc-141">ICLRGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)
