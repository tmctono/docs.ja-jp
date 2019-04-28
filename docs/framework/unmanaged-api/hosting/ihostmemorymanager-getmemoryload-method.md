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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c43fd1c63b14fc3254044247213bf09453da870e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61599382"
---
# <a name="ihostmemorymanagergetmemoryload-method"></a><span data-ttu-id="baeb2-102">IHostMemoryManager::GetMemoryLoad メソッド</span><span class="sxs-lookup"><span data-stu-id="baeb2-102">IHostMemoryManager::GetMemoryLoad Method</span></span>
<span data-ttu-id="baeb2-103">現在使用中で、したがって使用不可能で、ホストによって報告された、物理メモリの量を取得します。</span><span class="sxs-lookup"><span data-stu-id="baeb2-103">Gets the amount of physical memory that is currently in use, and therefore unavailable, as reported by the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="baeb2-104">構文</span><span class="sxs-lookup"><span data-stu-id="baeb2-104">Syntax</span></span>  
  
```  
HRESULT GetMemoryLoad (  
    [out] DWORD*  pMemoryLoad,   
    [out] SIZE_T  *pAvailableBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="baeb2-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="baeb2-105">Parameters</span></span>  
 `pMemoryLoad`  
 <span data-ttu-id="baeb2-106">[out]現在使用されている物理メモリの総量のおおよその割合へのポインター。</span><span class="sxs-lookup"><span data-stu-id="baeb2-106">[out] A pointer to the approximate percentage of total physical memory that is currently in use.</span></span>  
  
 `pAvailableBytes`  
 <span data-ttu-id="baeb2-107">[out]共通言語ランタイム (CLR) に使用できるバイト数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="baeb2-107">[out] A pointer to the number of bytes available to the common language runtime (CLR).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="baeb2-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="baeb2-108">Return Value</span></span>  
  
|<span data-ttu-id="baeb2-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="baeb2-109">HRESULT</span></span>|<span data-ttu-id="baeb2-110">説明</span><span class="sxs-lookup"><span data-stu-id="baeb2-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="baeb2-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="baeb2-111">S_OK</span></span>|<span data-ttu-id="baeb2-112">`GetMemoryLoad` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="baeb2-112">`GetMemoryLoad` returned successfully.</span></span>|  
|<span data-ttu-id="baeb2-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="baeb2-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="baeb2-114">プロセスに CLR が読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="baeb2-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="baeb2-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="baeb2-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="baeb2-116">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="baeb2-116">The call timed out.</span></span>|  
|<span data-ttu-id="baeb2-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="baeb2-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="baeb2-118">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="baeb2-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="baeb2-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="baeb2-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="baeb2-120">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="baeb2-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="baeb2-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="baeb2-121">E_FAIL</span></span>|<span data-ttu-id="baeb2-122">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="baeb2-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="baeb2-123">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="baeb2-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="baeb2-124">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="baeb2-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="baeb2-125">Remarks</span><span class="sxs-lookup"><span data-stu-id="baeb2-125">Remarks</span></span>  
 <span data-ttu-id="baeb2-126">`GetMemoryLoad` Win32 のラップ`GlobalMemoryStatus`関数。</span><span class="sxs-lookup"><span data-stu-id="baeb2-126">`GetMemoryLoad` wraps the Win32 `GlobalMemoryStatus` function.</span></span> <span data-ttu-id="baeb2-127">値`pMemoryLoad`相当、`dwMemoryLoad`フィールドに、`MEMORYSTATUS`から返される構造体`GlobalMemoryStatus`します。</span><span class="sxs-lookup"><span data-stu-id="baeb2-127">The value of `pMemoryLoad` is the equivalent of the `dwMemoryLoad` field in the `MEMORYSTATUS` structure returned from `GlobalMemoryStatus`.</span></span>  
  
 <span data-ttu-id="baeb2-128">ランタイムは、ガベージ コレクターのヒューリスティックとして戻り値を使用します。</span><span class="sxs-lookup"><span data-stu-id="baeb2-128">The runtime uses the return value as a heuristic for the garbage collector.</span></span> <span data-ttu-id="baeb2-129">たとえば、ホストは、メモリの大部分が使用されているレポート、ガベージ コレクターが利用できるメモリの量を増やす複数世代から収集することがあります。</span><span class="sxs-lookup"><span data-stu-id="baeb2-129">For example, if the host reports that the majority of memory is in use, the garbage collector may elect to collect from multiple generations to increase the amount of memory that can potentially become available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="baeb2-130">必要条件</span><span class="sxs-lookup"><span data-stu-id="baeb2-130">Requirements</span></span>  
 <span data-ttu-id="baeb2-131">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="baeb2-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="baeb2-132">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="baeb2-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="baeb2-133">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="baeb2-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="baeb2-134">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="baeb2-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="baeb2-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="baeb2-135">See also</span></span>

- <xref:System.GC?displayProperty=nameWithType>
- [<span data-ttu-id="baeb2-136">IHostMemoryManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="baeb2-136">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
