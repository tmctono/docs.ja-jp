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
ms.openlocfilehash: 38938de335e5f0d7cb8051554c400f16df012362
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965357"
---
# <a name="iclrruntimehostexecuteapplication-method"></a><span data-ttu-id="14ef5-102">ICLRRuntimeHost::ExecuteApplication メソッド</span><span class="sxs-lookup"><span data-stu-id="14ef5-102">ICLRRuntimeHost::ExecuteApplication Method</span></span>
<span data-ttu-id="14ef5-103">新しいドメインでアクティブ化するアプリケーションを指定するために、マニフェストベースの ClickOnce 配置シナリオで使用されます。</span><span class="sxs-lookup"><span data-stu-id="14ef5-103">Used in manifest-based ClickOnce deployment scenarios to specify the application to be activated in a new domain.</span></span> <span data-ttu-id="14ef5-104">これらのシナリオの詳細については、「 [ClickOnce のセキュリティと配置](/visualstudio/deployment/clickonce-security-and-deployment)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="14ef5-104">For more information about these scenarios, see [ClickOnce Security and Deployment](/visualstudio/deployment/clickonce-security-and-deployment).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14ef5-105">構文</span><span class="sxs-lookup"><span data-stu-id="14ef5-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="14ef5-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="14ef5-106">Parameters</span></span>  
 `pwzAppFullName`  
 <span data-ttu-id="14ef5-107">からに<xref:System.ApplicationIdentity>定義されているアプリケーションの完全名。</span><span class="sxs-lookup"><span data-stu-id="14ef5-107">[in] The full name of the application, as defined for <xref:System.ApplicationIdentity>.</span></span>  
  
 `dwManifestPaths`  
 <span data-ttu-id="14ef5-108">から`ppwzManifestPaths`配列に格納されている文字列の数。</span><span class="sxs-lookup"><span data-stu-id="14ef5-108">[in] The number of strings contained in the `ppwzManifestPaths` array.</span></span>  
  
 `ppwzManifestPaths`  
 <span data-ttu-id="14ef5-109">[in] オプション。</span><span class="sxs-lookup"><span data-stu-id="14ef5-109">[in] Optional.</span></span> <span data-ttu-id="14ef5-110">アプリケーションのマニフェストパスを格納する文字列配列。</span><span class="sxs-lookup"><span data-stu-id="14ef5-110">A string array that contains manifest paths for the application.</span></span>  
  
 `dwActivationData`  
 <span data-ttu-id="14ef5-111">から`ppwzActivationData`配列に格納されている文字列の数。</span><span class="sxs-lookup"><span data-stu-id="14ef5-111">[in] The number of strings contained in the `ppwzActivationData` array.</span></span>  
  
 `ppwzActivationData`  
 <span data-ttu-id="14ef5-112">[in] オプション。</span><span class="sxs-lookup"><span data-stu-id="14ef5-112">[in] Optional.</span></span> <span data-ttu-id="14ef5-113">Web に配置されたアプリケーションの URL のクエリ文字列部分など、アプリケーションのアクティベーションデータを格納する文字列配列。</span><span class="sxs-lookup"><span data-stu-id="14ef5-113">A string array that contains the application's activation data, such as the query string portion of the URL for applications deployed over the Web.</span></span>  
  
 `pReturnValue`  
 <span data-ttu-id="14ef5-114">入出力アプリケーションのエントリポイントから返される値。</span><span class="sxs-lookup"><span data-stu-id="14ef5-114">[out] The value returned from the entry point of the application.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="14ef5-115">戻り値</span><span class="sxs-lookup"><span data-stu-id="14ef5-115">Return Value</span></span>  
  
