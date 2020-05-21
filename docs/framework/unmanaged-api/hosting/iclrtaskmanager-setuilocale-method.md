---
title: ICLRTaskManager::SetUILocale メソッド
ms.date: 03/30/2017
api_name:
- ICLRTaskManager.SetUILocale
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTaskManager::SetUILocale
helpviewer_keywords:
- ICLRTaskManager::SetUILocale method [.NET Framework hosting]
- SetUILocale method, ICLRTaskManager interface [.NET Framework hosting]
ms.assetid: 03adaa9a-2beb-49b3-b2c4-6b4fc3f10715
topic_type:
- apiref
ms.openlocfilehash: e6ab7c7af1cf9f30f6708c4e970db619ca071343
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762774"
---
# <a name="iclrtaskmanagersetuilocale-method"></a><span data-ttu-id="e6694-102">ICLRTaskManager::SetUILocale メソッド</span><span class="sxs-lookup"><span data-stu-id="e6694-102">ICLRTaskManager::SetUILocale Method</span></span>
<span data-ttu-id="e6694-103">現在実行中のタスクのユーザーインターフェイス (UI) ロケール (カルチャ) がホストによって変更されたことを、共通言語ランタイム (CLR) に通知します。</span><span class="sxs-lookup"><span data-stu-id="e6694-103">Notifies the common language runtime (CLR) that the host has modified the user interface (UI) locale, or culture, on the currently executing task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6694-104">構文</span><span class="sxs-lookup"><span data-stu-id="e6694-104">Syntax</span></span>  
  
```cpp  
HRESULT SetUILocale (  
    [in] LCID lcid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e6694-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e6694-105">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="e6694-106">から新しく割り当てられた地理的カルチャとユーザーインターフェイスの言語にマップされるロケール識別子の値。</span><span class="sxs-lookup"><span data-stu-id="e6694-106">[in] The locale identifier value that maps to the newly assigned geographical culture and language for the user interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e6694-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="e6694-107">Return Value</span></span>  
  
|<span data-ttu-id="e6694-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e6694-108">HRESULT</span></span>|<span data-ttu-id="e6694-109">説明</span><span class="sxs-lookup"><span data-stu-id="e6694-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e6694-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="e6694-110">S_OK</span></span>|<span data-ttu-id="e6694-111">`SetUILocale`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="e6694-111">`SetUILocale` returned successfully.</span></span>|  
|<span data-ttu-id="e6694-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e6694-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e6694-113">CLR がプロセスに読み込まれていないか、CLR がマネージドコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="e6694-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e6694-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e6694-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e6694-115">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="e6694-115">The call timed out.</span></span>|  
|<span data-ttu-id="e6694-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e6694-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e6694-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="e6694-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e6694-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e6694-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e6694-119">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="e6694-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e6694-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e6694-120">E_FAIL</span></span>|<span data-ttu-id="e6694-121">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="e6694-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e6694-122">メソッドが E_FAIL を返すと、そのプロセス内で CLR が使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="e6694-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e6694-123">後続のホストメソッドの呼び出しでは HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="e6694-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e6694-124">解説</span><span class="sxs-lookup"><span data-stu-id="e6694-124">Remarks</span></span>  
 <span data-ttu-id="e6694-125">`SetUILocale`ロケールの同期に必要なメカニズムをホストが実行する機会を提供します。</span><span class="sxs-lookup"><span data-stu-id="e6694-125">`SetUILocale` provides an opportunity for the host to execute any mechanisms it might have for the synchronization of locales.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6694-126">要件</span><span class="sxs-lookup"><span data-stu-id="e6694-126">Requirements</span></span>  
 <span data-ttu-id="e6694-127">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e6694-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6694-128">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="e6694-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e6694-129">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="e6694-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e6694-130">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6694-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6694-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="e6694-131">See also</span></span>

- [<span data-ttu-id="e6694-132">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e6694-132">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="e6694-133">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e6694-133">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="e6694-134">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e6694-134">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="e6694-135">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e6694-135">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
