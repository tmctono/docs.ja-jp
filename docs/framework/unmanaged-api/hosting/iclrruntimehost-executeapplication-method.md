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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8ce7e9ff4041abd1e89330bd3a565b755875d3b2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59194228"
---
# <a name="iclrruntimehostexecuteapplication-method"></a><span data-ttu-id="d003d-102">ICLRRuntimeHost::ExecuteApplication メソッド</span><span class="sxs-lookup"><span data-stu-id="d003d-102">ICLRRuntimeHost::ExecuteApplication Method</span></span>
<span data-ttu-id="d003d-103">マニフェスト ベースの ClickOnce 配置のシナリオで使用すると、新しいドメインでアクティブ化するアプリケーションを指定します。</span><span class="sxs-lookup"><span data-stu-id="d003d-103">Used in manifest-based ClickOnce deployment scenarios to specify the application to be activated in a new domain.</span></span> <span data-ttu-id="d003d-104">これらのシナリオの詳細については、次を参照してください。 [ClickOnce Security and Deployment](/visualstudio/deployment/clickonce-security-and-deployment)します。</span><span class="sxs-lookup"><span data-stu-id="d003d-104">For more information about these scenarios, see [ClickOnce Security and Deployment](/visualstudio/deployment/clickonce-security-and-deployment).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d003d-105">構文</span><span class="sxs-lookup"><span data-stu-id="d003d-105">Syntax</span></span>  
  
