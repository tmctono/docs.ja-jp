---
title: ICLRRuntimeHost::ExecuteApplication メソッド
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.ExecuteApplication
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::ExecuteApplication
helpviewer_keywords:
- ICLRRuntimeHost::ExecuteApplication method [.NET Framework hosting]
- ExecuteApplication method [.NET Framework hosting]
ms.assetid: 5f28cc4e-7176-4e00-aa1f-58ae6ee52fe4
topic_type:
- apiref
ms.openlocfilehash: 4b56ffab8fb6a9ef70b51421f9cdc5535111e527
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120481"
---
# <a name="iclrruntimehostexecuteapplication-method"></a><span data-ttu-id="dca16-102">ICLRRuntimeHost::ExecuteApplication メソッド</span><span class="sxs-lookup"><span data-stu-id="dca16-102">ICLRRuntimeHost::ExecuteApplication Method</span></span>
<span data-ttu-id="dca16-103">新しいドメインでアクティブ化するアプリケーションを指定するために、マニフェストベースの ClickOnce 配置シナリオで使用されます。</span><span class="sxs-lookup"><span data-stu-id="dca16-103">Used in manifest-based ClickOnce deployment scenarios to specify the application to be activated in a new domain.</span></span> <span data-ttu-id="dca16-104">これらのシナリオの詳細については、「 [ClickOnce のセキュリティと配置](/visualstudio/deployment/clickonce-security-and-deployment)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dca16-104">For more information about these scenarios, see [ClickOnce Security and Deployment](/visualstudio/deployment/clickonce-security-and-deployment).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dca16-105">構文</span><span class="sxs-lookup"><span data-stu-id="dca16-105">Syntax</span></span>  
  
