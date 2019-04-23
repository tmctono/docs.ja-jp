---
title: IHostAutoEvent::Set メソッド
ms.date: 03/30/2017
api_name:
- IHostAutoEvent.Set
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAutoEvent::Set
helpviewer_keywords:
- Set method, IHostAutoEvent interface [.NET Framework hosting]
- IHostAutoEvent::Set method [.NET Framework hosting]
ms.assetid: 46becf3e-bc0e-4338-85c0-9ab0df76a1d0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5af9f55bdcfe23f0b2a051b33cb1280f312820a7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59227016"
---
# <a name="ihostautoeventset-method"></a><span data-ttu-id="02a7e-102">IHostAutoEvent::Set メソッド</span><span class="sxs-lookup"><span data-stu-id="02a7e-102">IHostAutoEvent::Set Method</span></span>
<span data-ttu-id="02a7e-103">現在の設定[IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)インスタンスがシグナル状態にします。</span><span class="sxs-lookup"><span data-stu-id="02a7e-103">Sets the current [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) instance to a signaled state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02a7e-104">構文</span><span class="sxs-lookup"><span data-stu-id="02a7e-104">Syntax</span></span>  
  
```  
HRESULT Set ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="02a7e-105">戻り値</span><span class="sxs-lookup"><span data-stu-id="02a7e-105">Return Value</span></span>  
  
|<span data-ttu-id="02a7e-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="02a7e-106">HRESULT</span></span>|<span data-ttu-id="02a7e-107">説明</span><span class="sxs-lookup"><span data-stu-id="02a7e-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="02a7e-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="02a7e-108">S_OK</span></span>|<span data-ttu-id="02a7e-109">`Set` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="02a7e-109">`Set` returned successfully.</span></span>|  
|<span data-ttu-id="02a7e-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="02a7e-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="02a7e-111">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="02a7e-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="02a7e-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="02a7e-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="02a7e-113">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="02a7e-113">The call timed out.</span></span>|  
|<span data-ttu-id="02a7e-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="02a7e-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="02a7e-115">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="02a7e-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="02a7e-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="02a7e-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="02a7e-117">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="02a7e-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="02a7e-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="02a7e-118">E_FAIL</span></span>|<span data-ttu-id="02a7e-119">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="02a7e-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="02a7e-120">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="02a7e-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="02a7e-121">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="02a7e-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="02a7e-122">必要条件</span><span class="sxs-lookup"><span data-stu-id="02a7e-122">Requirements</span></span>  
 <span data-ttu-id="02a7e-123">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="02a7e-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02a7e-124">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="02a7e-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="02a7e-125">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="02a7e-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="02a7e-126">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02a7e-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02a7e-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="02a7e-127">See also</span></span>

- [<span data-ttu-id="02a7e-128">ICLRSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="02a7e-128">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="02a7e-129">IHostAutoEvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="02a7e-129">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="02a7e-130">IHostManualEvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="02a7e-130">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="02a7e-131">IHostSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="02a7e-131">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