```  
HRESULT ExecuteApplication(  
    [in] LPCWSTR   pwzAppFullName,  
    [in] DWORD     dwManifestPaths,  
    [in] LPCWSTR   *ppwzManifestPaths,  
    [in] DWORD     dwActivationData,  
    [in] LPCWSTR   *ppwzActivationData,  
    [out] int      *pReturnValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d003d-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d003d-106">Parameters</span></span>  
 `pwzAppFullName`  
 <span data-ttu-id="d003d-107">[in]に対して定義されている、アプリケーションの完全名<xref:System.ApplicationIdentity>します。</span><span class="sxs-lookup"><span data-stu-id="d003d-107">[in] The full name of the application, as defined for <xref:System.ApplicationIdentity>.</span></span>  
  
 `dwManifestPaths`  
 <span data-ttu-id="d003d-108">[in]含まれる文字列の数、`ppwzManifestPaths`配列。</span><span class="sxs-lookup"><span data-stu-id="d003d-108">[in] The number of strings contained in the `ppwzManifestPaths` array.</span></span>  
  
 `ppwzManifestPaths`  
 <span data-ttu-id="d003d-109">[in] オプション。</span><span class="sxs-lookup"><span data-stu-id="d003d-109">[in] Optional.</span></span> <span data-ttu-id="d003d-110">アプリケーションのマニフェストのパスを含む文字列配列。</span><span class="sxs-lookup"><span data-stu-id="d003d-110">A string array that contains manifest paths for the application.</span></span>  
  
 `dwActivationData`  
 <span data-ttu-id="d003d-111">[in]含まれる文字列の数、`ppwzActivationData`配列。</span><span class="sxs-lookup"><span data-stu-id="d003d-111">[in] The number of strings contained in the `ppwzActivationData` array.</span></span>  
  
 `ppwzActivationData`  
 <span data-ttu-id="d003d-112">[in] オプション。</span><span class="sxs-lookup"><span data-stu-id="d003d-112">[in] Optional.</span></span> <span data-ttu-id="d003d-113">Web 経由でデプロイされたアプリケーションの URL のクエリ文字列部分などのアプリケーションのアクティベーション データを含む文字列配列。</span><span class="sxs-lookup"><span data-stu-id="d003d-113">A string array that contains the application's activation data, such as the query string portion of the URL for applications deployed over the Web.</span></span>  
  
 `pReturnValue`  
 <span data-ttu-id="d003d-114">[out]アプリケーションのエントリ ポイントから返される値。</span><span class="sxs-lookup"><span data-stu-id="d003d-114">[out] The value returned from the entry point of the application.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d003d-115">戻り値</span><span class="sxs-lookup"><span data-stu-id="d003d-115">Return Value</span></span>  
  
|<span data-ttu-id="d003d-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d003d-116">HRESULT</span></span>|<span data-ttu-id="d003d-117">説明</span><span class="sxs-lookup"><span data-stu-id="d003d-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d003d-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="d003d-118">S_OK</span></span>|<span data-ttu-id="d003d-119">`ExecuteApplication` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="d003d-119">`ExecuteApplication` returned successfully.</span></span>|  
|<span data-ttu-id="d003d-120">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d003d-120">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d003d-121">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="d003d-121">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d003d-122">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d003d-122">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d003d-123">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="d003d-123">The call timed out.</span></span>|  
|<span data-ttu-id="d003d-124">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d003d-124">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d003d-125">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="d003d-125">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d003d-126">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d003d-126">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d003d-127">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="d003d-127">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d003d-128">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d003d-128">E_FAIL</span></span>|<span data-ttu-id="d003d-129">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="d003d-129">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d003d-130">メソッドから E_FAIL が返された場合、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="d003d-130">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d003d-131">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="d003d-131">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d003d-132">Remarks</span><span class="sxs-lookup"><span data-stu-id="d003d-132">Remarks</span></span>  
 <span data-ttu-id="d003d-133">`ExecuteApplication` 新しく作成されたアプリケーション ドメインで ClickOnce アプリケーションをアクティブ化に使用されます。</span><span class="sxs-lookup"><span data-stu-id="d003d-133">`ExecuteApplication` is used to activate ClickOnce applications in a newly created application domain.</span></span>  
  
 <span data-ttu-id="d003d-134">`pReturnValue`出力パラメーターが、アプリケーションによって返される値に設定します。</span><span class="sxs-lookup"><span data-stu-id="d003d-134">The `pReturnValue` output parameter is set to the value returned by the application.</span></span> <span data-ttu-id="d003d-135">場合は null の値を指定する場合`pReturnValue`、`ExecuteApplication`失敗しませんが、値を返さない。</span><span class="sxs-lookup"><span data-stu-id="d003d-135">If you supply a value of null for `pReturnValue`, `ExecuteApplication` does not fail, but it does not return a value.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d003d-136">呼び出すのではない、 [Start メソッド](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md)メソッドを呼び出す前に、`ExecuteApplication`マニフェスト ベースのアプリケーションをアクティブ化するメソッド。</span><span class="sxs-lookup"><span data-stu-id="d003d-136">Do not call the [Start Method](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) method before calling the `ExecuteApplication` method to activate a manifest-based application.</span></span> <span data-ttu-id="d003d-137">場合、`Start`メソッドが最初に、呼び出された、`ExecuteApplication`メソッドの呼び出しが失敗します。</span><span class="sxs-lookup"><span data-stu-id="d003d-137">If the `Start` method is called first, the `ExecuteApplication` method call will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d003d-138">必要条件</span><span class="sxs-lookup"><span data-stu-id="d003d-138">Requirements</span></span>  
 <span data-ttu-id="d003d-139">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d003d-139">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d003d-140">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d003d-140">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d003d-141">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="d003d-141">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d003d-142">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d003d-142">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d003d-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="d003d-143">See also</span></span>

- <xref:System.ActivationContext>
- <xref:System.AppDomainManager>
- <xref:System.ApplicationIdentity>
- [<span data-ttu-id="d003d-144">ICLRRuntimeHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d003d-144">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
- [<span data-ttu-id="d003d-145">SetAppDomainManager メソッド</span><span class="sxs-lookup"><span data-stu-id="d003d-145">SetAppDomainManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-setappdomainmanager-method.md)
- [<span data-ttu-id="d003d-146">チュートリアル: デザイナーを使用し、ClickOnce 配置 API で必要に応じてアセンブリをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="d003d-146">Walkthrough: Downloading Assemblies on Demand with the ClickOnce Deployment API Using the Designer</span></span>](/visualstudio/deployment/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api-using-the-designer)