```cpp  
HRESULT ExecuteApplication(  
    [in] LPCWSTR   pwzAppFullName,  
    [in] DWORD     dwManifestPaths,  
    [in] LPCWSTR   *ppwzManifestPaths,  
    [in] DWORD     dwActivationData,  
    [in] LPCWSTR   *ppwzActivationData,  
    [out] int      *pReturnValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dca16-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="dca16-106">Parameters</span></span>  
 `pwzAppFullName`  
 <span data-ttu-id="dca16-107">から<xref:System.ApplicationIdentity>に対して定義されているアプリケーションの完全名。</span><span class="sxs-lookup"><span data-stu-id="dca16-107">[in] The full name of the application, as defined for <xref:System.ApplicationIdentity>.</span></span>  
  
 `dwManifestPaths`  
 <span data-ttu-id="dca16-108">から`ppwzManifestPaths` 配列に格納されている文字列の数。</span><span class="sxs-lookup"><span data-stu-id="dca16-108">[in] The number of strings contained in the `ppwzManifestPaths` array.</span></span>  
  
 `ppwzManifestPaths`  
 <span data-ttu-id="dca16-109">[in] オプション。</span><span class="sxs-lookup"><span data-stu-id="dca16-109">[in] Optional.</span></span> <span data-ttu-id="dca16-110">アプリケーションのマニフェストパスを格納する文字列配列。</span><span class="sxs-lookup"><span data-stu-id="dca16-110">A string array that contains manifest paths for the application.</span></span>  
  
 `dwActivationData`  
 <span data-ttu-id="dca16-111">から`ppwzActivationData` 配列に格納されている文字列の数。</span><span class="sxs-lookup"><span data-stu-id="dca16-111">[in] The number of strings contained in the `ppwzActivationData` array.</span></span>  
  
 `ppwzActivationData`  
 <span data-ttu-id="dca16-112">[in] オプション。</span><span class="sxs-lookup"><span data-stu-id="dca16-112">[in] Optional.</span></span> <span data-ttu-id="dca16-113">Web に配置されたアプリケーションの URL のクエリ文字列部分など、アプリケーションのアクティベーションデータを格納する文字列配列。</span><span class="sxs-lookup"><span data-stu-id="dca16-113">A string array that contains the application's activation data, such as the query string portion of the URL for applications deployed over the Web.</span></span>  
  
 `pReturnValue`  
 <span data-ttu-id="dca16-114">入出力アプリケーションのエントリポイントから返される値。</span><span class="sxs-lookup"><span data-stu-id="dca16-114">[out] The value returned from the entry point of the application.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dca16-115">戻り値</span><span class="sxs-lookup"><span data-stu-id="dca16-115">Return Value</span></span>  
  
|<span data-ttu-id="dca16-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="dca16-116">HRESULT</span></span>|<span data-ttu-id="dca16-117">説明</span><span class="sxs-lookup"><span data-stu-id="dca16-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="dca16-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="dca16-118">S_OK</span></span>|<span data-ttu-id="dca16-119">`ExecuteApplication` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="dca16-119">`ExecuteApplication` returned successfully.</span></span>|  
|<span data-ttu-id="dca16-120">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="dca16-120">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="dca16-121">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="dca16-121">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="dca16-122">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="dca16-122">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="dca16-123">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="dca16-123">The call timed out.</span></span>|  
|<span data-ttu-id="dca16-124">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="dca16-124">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="dca16-125">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="dca16-125">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="dca16-126">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="dca16-126">HOST_E_ABANDONED</span></span>|<span data-ttu-id="dca16-127">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="dca16-127">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="dca16-128">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="dca16-128">E_FAIL</span></span>|<span data-ttu-id="dca16-129">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="dca16-129">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="dca16-130">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="dca16-130">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="dca16-131">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="dca16-131">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dca16-132">Remarks</span><span class="sxs-lookup"><span data-stu-id="dca16-132">Remarks</span></span>  
 <span data-ttu-id="dca16-133">`ExecuteApplication` は、新しく作成されたアプリケーションドメインで ClickOnce アプリケーションをアクティブ化するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="dca16-133">`ExecuteApplication` is used to activate ClickOnce applications in a newly created application domain.</span></span>  
  
 <span data-ttu-id="dca16-134">`pReturnValue` の出力パラメーターは、アプリケーションによって返される値に設定されます。</span><span class="sxs-lookup"><span data-stu-id="dca16-134">The `pReturnValue` output parameter is set to the value returned by the application.</span></span> <span data-ttu-id="dca16-135">`pReturnValue`に null 値を指定した場合、`ExecuteApplication` は失敗しませんが、値は返されません。</span><span class="sxs-lookup"><span data-stu-id="dca16-135">If you supply a value of null for `pReturnValue`, `ExecuteApplication` does not fail, but it does not return a value.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="dca16-136">`ExecuteApplication` メソッドを呼び出してからマニフェストベースのアプリケーションをアクティブ化する前に、 [Start メソッド](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md)メソッドを呼び出さないでください。</span><span class="sxs-lookup"><span data-stu-id="dca16-136">Do not call the [Start Method](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) method before calling the `ExecuteApplication` method to activate a manifest-based application.</span></span> <span data-ttu-id="dca16-137">`Start` メソッドが最初に呼び出された場合、`ExecuteApplication` メソッドの呼び出しは失敗します。</span><span class="sxs-lookup"><span data-stu-id="dca16-137">If the `Start` method is called first, the `ExecuteApplication` method call will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dca16-138">［要件］</span><span class="sxs-lookup"><span data-stu-id="dca16-138">Requirements</span></span>  
 <span data-ttu-id="dca16-139">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dca16-139">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dca16-140">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="dca16-140">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="dca16-141">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="dca16-141">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dca16-142">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dca16-142">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dca16-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="dca16-143">See also</span></span>

- <xref:System.ActivationContext>
- <xref:System.AppDomainManager>
- <xref:System.ApplicationIdentity>
- [<span data-ttu-id="dca16-144">ICLRRuntimeHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="dca16-144">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
- [<span data-ttu-id="dca16-145">SetAppDomainManager メソッド</span><span class="sxs-lookup"><span data-stu-id="dca16-145">SetAppDomainManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-setappdomainmanager-method.md)
- [<span data-ttu-id="dca16-146">チュートリアル : デザイナーを使用し、ClickOnce 配置 API で必要に応じてアセンブリをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="dca16-146">Walkthrough: Downloading Assemblies on Demand with the ClickOnce Deployment API Using the Designer</span></span>](/visualstudio/deployment/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api-using-the-designer)
