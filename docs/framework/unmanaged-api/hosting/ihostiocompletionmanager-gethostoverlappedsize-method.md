---
title: IHostIoCompletionManager::GetHostOverlappedSize メソッド
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.GetHostOverlappedSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::GetHostOverlappedSize
helpviewer_keywords:
- IHostIoCompletionManager::GetHostOverlappedSize method [.NET Framework hosting]
- GetHostOverlappedSize method [.NET Framework hosting]
ms.assetid: 2902578b-d5e2-4f8d-a103-0c7b6dceda9e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c43f906961b9e76d5f0f34ba5a5b2f656f5b1488
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937515"
---
# <a name="ihostiocompletionmanagergethostoverlappedsize-method"></a><span data-ttu-id="11e58-102">IHostIoCompletionManager::GetHostOverlappedSize メソッド</span><span class="sxs-lookup"><span data-stu-id="11e58-102">IHostIoCompletionManager::GetHostOverlappedSize Method</span></span>
<span data-ttu-id="11e58-103">ホストが i/o 要求に追加しようとしているカスタムデータのサイズを取得します。</span><span class="sxs-lookup"><span data-stu-id="11e58-103">Gets the size of any custom data the host intends to append to I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11e58-104">構文</span><span class="sxs-lookup"><span data-stu-id="11e58-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHostOverlappedSize (  
    [out] DWORD *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="11e58-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="11e58-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="11e58-106">入出力Win32 `OVERLAPPED`オブジェクトのサイズに加えて、共通言語ランタイム (CLR: common language runtime) によって割り当てられるバイト数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="11e58-106">[out] A pointer to the number of bytes that the common language runtime (CLR) should allocate in addition to the size of the Win32 `OVERLAPPED` object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="11e58-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="11e58-107">Return Value</span></span>  
  
|<span data-ttu-id="11e58-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="11e58-108">HRESULT</span></span>|<span data-ttu-id="11e58-109">説明</span><span class="sxs-lookup"><span data-stu-id="11e58-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="11e58-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="11e58-110">S_OK</span></span>|<span data-ttu-id="11e58-111">`GetHostOverlappedSize`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="11e58-111">`GetHostOverlappedSize` returned successfully.</span></span>|  
|<span data-ttu-id="11e58-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="11e58-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="11e58-113">CLR がプロセスに読み込まれていないか、CLR がマネージドコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="11e58-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="11e58-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="11e58-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="11e58-115">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="11e58-115">The call timed out.</span></span>|  
|<span data-ttu-id="11e58-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="11e58-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="11e58-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="11e58-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="11e58-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="11e58-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="11e58-119">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="11e58-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="11e58-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="11e58-120">E_FAIL</span></span>|<span data-ttu-id="11e58-121">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="11e58-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="11e58-122">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="11e58-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="11e58-123">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="11e58-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="11e58-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="11e58-124">Remarks</span></span>  
 <span data-ttu-id="11e58-125">Windows プラットフォーム api に対するすべての非同期 i/o 呼び出しは、ファイル`OVERLAPPED`ポインターの位置などの情報を提供する Win32 オブジェクトを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="11e58-125">All asynchronous I/O calls to Windows Platform APIs take a Win32 `OVERLAPPED` object, which provides information such as the file pointer position.</span></span> <span data-ttu-id="11e58-126">状態を維持するために、非同期 i/o 呼び出しを行うアプリケーションは、通常、カスタムデータを構造に追加します。</span><span class="sxs-lookup"><span data-stu-id="11e58-126">To maintain state, applications that make asynchronous I/O calls typically add custom data to the structure.</span></span> <span data-ttu-id="11e58-127">`GetHostOverlappedSize`と[Iho、O補完 manager:: InitializeHostOverlapped](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-initializehostoverlapped-method.md)は、このようなカスタムデータをホストに含める機会を提供します。</span><span class="sxs-lookup"><span data-stu-id="11e58-127">`GetHostOverlappedSize` and [IHostIoCompletionManager::InitializeHostOverlapped](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-initializehostoverlapped-method.md) provide an opportunity for the host to include such custom data.</span></span>  
  
 <span data-ttu-id="11e58-128">CLR は、 `GetHostOverlappedSize`メソッドを呼び出して、ホストが`OVERLAPPED`オブジェクトに追加するカスタムデータのサイズを決定します。</span><span class="sxs-lookup"><span data-stu-id="11e58-128">The CLR calls the `GetHostOverlappedSize` method to determine the size of the custom data that the host intends to append to the `OVERLAPPED` object.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="11e58-129">`GetHostOverlappedSize`は1回だけ呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="11e58-129">`GetHostOverlappedSize` is called only once.</span></span> <span data-ttu-id="11e58-130">ホストのカスタムデータは、すべての i/o 要求に対して同じサイズである必要があります。</span><span class="sxs-lookup"><span data-stu-id="11e58-130">The host's custom data must be the same size for every I/O request.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="11e58-131">`OVERLAPPED`オブジェクト自体のサイズは、の`pcbSize`値には含まれません。</span><span class="sxs-lookup"><span data-stu-id="11e58-131">The size of the `OVERLAPPED` object itself is not included in the value of `pcbSize`.</span></span>  
  
 <span data-ttu-id="11e58-132">構造体の`OVERLAPPED`詳細については、Windows プラットフォームのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="11e58-132">For more information about the `OVERLAPPED` structure, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11e58-133">必要条件</span><span class="sxs-lookup"><span data-stu-id="11e58-133">Requirements</span></span>  
 <span data-ttu-id="11e58-134">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="11e58-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11e58-135">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="11e58-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="11e58-136">**ライブラリ**Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="11e58-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="11e58-137">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11e58-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11e58-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="11e58-138">See also</span></span>

- <xref:System.Threading.NativeOverlapped>
- [<span data-ttu-id="11e58-139">ICLRIoCompletionManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="11e58-139">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="11e58-140">IHostIoCompletionManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="11e58-140">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
