---
title: IHostIoCompletionManager::InitializeHostOverlapped メソッド
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.InitializeHostOverlapped
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::InitializeHostOverlapped
helpviewer_keywords:
- IHostIoCompletionManager::InitializeHostOverlapped method [.NET Framework hosting]
- InitializeHostOverlapped method [.NET Framework hosting]
ms.assetid: c35199bf-bc47-4901-b467-4e8a37644bbb
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1dea19a13cd2c741a24695b293ae1c8621ad5688
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59157671"
---
# <a name="ihostiocompletionmanagerinitializehostoverlapped-method"></a><span data-ttu-id="9aea6-102">IHostIoCompletionManager::InitializeHostOverlapped メソッド</span><span class="sxs-lookup"><span data-stu-id="9aea6-102">IHostIoCompletionManager::InitializeHostOverlapped Method</span></span>
<span data-ttu-id="9aea6-103">Win32 に追加するカスタム データを初期化する機会をホストを提供します。`OVERLAPPED`非同期 I/O 要求に使用される構造体。</span><span class="sxs-lookup"><span data-stu-id="9aea6-103">Provides the host with an opportunity to initialize any custom data to append to a Win32 `OVERLAPPED` structure that is used for asynchronous I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9aea6-104">構文</span><span class="sxs-lookup"><span data-stu-id="9aea6-104">Syntax</span></span>  
  
```  
HRESULT InitializeHostOverlapped (  
    [in] void* pvOverlapped  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9aea6-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9aea6-105">Parameters</span></span>  
 `pvOverlapped`  
 <span data-ttu-id="9aea6-106">[in]Win32 へのポインター`OVERLAPPED`構造体が I/O 要求に含まれています。</span><span class="sxs-lookup"><span data-stu-id="9aea6-106">[in] A pointer to the Win32 `OVERLAPPED` structure to be included with the I/O request.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9aea6-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="9aea6-107">Return Value</span></span>  
  
|<span data-ttu-id="9aea6-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9aea6-108">HRESULT</span></span>|<span data-ttu-id="9aea6-109">説明</span><span class="sxs-lookup"><span data-stu-id="9aea6-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9aea6-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="9aea6-110">S_OK</span></span>|`InitializeHostOverlapped` <span data-ttu-id="9aea6-111">正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="9aea6-111">returned successfully.</span></span>|  
|<span data-ttu-id="9aea6-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9aea6-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9aea6-113">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="9aea6-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9aea6-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9aea6-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9aea6-115">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="9aea6-115">The call timed out.</span></span>|  
|<span data-ttu-id="9aea6-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9aea6-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9aea6-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="9aea6-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9aea6-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9aea6-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9aea6-119">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="9aea6-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9aea6-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9aea6-120">E_FAIL</span></span>|<span data-ttu-id="9aea6-121">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="9aea6-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9aea6-122">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="9aea6-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9aea6-123">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="9aea6-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="9aea6-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="9aea6-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="9aea6-125">メモリが不足していますが、要求されたリソースを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="9aea6-125">Not enough memory was available to allocate the requested resource.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9aea6-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="9aea6-126">Remarks</span></span>  
 <span data-ttu-id="9aea6-127">Windows プラットフォームの機能の使用、`OVERLAPPED`非同期 I/O 要求の状態を格納する構造体。</span><span class="sxs-lookup"><span data-stu-id="9aea6-127">The Windows Platform functions use the `OVERLAPPED` structure to store state for asynchronous I/O requests.</span></span> <span data-ttu-id="9aea6-128">CLR の呼び出し、`InitializeHostOverlapped`ホストにカスタム データを追加する機会を提供するメソッド、`OVERLAPPED`インスタンス。</span><span class="sxs-lookup"><span data-stu-id="9aea6-128">The CLR calls the `InitializeHostOverlapped` method to give the host the opportunity to append custom data to an `OVERLAPPED` instance.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="9aea6-129">を、カスタム データ ブロックの先頭を取得するホストは、のサイズにオフセットを設定する必要があります、`OVERLAPPED`構造 (`sizeof(OVERLAPPED)`)。</span><span class="sxs-lookup"><span data-stu-id="9aea6-129">To get to the beginning of their custom data block, hosts must set the offset to the size of the `OVERLAPPED` structure (`sizeof(OVERLAPPED)`).</span></span>  
  
 <span data-ttu-id="9aea6-130">E_OUTOFMEMORY の戻り値は、ホストがそのカスタム データの初期化に失敗したことを示します。</span><span class="sxs-lookup"><span data-stu-id="9aea6-130">A return value of E_OUTOFMEMORY indicates that the host has failed to initialize its custom data.</span></span> <span data-ttu-id="9aea6-131">この場合、CLR では、エラーが報告され、呼び出しが失敗します。</span><span class="sxs-lookup"><span data-stu-id="9aea6-131">In this case, the CLR reports an error and fails the call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9aea6-132">必要条件</span><span class="sxs-lookup"><span data-stu-id="9aea6-132">Requirements</span></span>  
 <span data-ttu-id="9aea6-133">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9aea6-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9aea6-134">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9aea6-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9aea6-135">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="9aea6-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="9aea6-136">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="9aea6-136">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9aea6-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="9aea6-137">See also</span></span>

- [<span data-ttu-id="9aea6-138">ICLRIoCompletionManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9aea6-138">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="9aea6-139">GetHostOverlappedSize メソッド</span><span class="sxs-lookup"><span data-stu-id="9aea6-139">GetHostOverlappedSize Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-gethostoverlappedsize-method.md)
- [<span data-ttu-id="9aea6-140">IHostIoCompletionManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9aea6-140">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
