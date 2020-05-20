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
ms.openlocfilehash: 293c1764f4c0d857138726b8ed4855b1e3b03116
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703923"
---
# <a name="iclrruntimehostunloadappdomain-method"></a><span data-ttu-id="74761-102">ICLRRuntimeHost::UnloadAppDomain メソッド</span><span class="sxs-lookup"><span data-stu-id="74761-102">ICLRRuntimeHost::UnloadAppDomain Method</span></span>
<span data-ttu-id="74761-103"><xref:System.AppDomain>指定した数値識別子に対応するマネージをアンロードします。</span><span class="sxs-lookup"><span data-stu-id="74761-103">Unloads the managed <xref:System.AppDomain> that corresponds to the specified numeric identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74761-104">構文</span><span class="sxs-lookup"><span data-stu-id="74761-104">Syntax</span></span>  
  
```cpp  
HRESULT UnloadAppDomain(  
    [in] DWORD dwAppDomainId  
    [in] BOOL  fWaitUntilDone  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="74761-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="74761-105">Parameters</span></span>  
 `dwAppDomainId`  
 <span data-ttu-id="74761-106">からアンロードするアプリケーションドメインの数値識別子。</span><span class="sxs-lookup"><span data-stu-id="74761-106">[in] The numeric identifier of the application domain to unload.</span></span>  
  
 `fWaitUntilDone`  
 <span data-ttu-id="74761-107">[入力] `true`アプリケーションドメインのアンロードを試行する前に、共通言語ランタイム (CLR) がアプリケーションの現在のスレッドの実行を完了するまで待機する必要があることを示す場合は。</span><span class="sxs-lookup"><span data-stu-id="74761-107">[in] `true` to indicate that the common language runtime( CLR) must wait until it has finished executing the application's current thread before attempting to unload the application domain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="74761-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="74761-108">Return Value</span></span>  
  
|<span data-ttu-id="74761-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="74761-109">HRESULT</span></span>|<span data-ttu-id="74761-110">説明</span><span class="sxs-lookup"><span data-stu-id="74761-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="74761-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="74761-111">S_OK</span></span>|<span data-ttu-id="74761-112">`UnloadAppDomain`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="74761-112">`UnloadAppDomain` returned successfully.</span></span>|  
|<span data-ttu-id="74761-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="74761-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="74761-114">CLR がプロセスに読み込まれていないか、CLR がマネージドコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="74761-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="74761-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="74761-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="74761-116">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="74761-116">The call timed out.</span></span>|  
|<span data-ttu-id="74761-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="74761-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="74761-118">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="74761-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="74761-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="74761-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="74761-120">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="74761-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="74761-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="74761-121">E_FAIL</span></span>|<span data-ttu-id="74761-122">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="74761-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="74761-123">メソッドが E_FAIL を返す場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="74761-123">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="74761-124">後続のホストメソッドの呼び出しでは HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="74761-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="74761-125">解説</span><span class="sxs-lookup"><span data-stu-id="74761-125">Remarks</span></span>  
 <span data-ttu-id="74761-126">[GetCurrentAppDomainId](iclrruntimehost-getcurrentappdomainid-method.md)を呼び出すことにより、現在のスレッドが実行されているアプリケーションドメインの数値識別子を取得できます。</span><span class="sxs-lookup"><span data-stu-id="74761-126">You can get the numeric identifier of the application domain in which the current thread is executing by calling [GetCurrentAppDomainId](iclrruntimehost-getcurrentappdomainid-method.md).</span></span> <span data-ttu-id="74761-127">この識別子は <xref:System.AppDomain.Id%2A> 、マネージ型のプロパティに対応 <xref:System.AppDomain> しています。</span><span class="sxs-lookup"><span data-stu-id="74761-127">This identifier corresponds to the <xref:System.AppDomain.Id%2A> property of the managed <xref:System.AppDomain> type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74761-128">要件</span><span class="sxs-lookup"><span data-stu-id="74761-128">Requirements</span></span>  
 <span data-ttu-id="74761-129">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="74761-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74761-130">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="74761-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="74761-131">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="74761-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="74761-132">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74761-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74761-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="74761-133">See also</span></span>

- [<span data-ttu-id="74761-134">ICLRRuntimeHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="74761-134">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)
