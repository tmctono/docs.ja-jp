---
title: IHostMemoryManager::GetMemoryLoad メソッド
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.GetMemoryLoad
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::GetMemoryLoad
helpviewer_keywords:
- IHostMemoryManager::GetMemoryLoad method [.NET Framework hosting]
- GetMemoryLoad method [.NET Framework hosting]
ms.assetid: e8138f6e-a0a4-48d4-8dae-9466b4dc6180
topic_type:
- apiref
ms.openlocfilehash: 88acd50c83eb1ff4d59aa50d677db2383912659a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176280"
---
# <a name="ihostmemorymanagergetmemoryload-method"></a><span data-ttu-id="8fdbf-102">IHostMemoryManager::GetMemoryLoad メソッド</span><span class="sxs-lookup"><span data-stu-id="8fdbf-102">IHostMemoryManager::GetMemoryLoad Method</span></span>
<span data-ttu-id="8fdbf-103">ホストによって報告された、現在使用中であり、したがって利用できない物理メモリの量を取得します。</span><span class="sxs-lookup"><span data-stu-id="8fdbf-103">Gets the amount of physical memory that is currently in use, and therefore unavailable, as reported by the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8fdbf-104">構文</span><span class="sxs-lookup"><span data-stu-id="8fdbf-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMemoryLoad (  
    [out] DWORD*  pMemoryLoad,
    [out] SIZE_T  *pAvailableBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8fdbf-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8fdbf-105">Parameters</span></span>  
 `pMemoryLoad`  
 <span data-ttu-id="8fdbf-106">[アウト]現在使用中の物理メモリの合計に対する概算のパーセンテージへのポインター。</span><span class="sxs-lookup"><span data-stu-id="8fdbf-106">[out] A pointer to the approximate percentage of total physical memory that is currently in use.</span></span>  
  
 `pAvailableBytes`  
 <span data-ttu-id="8fdbf-107">[アウト]共通言語ランタイム (CLR) で使用できるバイト数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="8fdbf-107">[out] A pointer to the number of bytes available to the common language runtime (CLR).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8fdbf-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="8fdbf-108">Return Value</span></span>  
  
|<span data-ttu-id="8fdbf-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8fdbf-109">HRESULT</span></span>|<span data-ttu-id="8fdbf-110">説明</span><span class="sxs-lookup"><span data-stu-id="8fdbf-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8fdbf-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="8fdbf-111">S_OK</span></span>|<span data-ttu-id="8fdbf-112">`GetMemoryLoad`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="8fdbf-112">`GetMemoryLoad` returned successfully.</span></span>|  
|<span data-ttu-id="8fdbf-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8fdbf-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8fdbf-114">CLR がプロセスに読み込まれていないか、CLR がマネージ コードを実行できない状態または呼び出しを正常に処理できない状態にあります。</span><span class="sxs-lookup"><span data-stu-id="8fdbf-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8fdbf-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8fdbf-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8fdbf-116">通話がタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="8fdbf-116">The call timed out.</span></span>|  
|<span data-ttu-id="8fdbf-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8fdbf-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8fdbf-118">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="8fdbf-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8fdbf-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8fdbf-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8fdbf-120">ブロックされたスレッドまたはファイバが待機しているときにイベントがキャンセルされました。</span><span class="sxs-lookup"><span data-stu-id="8fdbf-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8fdbf-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8fdbf-121">E_FAIL</span></span>|<span data-ttu-id="8fdbf-122">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="8fdbf-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8fdbf-123">メソッドがE_FAILを返すと、CLR はプロセス内で使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="8fdbf-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8fdbf-124">ホスト メソッドへの後続の呼び出しは、HOST_E_CLRNOTAVAILABLEを返します。</span><span class="sxs-lookup"><span data-stu-id="8fdbf-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8fdbf-125">解説</span><span class="sxs-lookup"><span data-stu-id="8fdbf-125">Remarks</span></span>  
 <span data-ttu-id="8fdbf-126">`GetMemoryLoad`Win32`GlobalMemoryStatus`関数をラップします。</span><span class="sxs-lookup"><span data-stu-id="8fdbf-126">`GetMemoryLoad` wraps the Win32 `GlobalMemoryStatus` function.</span></span> <span data-ttu-id="8fdbf-127">の値`pMemoryLoad`は、 から`dwMemoryLoad``MEMORYSTATUS``GlobalMemoryStatus`返される構造体のフィールドと同じです。</span><span class="sxs-lookup"><span data-stu-id="8fdbf-127">The value of `pMemoryLoad` is the equivalent of the `dwMemoryLoad` field in the `MEMORYSTATUS` structure returned from `GlobalMemoryStatus`.</span></span>  
  
 <span data-ttu-id="8fdbf-128">ランタイムは、ガベージ コレクターのヒューリスティックとして戻り値を使用します。</span><span class="sxs-lookup"><span data-stu-id="8fdbf-128">The runtime uses the return value as a heuristic for the garbage collector.</span></span> <span data-ttu-id="8fdbf-129">たとえば、ホストがメモリの大部分が使用中であると報告した場合、ガベージ コレクターは、使用可能になる可能性のあるメモリの量を増やすために、複数の世代から収集することを選択できます。</span><span class="sxs-lookup"><span data-stu-id="8fdbf-129">For example, if the host reports that the majority of memory is in use, the garbage collector may elect to collect from multiple generations to increase the amount of memory that can potentially become available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8fdbf-130">必要条件</span><span class="sxs-lookup"><span data-stu-id="8fdbf-130">Requirements</span></span>  
 <span data-ttu-id="8fdbf-131">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8fdbf-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8fdbf-132">**ヘッダー:** msCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8fdbf-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8fdbf-133">**ライブラリ:** MSCorEE.dll にリソースとして含まれる</span><span class="sxs-lookup"><span data-stu-id="8fdbf-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8fdbf-134">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8fdbf-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fdbf-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="8fdbf-135">See also</span></span>

- <xref:System.GC?displayProperty=nameWithType>
- [<span data-ttu-id="8fdbf-136">IHostMemoryManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8fdbf-136">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
