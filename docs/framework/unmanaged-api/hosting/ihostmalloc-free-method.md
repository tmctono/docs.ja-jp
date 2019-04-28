---
title: IHostMAlloc::Free メソッド
ms.date: 03/30/2017
api_name:
- IHostMAlloc.Free
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMAlloc::Free
helpviewer_keywords:
- IHostMAlloc::Free method [.NET Framework hosting]
- Free method, IHostMAlloc interface [.NET Framework hosting]
ms.assetid: c89abf5b-1120-4437-8b57-4a99fb3ae7f9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 21342af13f9d77ebab979102172e1a2c28402273
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61796716"
---
# <a name="ihostmallocfree-method"></a><span data-ttu-id="81b41-102">IHostMAlloc::Free メソッド</span><span class="sxs-lookup"><span data-stu-id="81b41-102">IHostMAlloc::Free Method</span></span>
<span data-ttu-id="81b41-103">使用して割り当てられたメモリを解放、[アロケーション](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-alloc-method.md)関数。</span><span class="sxs-lookup"><span data-stu-id="81b41-103">Frees memory that was allocated by using the [Alloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-alloc-method.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81b41-104">構文</span><span class="sxs-lookup"><span data-stu-id="81b41-104">Syntax</span></span>  
  
```  
HRESULT Free (  
    [in] void* pMem  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="81b41-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="81b41-105">Parameters</span></span>  
 `pMem`  
 <span data-ttu-id="81b41-106">[in]解放するメモリへのポインター。</span><span class="sxs-lookup"><span data-stu-id="81b41-106">[in] A pointer to the memory to be freed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="81b41-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="81b41-107">Return Value</span></span>  
  
|<span data-ttu-id="81b41-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="81b41-108">HRESULT</span></span>|<span data-ttu-id="81b41-109">説明</span><span class="sxs-lookup"><span data-stu-id="81b41-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="81b41-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="81b41-110">S_OK</span></span>|<span data-ttu-id="81b41-111">`Free` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="81b41-111">`Free` returned successfully.</span></span>|  
|<span data-ttu-id="81b41-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="81b41-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="81b41-113">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="81b41-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="81b41-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="81b41-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="81b41-115">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="81b41-115">The call timed out.</span></span>|  
|<span data-ttu-id="81b41-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="81b41-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="81b41-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="81b41-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="81b41-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="81b41-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="81b41-119">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="81b41-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="81b41-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="81b41-120">E_FAIL</span></span>|<span data-ttu-id="81b41-121">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="81b41-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="81b41-122">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="81b41-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="81b41-123">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="81b41-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="81b41-124">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="81b41-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="81b41-125">ホストを通じて割り当てられていないメモリを解放しようとしました。</span><span class="sxs-lookup"><span data-stu-id="81b41-125">An attempt was made to free memory that was not allocated through the host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="81b41-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="81b41-126">Remarks</span></span>  
 <span data-ttu-id="81b41-127">場合、`pMem`パラメーターへの呼び出しを使用して割り当てられていないメモリの領域を指す`Alloc`ホストは HOST_E_INVALIDOPERATION を返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="81b41-127">If the `pMem` parameter refers to a region of memory that was not allocated by using a call to `Alloc`, the host should return HOST_E_INVALIDOPERATION.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="81b41-128">必要条件</span><span class="sxs-lookup"><span data-stu-id="81b41-128">Requirements</span></span>  
 <span data-ttu-id="81b41-129">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="81b41-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81b41-130">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="81b41-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="81b41-131">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="81b41-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="81b41-132">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81b41-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81b41-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="81b41-133">See also</span></span>

- [<span data-ttu-id="81b41-134">IHostMemoryManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="81b41-134">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="81b41-135">IHostMalloc インターフェイス</span><span class="sxs-lookup"><span data-stu-id="81b41-135">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
