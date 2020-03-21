---
title: ICLRGCManager2::SetGCStartupLimitsEx メソッド
ms.date: 03/30/2017
api_name:
- ICLRGCManager2.SetGCStartupLimitsEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRGCManager2::SetCLRGCStartupLimitsEx
helpviewer_keywords:
- ICLRGCManager2::SetGCStartupLimitsEx method [.NET Framework hosting]
- SetGCStartupLimitsEx method, ICLRGCManager2 interface [.NET Framework hosting]
ms.assetid: 6c3a08a9-5d65-48d4-8bbf-2a86ed7d356a
topic_type:
- apiref
ms.openlocfilehash: 9885149a71147db6eef13958b8ef825caa1d6ec6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176384"
---
# <a name="iclrgcmanager2setgcstartuplimitsex-method"></a><span data-ttu-id="bed7b-102">ICLRGCManager2::SetGCStartupLimitsEx メソッド</span><span class="sxs-lookup"><span data-stu-id="bed7b-102">ICLRGCManager2::SetGCStartupLimitsEx Method</span></span>
<span data-ttu-id="bed7b-103">ガベージ コレクション セグメントのサイズと、ガベージ コレクション システムのジェネレーション 0 の最大サイズを設定します。</span><span class="sxs-lookup"><span data-stu-id="bed7b-103">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bed7b-104">構文</span><span class="sxs-lookup"><span data-stu-id="bed7b-104">Syntax</span></span>  
  
```cpp  
HRESULT SetGCStartupLimitsEx (  
    [in] SIZE_T SegmentSize,
    [in] SIZE_T MaxGen0Size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bed7b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="bed7b-105">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="bed7b-106">[in]ガベージ コレクション セグメントの指定されたサイズ。</span><span class="sxs-lookup"><span data-stu-id="bed7b-106">[in] The specified size of a garbage collection segment.</span></span>  
  
 <span data-ttu-id="bed7b-107">最小セグメント サイズは 4 MB です。</span><span class="sxs-lookup"><span data-stu-id="bed7b-107">The minimum segment size is 4 MB.</span></span> <span data-ttu-id="bed7b-108">セグメントは、1 MB 以上の増分で増やすことができます。</span><span class="sxs-lookup"><span data-stu-id="bed7b-108">Segments can be increased in increments of 1 MB or larger.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="bed7b-109">[in]ジェネレーション 0 の指定された最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="bed7b-109">[in] The specified maximum size for generation 0.</span></span>  
  
 <span data-ttu-id="bed7b-110">最小世代 0 サイズは 64 KB です。</span><span class="sxs-lookup"><span data-stu-id="bed7b-110">The minimum generation 0 size is 64 KB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bed7b-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="bed7b-111">Return Value</span></span>  
  
|<span data-ttu-id="bed7b-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="bed7b-112">HRESULT</span></span>|<span data-ttu-id="bed7b-113">説明</span><span class="sxs-lookup"><span data-stu-id="bed7b-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="bed7b-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="bed7b-114">S_OK</span></span>|<span data-ttu-id="bed7b-115">`SetGCStartupLimitsEx`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="bed7b-115">`SetGCStartupLimitsEx` returned successfully.</span></span>|  
|<span data-ttu-id="bed7b-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="bed7b-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="bed7b-117">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージ コードを実行できない状態または呼び出しを正常に処理できない状態にあります。</span><span class="sxs-lookup"><span data-stu-id="bed7b-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="bed7b-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="bed7b-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="bed7b-119">通話がタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="bed7b-119">The call timed out.</span></span>|  
|<span data-ttu-id="bed7b-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="bed7b-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="bed7b-121">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="bed7b-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="bed7b-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="bed7b-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="bed7b-123">ブロックされたスレッドまたはファイバが待機しているときにイベントがキャンセルされました。</span><span class="sxs-lookup"><span data-stu-id="bed7b-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="bed7b-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="bed7b-124">E_FAIL</span></span>|<span data-ttu-id="bed7b-125">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="bed7b-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="bed7b-126">メソッドがE_FAILを返した後、CLR はプロセス内で使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="bed7b-126">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="bed7b-127">ホスト メソッドへの後続の呼び出しは、HOST_E_CLRNOTAVAILABLEを返します。</span><span class="sxs-lookup"><span data-stu-id="bed7b-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bed7b-128">解説</span><span class="sxs-lookup"><span data-stu-id="bed7b-128">Remarks</span></span>  
 <span data-ttu-id="bed7b-129">設定する値`SetGCStartupLimitsEx`は、ホストが開始される前にのみ指定できます。</span><span class="sxs-lookup"><span data-stu-id="bed7b-129">The values that `SetGCStartupLimitsEx` sets can be specified only before the host is started.</span></span> <span data-ttu-id="bed7b-130">以降の`SetGCStartupLimitsEx`呼び出しは無視されます。</span><span class="sxs-lookup"><span data-stu-id="bed7b-130">Later calls to `SetGCStartupLimitsEx` are ignored.</span></span>  
  
 <span data-ttu-id="bed7b-131">どちらかのパラメータに影響を与えずに設定するには、変更しないパラメータに 0 (ゼロ) を指定します。</span><span class="sxs-lookup"><span data-stu-id="bed7b-131">To set either parameter without affecting the other, specify 0 (zero) for the parameter you don't want to change.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bed7b-132">必要条件</span><span class="sxs-lookup"><span data-stu-id="bed7b-132">Requirements</span></span>  
 <span data-ttu-id="bed7b-133">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bed7b-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bed7b-134">**ヘッダー:** msCorEE.h</span><span class="sxs-lookup"><span data-stu-id="bed7b-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bed7b-135">**ライブラリ:** MSCorEE.dll にリソースとして含まれる</span><span class="sxs-lookup"><span data-stu-id="bed7b-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bed7b-136">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bed7b-136">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bed7b-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="bed7b-137">See also</span></span>

- [<span data-ttu-id="bed7b-138">自動メモリ管理</span><span class="sxs-lookup"><span data-stu-id="bed7b-138">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="bed7b-139">ガベージ コレクション</span><span class="sxs-lookup"><span data-stu-id="bed7b-139">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
- [<span data-ttu-id="bed7b-140">ICLRControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bed7b-140">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="bed7b-141">ICLRGCManager2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bed7b-141">ICLRGCManager2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md)
