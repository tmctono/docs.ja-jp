---
title: ICLRDomainManager::SetAppDomainManagerType メソッド
ms.date: 03/30/2017
api_name:
- ICLRDomainManager.SetAppDomainManagerType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDomainManager::SetAppDomainManagerType
helpviewer_keywords:
- SetAppDomainManagerType method, ICLRDomainManager interface [.NET Framework hosting]
- ICLRDomainManager::SetAppDomainManagerType method [.NET Framework hosting]
ms.assetid: ee91abb0-cb74-41dd-927b-e117fb8ffdf4
ms.openlocfilehash: 5c61e2e1208cec0bda1492964a8d02bd71f5a1c6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129332"
---
# <a name="iclrdomainmanagersetappdomainmanagertype-method"></a><span data-ttu-id="a250d-102">ICLRDomainManager::SetAppDomainManagerType メソッド</span><span class="sxs-lookup"><span data-stu-id="a250d-102">ICLRDomainManager::SetAppDomainManagerType Method</span></span>
<span data-ttu-id="a250d-103">既定のアプリケーションドメインを初期化するために使用されるアプリケーションドメインマネージャーの <xref:System.AppDomainManager?displayProperty=nameWithType> クラスから派生した型を指定します。</span><span class="sxs-lookup"><span data-stu-id="a250d-103">Specifies the type, derived from the <xref:System.AppDomainManager?displayProperty=nameWithType> class, of the application domain manager that will be used to initialize the default application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a250d-104">構文</span><span class="sxs-lookup"><span data-stu-id="a250d-104">Syntax</span></span>  
  
```cpp  
HRESULT SetAppDomainManagerType(  
    [in] LPCWSTR wszAppDomainManagerAssembly,  
    [in] LPCWSTR wszAppDomainManagerType,  
    [in] EInitializeNewDomainFlags dwInitializeDomainFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a250d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a250d-105">Parameters</span></span>  
 `wszAppDomainManagerAssembly`  
 <span data-ttu-id="a250d-106">からアプリケーションドメインマネージャーの種類を含むアセンブリの表示名です。たとえば、"使用しているバージョン = 1.0.0.0, Culture = ニュートラル, PublicKeyToken = 6856bccf150f00b3" のようになります。</span><span class="sxs-lookup"><span data-stu-id="a250d-106">[in] The display name of the assembly that contains the application domain manager type; for example: "AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3".</span></span>  
  
 `wszAppDomainManagerType`  
 <span data-ttu-id="a250d-107">から名前空間を含む、アプリケーションドメインマネージャーの型名。</span><span class="sxs-lookup"><span data-stu-id="a250d-107">[in] The type name of the application domain manager, including the namespace.</span></span>  
  
 `dwInitializeDomainFlags`  
 <span data-ttu-id="a250d-108">からアプリケーションドメインマネージャーに関する情報を提供する[EInitializeNewDomainFlags](../../../../docs/framework/unmanaged-api/hosting/einitializenewdomainflags-enumeration.md)列挙値の組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="a250d-108">[in] A combination of [EInitializeNewDomainFlags](../../../../docs/framework/unmanaged-api/hosting/einitializenewdomainflags-enumeration.md) enumeration values that provide information about the application domain manager.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a250d-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="a250d-109">Return Value</span></span>  
 <span data-ttu-id="a250d-110">このメソッドは、次の特定の HRESULT と、メソッドの失敗を示す HRESULT エラーも返します。</span><span class="sxs-lookup"><span data-stu-id="a250d-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="a250d-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a250d-111">HRESULT</span></span>|<span data-ttu-id="a250d-112">説明</span><span class="sxs-lookup"><span data-stu-id="a250d-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a250d-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="a250d-113">S_OK</span></span>|<span data-ttu-id="a250d-114">メソッドは正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="a250d-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="a250d-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a250d-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a250d-116">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="a250d-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a250d-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="a250d-117">Remarks</span></span>  
 <span data-ttu-id="a250d-118">現時点では、`dwInitializeDomainFlags` に対して定義されている唯一の値は `eInitializeNewDomainFlags_NoSecurityChanges`であり、<xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> メソッドの実行中にアプリケーションドメインマネージャーがセキュリティ設定を変更しないことを共通言語ランタイム (CLR) に通知します。</span><span class="sxs-lookup"><span data-stu-id="a250d-118">Currently, the only defined value for `dwInitializeDomainFlags` is `eInitializeNewDomainFlags_NoSecurityChanges`, which tells the common language runtime (CLR) that the application domain manager will not modify security settings during the execution of the <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="a250d-119">これにより、CLR は条件付き <xref:System.Security.AllowPartiallyTrustedCallersAttribute> (APTCA) 属性を持つアセンブリの読み込みを最適化できます。</span><span class="sxs-lookup"><span data-stu-id="a250d-119">This allows the CLR to optimize the loading of assemblies that have the conditional <xref:System.Security.AllowPartiallyTrustedCallersAttribute> (APTCA) attribute.</span></span> <span data-ttu-id="a250d-120">これにより、このアセンブリセットの推移的なクロージャが大きい場合に、起動時間が大幅に向上する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a250d-120">This can result in a significant improvement in startup time if the transitive closure of this set of assemblies is large.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="a250d-121">ホストでアプリケーションドメインマネージャーの `eInitializeNewDomainFlags_NoSecurityChanges` が指定されている場合、アプリケーションドメインのセキュリティを変更しようとすると、<xref:System.InvalidOperationException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="a250d-121">If the host specifies `eInitializeNewDomainFlags_NoSecurityChanges` for the application domain manager, an <xref:System.InvalidOperationException> is thrown if any attempt is made to modify the security of the application domain.</span></span>  
  
 <span data-ttu-id="a250d-122">[ICLRControl:: SetAppDomainManagerType](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)メソッドを呼び出すことは、`eInitializeNewDomainFlags_None`で `ICLRDomainManager::SetAppDomainManagerType` を呼び出すことと同じです。</span><span class="sxs-lookup"><span data-stu-id="a250d-122">Calling the [ICLRControl::SetAppDomainManagerType](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)method is equivalent to calling `ICLRDomainManager::SetAppDomainManagerType` with `eInitializeNewDomainFlags_None`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a250d-123">［要件］</span><span class="sxs-lookup"><span data-stu-id="a250d-123">Requirements</span></span>  
 <span data-ttu-id="a250d-124">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a250d-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a250d-125">**ヘッダー:** メタホスト .h</span><span class="sxs-lookup"><span data-stu-id="a250d-125">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="a250d-126">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="a250d-126">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a250d-127">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a250d-127">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a250d-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="a250d-128">See also</span></span>

- [<span data-ttu-id="a250d-129">ホスティング</span><span class="sxs-lookup"><span data-stu-id="a250d-129">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
- [<span data-ttu-id="a250d-130">ICLRDomainManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a250d-130">ICLRDomainManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-interface.md)
- [<span data-ttu-id="a250d-131">EInitializeNewDomainFlags 列挙型</span><span class="sxs-lookup"><span data-stu-id="a250d-131">EInitializeNewDomainFlags Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/einitializenewdomainflags-enumeration.md)
