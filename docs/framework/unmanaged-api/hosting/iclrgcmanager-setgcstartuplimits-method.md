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
ms.openlocfilehash: 645b64c8b536029663c350bdcde9a716a715aab3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178083"
---
# <a name="iclrgcmanagersetgcstartuplimits-method"></a><span data-ttu-id="6b4f9-102">ICLRGCManager::SetGCStartupLimits メソッド</span><span class="sxs-lookup"><span data-stu-id="6b4f9-102">ICLRGCManager::SetGCStartupLimits Method</span></span>
<span data-ttu-id="6b4f9-103">ガベージ コレクション セグメントのサイズと、ガベージ コレクション システムのジェネレーション 0 の最大サイズを設定します。</span><span class="sxs-lookup"><span data-stu-id="6b4f9-103">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="6b4f9-104">NET Framework 4.5 以降では、セグメント サイズと最大世代 0 サイズを`DWORD`[ICLRGCManager2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md)メソッドを使用して、より大きな値に設定できます。</span><span class="sxs-lookup"><span data-stu-id="6b4f9-104">Starting with the .NET Framework 4.5, you can set segment size and maximum generation 0 size to values greater than `DWORD` by using the [ICLRGCManager2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b4f9-105">構文</span><span class="sxs-lookup"><span data-stu-id="6b4f9-105">Syntax</span></span>  
  
```cpp  
HRESULT SetGCStartupLimits (  
    [in] DWORD SegmentSize,
    [in] DWORD MaxGen0Size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6b4f9-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6b4f9-106">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="6b4f9-107">[in]ガベージ コレクション セグメントの指定されたサイズ。</span><span class="sxs-lookup"><span data-stu-id="6b4f9-107">[in] The specified size of a garbage collection segment.</span></span>  
  
 <span data-ttu-id="6b4f9-108">最小セグメント サイズは 4 MB です。</span><span class="sxs-lookup"><span data-stu-id="6b4f9-108">The minimum segment size is 4 MB.</span></span> <span data-ttu-id="6b4f9-109">セグメントは、1 MB 以上の増分で増やすことができます。</span><span class="sxs-lookup"><span data-stu-id="6b4f9-109">Segments can be increased in increments of 1 MB or larger.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="6b4f9-110">[in]ジェネレーション 0 の指定された最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="6b4f9-110">[in] The specified maximum size for generation 0.</span></span>  
  
 <span data-ttu-id="6b4f9-111">最小世代 0 サイズは 64 KB です。</span><span class="sxs-lookup"><span data-stu-id="6b4f9-111">The minimum generation 0 size is 64 KB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6b4f9-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="6b4f9-112">Return Value</span></span>  
  
|<span data-ttu-id="6b4f9-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6b4f9-113">HRESULT</span></span>|<span data-ttu-id="6b4f9-114">説明</span><span class="sxs-lookup"><span data-stu-id="6b4f9-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6b4f9-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="6b4f9-115">S_OK</span></span>|<span data-ttu-id="6b4f9-116">`SetGCStartupLimits`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="6b4f9-116">`SetGCStartupLimits` returned successfully.</span></span>|  
|<span data-ttu-id="6b4f9-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6b4f9-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6b4f9-118">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージ コードを実行できない状態または呼び出しを正常に処理できない状態にあります。</span><span class="sxs-lookup"><span data-stu-id="6b4f9-118">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="6b4f9-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="6b4f9-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="6b4f9-120">通話がタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="6b4f9-120">The call timed out.</span></span>|  
|<span data-ttu-id="6b4f9-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="6b4f9-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="6b4f9-122">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="6b4f9-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="6b4f9-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="6b4f9-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="6b4f9-124">ブロックされたスレッドまたはファイバが待機しているときにイベントがキャンセルされました。</span><span class="sxs-lookup"><span data-stu-id="6b4f9-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="6b4f9-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6b4f9-125">E_FAIL</span></span>|<span data-ttu-id="6b4f9-126">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="6b4f9-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="6b4f9-127">メソッドがE_FAILを返した後、CLR はプロセス内で使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="6b4f9-127">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="6b4f9-128">ホスト メソッドへの後続の呼び出しは、HOST_E_CLRNOTAVAILABLEを返します。</span><span class="sxs-lookup"><span data-stu-id="6b4f9-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6b4f9-129">解説</span><span class="sxs-lookup"><span data-stu-id="6b4f9-129">Remarks</span></span>  
 <span data-ttu-id="6b4f9-130">設定する`SetGCStartupLimits`値は、1 回だけ指定できます。</span><span class="sxs-lookup"><span data-stu-id="6b4f9-130">The values that `SetGCStartupLimits` sets can be specified only once.</span></span> <span data-ttu-id="6b4f9-131">以降の`SetGCStartupLimits`呼び出しは無視されます。</span><span class="sxs-lookup"><span data-stu-id="6b4f9-131">Later calls to `SetGCStartupLimits` are ignored.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b4f9-132">必要条件</span><span class="sxs-lookup"><span data-stu-id="6b4f9-132">Requirements</span></span>  
 <span data-ttu-id="6b4f9-133">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b4f9-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b4f9-134">**ヘッダー:** msCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6b4f9-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6b4f9-135">**ライブラリ:** MSCorEE.dll にリソースとして含まれる</span><span class="sxs-lookup"><span data-stu-id="6b4f9-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6b4f9-136">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6b4f9-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b4f9-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="6b4f9-137">See also</span></span>

- [<span data-ttu-id="6b4f9-138">自動メモリ管理</span><span class="sxs-lookup"><span data-stu-id="6b4f9-138">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="6b4f9-139">ガベージ コレクション</span><span class="sxs-lookup"><span data-stu-id="6b4f9-139">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
- [<span data-ttu-id="6b4f9-140">ICLRControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6b4f9-140">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="6b4f9-141">ICLRGCManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6b4f9-141">ICLRGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)
