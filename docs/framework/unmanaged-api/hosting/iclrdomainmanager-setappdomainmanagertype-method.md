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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6cfef7d929d40996716a02a4db51630827011a68
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61984777"
---
# <a name="iclrdomainmanagersetappdomainmanagertype-method"></a><span data-ttu-id="33826-102">ICLRDomainManager::SetAppDomainManagerType メソッド</span><span class="sxs-lookup"><span data-stu-id="33826-102">ICLRDomainManager::SetAppDomainManagerType Method</span></span>
<span data-ttu-id="33826-103">派生した、型を指定します、<xref:System.AppDomainManager?displayProperty=nameWithType>の既定のアプリケーション ドメインを初期化するために使用されるアプリケーション ドメイン マネージャーのクラス。</span><span class="sxs-lookup"><span data-stu-id="33826-103">Specifies the type, derived from the <xref:System.AppDomainManager?displayProperty=nameWithType> class, of the application domain manager that will be used to initialize the default application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33826-104">構文</span><span class="sxs-lookup"><span data-stu-id="33826-104">Syntax</span></span>  
  
```  
HRESULT SetAppDomainManagerType(  
    [in] LPCWSTR wszAppDomainManagerAssembly,  
    [in] LPCWSTR wszAppDomainManagerType,  
    [in] EInitializeNewDomainFlags dwInitializeDomainFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="33826-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="33826-105">Parameters</span></span>  
 `wszAppDomainManagerAssembly`  
 <span data-ttu-id="33826-106">[in]アプリケーション ドメイン マネージャーの種類; を含むアセンブリの表示名例えば："AdMgrExample、バージョン 1.0.0.0、Culture = neutral, PublicKeyToken = = 6856bccf150f00b3"。</span><span class="sxs-lookup"><span data-stu-id="33826-106">[in] The display name of the assembly that contains the application domain manager type; for example: "AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3".</span></span>  
  
 `wszAppDomainManagerType`  
 <span data-ttu-id="33826-107">[in]名前空間を含む、アプリケーション ドメイン マネージャーの型名。</span><span class="sxs-lookup"><span data-stu-id="33826-107">[in] The type name of the application domain manager, including the namespace.</span></span>  
  
 `dwInitializeDomainFlags`  
 <span data-ttu-id="33826-108">[in]組み合わせた[EInitializeNewDomainFlags](../../../../docs/framework/unmanaged-api/hosting/einitializenewdomainflags-enumeration.md)アプリケーション ドメイン マネージャーに関する情報を提供する列挙値。</span><span class="sxs-lookup"><span data-stu-id="33826-108">[in] A combination of [EInitializeNewDomainFlags](../../../../docs/framework/unmanaged-api/hosting/einitializenewdomainflags-enumeration.md) enumeration values that provide information about the application domain manager.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="33826-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="33826-109">Return Value</span></span>  
 <span data-ttu-id="33826-110">このメソッドは、次の特定の HRESULT と、メソッドの失敗を示す HRESULT エラーも返します。</span><span class="sxs-lookup"><span data-stu-id="33826-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="33826-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="33826-111">HRESULT</span></span>|<span data-ttu-id="33826-112">説明</span><span class="sxs-lookup"><span data-stu-id="33826-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="33826-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="33826-113">S_OK</span></span>|<span data-ttu-id="33826-114">メソッドは正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="33826-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="33826-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="33826-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="33826-116">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="33826-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="33826-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="33826-117">Remarks</span></span>  
 <span data-ttu-id="33826-118">現時点では、のみ定義されている値の`dwInitializeDomainFlags`は`eInitializeNewDomainFlags_NoSecurityChanges`、共通言語ランタイム (CLR) を指示すると、アプリケーション ドメイン マネージャーが実行中のセキュリティ設定を変更しないこと、<xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType>メソッド。</span><span class="sxs-lookup"><span data-stu-id="33826-118">Currently, the only defined value for `dwInitializeDomainFlags` is `eInitializeNewDomainFlags_NoSecurityChanges`, which tells the common language runtime (CLR) that the application domain manager will not modify security settings during the execution of the <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="33826-119">これにより、条件付きのアセンブリの読み込みを最適化するために CLR <xref:System.Security.AllowPartiallyTrustedCallersAttribute> (APTCA) 属性。</span><span class="sxs-lookup"><span data-stu-id="33826-119">This allows the CLR to optimize the loading of assemblies that have the conditional <xref:System.Security.AllowPartiallyTrustedCallersAttribute> (APTCA) attribute.</span></span> <span data-ttu-id="33826-120">これは、結果、この一連のアセンブリの推移閉包が大きい場合に、起動時間が大幅に向上。</span><span class="sxs-lookup"><span data-stu-id="33826-120">This can result in a significant improvement in startup time if the transitive closure of this set of assemblies is large.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="33826-121">ホストが指定されている場合`eInitializeNewDomainFlags_NoSecurityChanges`のアプリケーション ドメイン マネージャーに、<xref:System.InvalidOperationException>が、アプリケーション ドメインのセキュリティを変更する試行が行われた場合にスローされます。</span><span class="sxs-lookup"><span data-stu-id="33826-121">If the host specifies `eInitializeNewDomainFlags_NoSecurityChanges` for the application domain manager, an <xref:System.InvalidOperationException> is thrown if any attempt is made to modify the security of the application domain.</span></span>  
  
 <span data-ttu-id="33826-122">呼び出す、 [iclrcontrol::setappdomainmanagertype](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)メソッドを呼び出すことは`ICLRDomainManager::SetAppDomainManagerType`で`eInitializeNewDomainFlags_None`します。</span><span class="sxs-lookup"><span data-stu-id="33826-122">Calling the [ICLRControl::SetAppDomainManagerType](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)method is equivalent to calling `ICLRDomainManager::SetAppDomainManagerType` with `eInitializeNewDomainFlags_None`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33826-123">必要条件</span><span class="sxs-lookup"><span data-stu-id="33826-123">Requirements</span></span>  
 <span data-ttu-id="33826-124">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="33826-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33826-125">**ヘッダー:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="33826-125">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="33826-126">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="33826-126">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="33826-127">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33826-127">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33826-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="33826-128">See also</span></span>

- [<span data-ttu-id="33826-129">ホスティング</span><span class="sxs-lookup"><span data-stu-id="33826-129">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
- [<span data-ttu-id="33826-130">ICLRDomainManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="33826-130">ICLRDomainManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-interface.md)
- [<span data-ttu-id="33826-131">EInitializeNewDomainFlags 列挙型</span><span class="sxs-lookup"><span data-stu-id="33826-131">EInitializeNewDomainFlags Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/einitializenewdomainflags-enumeration.md)
