---
title: ICLRRuntimeHost::UnloadAppDomain メソッド
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.UnloadAppDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::UnloadAppDomain
helpviewer_keywords:
- ICLRRuntimeHost::UnloadAppDomain method [.NET Framework hosting]
- UnloadAppDomain method [.NET Framework hosting]
ms.assetid: 571912bc-3429-4ff8-8eb2-ea993ffbd901
topic_type:
- apiref
ms.openlocfilehash: 2a6dc878f156d5d18970fed72c9722bab60f9ba8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120404"
---
# <a name="iclrruntimehostunloadappdomain-method"></a><span data-ttu-id="5d031-102">ICLRRuntimeHost::UnloadAppDomain メソッド</span><span class="sxs-lookup"><span data-stu-id="5d031-102">ICLRRuntimeHost::UnloadAppDomain Method</span></span>
<span data-ttu-id="5d031-103">指定した数値識別子に対応するマネージ <xref:System.AppDomain> をアンロードします。</span><span class="sxs-lookup"><span data-stu-id="5d031-103">Unloads the managed <xref:System.AppDomain> that corresponds to the specified numeric identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d031-104">構文</span><span class="sxs-lookup"><span data-stu-id="5d031-104">Syntax</span></span>  
  
```cpp  
HRESULT UnloadAppDomain(  
    [in] DWORD dwAppDomainId  
    [in] BOOL  fWaitUntilDone  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5d031-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5d031-105">Parameters</span></span>  
 `dwAppDomainId`  
 <span data-ttu-id="5d031-106">からアンロードするアプリケーションドメインの数値識別子。</span><span class="sxs-lookup"><span data-stu-id="5d031-106">[in] The numeric identifier of the application domain to unload.</span></span>  
  
 `fWaitUntilDone`  
 <span data-ttu-id="5d031-107">[in] アプリケーションドメインのアンロードを試行する前に、共通言語ランタイム (CLR) がアプリケーションの現在のスレッドの実行を完了するまで待機する必要があることを示す `true` ます。</span><span class="sxs-lookup"><span data-stu-id="5d031-107">[in] `true` to indicate that the common language runtime( CLR) must wait until it has finished executing the application's current thread before attempting to unload the application domain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5d031-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="5d031-108">Return Value</span></span>  
  
|<span data-ttu-id="5d031-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5d031-109">HRESULT</span></span>|<span data-ttu-id="5d031-110">説明</span><span class="sxs-lookup"><span data-stu-id="5d031-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5d031-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="5d031-111">S_OK</span></span>|<span data-ttu-id="5d031-112">`UnloadAppDomain` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="5d031-112">`UnloadAppDomain` returned successfully.</span></span>|  
|<span data-ttu-id="5d031-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5d031-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5d031-114">CLR がプロセスに読み込まれていないか、CLR がマネージドコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="5d031-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5d031-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5d031-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5d031-116">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="5d031-116">The call timed out.</span></span>|  
|<span data-ttu-id="5d031-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5d031-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5d031-118">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="5d031-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5d031-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5d031-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5d031-120">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="5d031-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5d031-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5d031-121">E_FAIL</span></span>|<span data-ttu-id="5d031-122">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="5d031-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5d031-123">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="5d031-123">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5d031-124">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="5d031-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5d031-125">Remarks</span><span class="sxs-lookup"><span data-stu-id="5d031-125">Remarks</span></span>  
 <span data-ttu-id="5d031-126">[GetCurrentAppDomainId](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md)を呼び出すことにより、現在のスレッドが実行されているアプリケーションドメインの数値識別子を取得できます。</span><span class="sxs-lookup"><span data-stu-id="5d031-126">You can get the numeric identifier of the application domain in which the current thread is executing by calling [GetCurrentAppDomainId](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md).</span></span> <span data-ttu-id="5d031-127">この識別子は、マネージ <xref:System.AppDomain> 型の <xref:System.AppDomain.Id%2A> プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="5d031-127">This identifier corresponds to the <xref:System.AppDomain.Id%2A> property of the managed <xref:System.AppDomain> type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d031-128">［要件］</span><span class="sxs-lookup"><span data-stu-id="5d031-128">Requirements</span></span>  
 <span data-ttu-id="5d031-129">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d031-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d031-130">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="5d031-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5d031-131">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="5d031-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5d031-132">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d031-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d031-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="5d031-133">See also</span></span>

- [<span data-ttu-id="5d031-134">ICLRRuntimeHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5d031-134">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
