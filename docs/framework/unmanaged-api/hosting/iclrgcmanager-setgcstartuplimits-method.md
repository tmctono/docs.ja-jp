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
ms.openlocfilehash: f9d6c4f01b01944c885190f90e2195c3a308490a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141206"
---
# <a name="iclrgcmanagersetgcstartuplimits-method"></a><span data-ttu-id="757c4-102">ICLRGCManager::SetGCStartupLimits メソッド</span><span class="sxs-lookup"><span data-stu-id="757c4-102">ICLRGCManager::SetGCStartupLimits Method</span></span>
<span data-ttu-id="757c4-103">ガベージコレクションセグメントのサイズとガベージコレクションシステムのジェネレーション0の最大サイズを設定します。</span><span class="sxs-lookup"><span data-stu-id="757c4-103">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="757c4-104">.NET Framework 4.5 以降では、 [ICLRGCManager2:: SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md)メソッドを使用して、セグメントサイズと最大ジェネレーション0のサイズを `DWORD` より大きい値に設定できます。</span><span class="sxs-lookup"><span data-stu-id="757c4-104">Starting with the .NET Framework 4.5, you can set segment size and maximum generation 0 size to values greater than `DWORD` by using the [ICLRGCManager2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="757c4-105">構文</span><span class="sxs-lookup"><span data-stu-id="757c4-105">Syntax</span></span>  
  
```cpp  
HRESULT SetGCStartupLimits (  
    [in] DWORD SegmentSize,   
    [in] DWORD MaxGen0Size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="757c4-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="757c4-106">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="757c4-107">からガベージコレクションセグメントの指定されたサイズ。</span><span class="sxs-lookup"><span data-stu-id="757c4-107">[in] The specified size of a garbage collection segment.</span></span>  
  
 <span data-ttu-id="757c4-108">セグメントの最小サイズは 4 MB です。</span><span class="sxs-lookup"><span data-stu-id="757c4-108">The minimum segment size is 4 MB.</span></span> <span data-ttu-id="757c4-109">セグメントは、1 MB 以上の単位で増やすことができます。</span><span class="sxs-lookup"><span data-stu-id="757c4-109">Segments can be increased in increments of 1 MB or larger.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="757c4-110">からジェネレーション0の指定された最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="757c4-110">[in] The specified maximum size for generation 0.</span></span>  
  
 <span data-ttu-id="757c4-111">ジェネレーション0の最小サイズは 64 KB です。</span><span class="sxs-lookup"><span data-stu-id="757c4-111">The minimum generation 0 size is 64 KB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="757c4-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="757c4-112">Return Value</span></span>  
  
|<span data-ttu-id="757c4-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="757c4-113">HRESULT</span></span>|<span data-ttu-id="757c4-114">説明</span><span class="sxs-lookup"><span data-stu-id="757c4-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="757c4-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="757c4-115">S_OK</span></span>|<span data-ttu-id="757c4-116">`SetGCStartupLimits` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="757c4-116">`SetGCStartupLimits` returned successfully.</span></span>|  
|<span data-ttu-id="757c4-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="757c4-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="757c4-118">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="757c4-118">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="757c4-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="757c4-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="757c4-120">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="757c4-120">The call timed out.</span></span>|  
|<span data-ttu-id="757c4-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="757c4-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="757c4-122">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="757c4-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="757c4-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="757c4-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="757c4-124">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="757c4-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="757c4-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="757c4-125">E_FAIL</span></span>|<span data-ttu-id="757c4-126">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="757c4-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="757c4-127">メソッドから E_FAIL が返された後は、そのプロセス内で CLR を使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="757c4-127">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="757c4-128">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="757c4-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="757c4-129">Remarks</span><span class="sxs-lookup"><span data-stu-id="757c4-129">Remarks</span></span>  
 <span data-ttu-id="757c4-130">`SetGCStartupLimits` セットの値は一度だけ指定できます。</span><span class="sxs-lookup"><span data-stu-id="757c4-130">The values that `SetGCStartupLimits` sets can be specified only once.</span></span> <span data-ttu-id="757c4-131">後で `SetGCStartupLimits` への呼び出しは無視されます。</span><span class="sxs-lookup"><span data-stu-id="757c4-131">Later calls to `SetGCStartupLimits` are ignored.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="757c4-132">［要件］</span><span class="sxs-lookup"><span data-stu-id="757c4-132">Requirements</span></span>  
 <span data-ttu-id="757c4-133">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="757c4-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="757c4-134">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="757c4-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="757c4-135">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="757c4-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="757c4-136">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="757c4-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="757c4-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="757c4-137">See also</span></span>

- [<span data-ttu-id="757c4-138">自動メモリ管理</span><span class="sxs-lookup"><span data-stu-id="757c4-138">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="757c4-139">ガベージ コレクション</span><span class="sxs-lookup"><span data-stu-id="757c4-139">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
- [<span data-ttu-id="757c4-140">ICLRControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="757c4-140">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="757c4-141">ICLRGCManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="757c4-141">ICLRGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)