|<span data-ttu-id="14ef5-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="14ef5-116">HRESULT</span></span>|<span data-ttu-id="14ef5-117">説明</span><span class="sxs-lookup"><span data-stu-id="14ef5-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="14ef5-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="14ef5-118">S_OK</span></span>|<span data-ttu-id="14ef5-119">`ExecuteApplication`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="14ef5-119">`ExecuteApplication` returned successfully.</span></span>|  
|<span data-ttu-id="14ef5-120">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="14ef5-120">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="14ef5-121">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="14ef5-121">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="14ef5-122">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="14ef5-122">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="14ef5-123">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="14ef5-123">The call timed out.</span></span>|  
|<span data-ttu-id="14ef5-124">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="14ef5-124">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="14ef5-125">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="14ef5-125">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="14ef5-126">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="14ef5-126">HOST_E_ABANDONED</span></span>|<span data-ttu-id="14ef5-127">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="14ef5-127">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="14ef5-128">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="14ef5-128">E_FAIL</span></span>|<span data-ttu-id="14ef5-129">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="14ef5-129">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="14ef5-130">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="14ef5-130">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="14ef5-131">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="14ef5-131">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="14ef5-132">Remarks</span><span class="sxs-lookup"><span data-stu-id="14ef5-132">Remarks</span></span>  
 <span data-ttu-id="14ef5-133">`ExecuteApplication`は、新しく作成されたアプリケーションドメインで ClickOnce アプリケーションをアクティブ化するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="14ef5-133">`ExecuteApplication` is used to activate ClickOnce applications in a newly created application domain.</span></span>  
  
 <span data-ttu-id="14ef5-134">`pReturnValue`出力パラメーターは、アプリケーションによって返される値に設定されます。</span><span class="sxs-lookup"><span data-stu-id="14ef5-134">The `pReturnValue` output parameter is set to the value returned by the application.</span></span> <span data-ttu-id="14ef5-135">に`pReturnValue`null 値を指定した場合、 `ExecuteApplication`は失敗しませんが、値を返しません。</span><span class="sxs-lookup"><span data-stu-id="14ef5-135">If you supply a value of null for `pReturnValue`, `ExecuteApplication` does not fail, but it does not return a value.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="14ef5-136">`ExecuteApplication`メソッドを呼び出してからマニフェストベースのアプリケーションをアクティブ化する前に、 [Start メソッド](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md)メソッドを呼び出さないでください。</span><span class="sxs-lookup"><span data-stu-id="14ef5-136">Do not call the [Start Method](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) method before calling the `ExecuteApplication` method to activate a manifest-based application.</span></span> <span data-ttu-id="14ef5-137">メソッドが最初`ExecuteApplication`に呼び出された場合、メソッドの呼び出しは失敗します。 `Start`</span><span class="sxs-lookup"><span data-stu-id="14ef5-137">If the `Start` method is called first, the `ExecuteApplication` method call will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="14ef5-138">必要条件</span><span class="sxs-lookup"><span data-stu-id="14ef5-138">Requirements</span></span>  
 <span data-ttu-id="14ef5-139">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="14ef5-139">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="14ef5-140">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="14ef5-140">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="14ef5-141">**ライブラリ**Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="14ef5-141">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="14ef5-142">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="14ef5-142">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14ef5-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="14ef5-143">See also</span></span>

- <xref:System.ActivationContext>
- <xref:System.AppDomainManager>
- <xref:System.ApplicationIdentity>
- [<span data-ttu-id="14ef5-144">ICLRRuntimeHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="14ef5-144">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
- [<span data-ttu-id="14ef5-145">SetAppDomainManager メソッド</span><span class="sxs-lookup"><span data-stu-id="14ef5-145">SetAppDomainManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-setappdomainmanager-method.md)
- [<span data-ttu-id="14ef5-146">チュートリアル: デザイナーを使用し、ClickOnce 配置 API で必要に応じてアセンブリをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="14ef5-146">Walkthrough: Downloading Assemblies on Demand with the ClickOnce Deployment API Using the Designer</span></span>](/visualstudio/deployment/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api-using-the-designer)
