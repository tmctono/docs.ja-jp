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
ms.openlocfilehash: 9fd299ad25166bcbcf0202da13a5b4cbdd20d7d7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133803"
---
# <a name="ihostiocompletionmanagerinitializehostoverlapped-method"></a><span data-ttu-id="956f7-102">IHostIoCompletionManager::InitializeHostOverlapped メソッド</span><span class="sxs-lookup"><span data-stu-id="956f7-102">IHostIoCompletionManager::InitializeHostOverlapped Method</span></span>
<span data-ttu-id="956f7-103">非同期 i/o 要求に使用される Win32 `OVERLAPPED` 構造に追加するカスタムデータを初期化する機会をホストに提供します。</span><span class="sxs-lookup"><span data-stu-id="956f7-103">Provides the host with an opportunity to initialize any custom data to append to a Win32 `OVERLAPPED` structure that is used for asynchronous I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="956f7-104">構文</span><span class="sxs-lookup"><span data-stu-id="956f7-104">Syntax</span></span>  
  
```cpp  
HRESULT InitializeHostOverlapped (  
    [in] void* pvOverlapped  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="956f7-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="956f7-105">Parameters</span></span>  
 `pvOverlapped`  
 <span data-ttu-id="956f7-106">からI/o 要求に含める Win32 `OVERLAPPED` 構造体へのポインター。</span><span class="sxs-lookup"><span data-stu-id="956f7-106">[in] A pointer to the Win32 `OVERLAPPED` structure to be included with the I/O request.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="956f7-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="956f7-107">Return Value</span></span>  
  
|<span data-ttu-id="956f7-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="956f7-108">HRESULT</span></span>|<span data-ttu-id="956f7-109">説明</span><span class="sxs-lookup"><span data-stu-id="956f7-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="956f7-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="956f7-110">S_OK</span></span>|<span data-ttu-id="956f7-111">`InitializeHostOverlapped` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="956f7-111">`InitializeHostOverlapped` returned successfully.</span></span>|  
|<span data-ttu-id="956f7-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="956f7-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="956f7-113">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="956f7-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="956f7-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="956f7-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="956f7-115">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="956f7-115">The call timed out.</span></span>|  
|<span data-ttu-id="956f7-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="956f7-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="956f7-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="956f7-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="956f7-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="956f7-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="956f7-119">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="956f7-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="956f7-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="956f7-120">E_FAIL</span></span>|<span data-ttu-id="956f7-121">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="956f7-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="956f7-122">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="956f7-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="956f7-123">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="956f7-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="956f7-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="956f7-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="956f7-125">要求されたリソースを割り当てるのに十分なメモリがありませんでした。</span><span class="sxs-lookup"><span data-stu-id="956f7-125">Not enough memory was available to allocate the requested resource.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="956f7-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="956f7-126">Remarks</span></span>  
 <span data-ttu-id="956f7-127">Windows プラットフォーム関数は、`OVERLAPPED` 構造を使用して、非同期 i/o 要求の状態を格納します。</span><span class="sxs-lookup"><span data-stu-id="956f7-127">The Windows Platform functions use the `OVERLAPPED` structure to store state for asynchronous I/O requests.</span></span> <span data-ttu-id="956f7-128">CLR は、`InitializeHostOverlapped` メソッドを呼び出して、ホストにカスタムデータを `OVERLAPPED` インスタンスに追加する機会を与えます。</span><span class="sxs-lookup"><span data-stu-id="956f7-128">The CLR calls the `InitializeHostOverlapped` method to give the host the opportunity to append custom data to an `OVERLAPPED` instance.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="956f7-129">カスタムデータブロックの先頭に到達するには、ホストでオフセットを `OVERLAPPED` 構造 (`sizeof(OVERLAPPED)`) のサイズに設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="956f7-129">To get to the beginning of their custom data block, hosts must set the offset to the size of the `OVERLAPPED` structure (`sizeof(OVERLAPPED)`).</span></span>  
  
 <span data-ttu-id="956f7-130">戻り値 E_OUTOFMEMORY は、ホストがカスタムデータを初期化できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="956f7-130">A return value of E_OUTOFMEMORY indicates that the host has failed to initialize its custom data.</span></span> <span data-ttu-id="956f7-131">この場合、CLR はエラーを報告し、呼び出しに失敗します。</span><span class="sxs-lookup"><span data-stu-id="956f7-131">In this case, the CLR reports an error and fails the call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="956f7-132">［要件］</span><span class="sxs-lookup"><span data-stu-id="956f7-132">Requirements</span></span>  
 <span data-ttu-id="956f7-133">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="956f7-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="956f7-134">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="956f7-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="956f7-135">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="956f7-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="956f7-136">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="956f7-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="956f7-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="956f7-137">See also</span></span>

- [<span data-ttu-id="956f7-138">ICLRIoCompletionManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="956f7-138">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="956f7-139">GetHostOverlappedSize メソッド</span><span class="sxs-lookup"><span data-stu-id="956f7-139">GetHostOverlappedSize Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-gethostoverlappedsize-method.md)
- [<span data-ttu-id="956f7-140">IHostIoCompletionManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="956f7-140">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
