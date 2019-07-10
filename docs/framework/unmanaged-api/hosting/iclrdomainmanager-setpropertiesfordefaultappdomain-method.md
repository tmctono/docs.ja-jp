---
title: ICLRDomainManager::SetPropertiesForDefaultAppDomain メソッド
ms.date: 03/30/2017
api_name:
- ICLRDomainManager.SetPropertiesForDefaultAppDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDomainManager::SetPropertiesForDefaultAppDomain
helpviewer_keywords:
- ICLRDomainManager::SetPropertiesForDefaultAppDomain method [.NET Framework hosting]
- SetPropertiesForDefaultAppDomain method [.NET Framework hosting]
ms.assetid: 43e61c4b-c435-45ec-9ef6-c68403aa4200
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cfd7c835cdc4b53c753d714216d1745eb0b80c2d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67772933"
---
# <a name="iclrdomainmanagersetpropertiesfordefaultappdomain-method"></a><span data-ttu-id="a6144-102">ICLRDomainManager::SetPropertiesForDefaultAppDomain メソッド</span><span class="sxs-lookup"><span data-stu-id="a6144-102">ICLRDomainManager::SetPropertiesForDefaultAppDomain Method</span></span>
<span data-ttu-id="a6144-103">既定のアプリケーション ドメインを初期化するために使用されるプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="a6144-103">Sets properties that will be used to initialize the default application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6144-104">構文</span><span class="sxs-lookup"><span data-stu-id="a6144-104">Syntax</span></span>  
  
```cpp  
HRESULT SetPropertiesForDefaultAppDomain(  
    [in] DWORD nProperties,  
    [in] LPCWSTR *pwszPropertyNames,  
    [in] LPCWSTR *pwszPropertyValues  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a6144-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a6144-105">Parameters</span></span>  
 `nProperties`  
 <span data-ttu-id="a6144-106">[in]エントリ数`pwszPropertyNames`と`pwszPropertyValues`します。</span><span class="sxs-lookup"><span data-stu-id="a6144-106">[in] The number of entries in `pwszPropertyNames` and `pwszPropertyValues`.</span></span>  
  
 `pwszPropertyNames`  
 <span data-ttu-id="a6144-107">[in]プロパティ名、またはプロパティがない場合は null の配列。</span><span class="sxs-lookup"><span data-stu-id="a6144-107">[in] An array of property names, or null if there are no properties.</span></span> <span data-ttu-id="a6144-108">現時点では、このメソッドによって認識される唯一のプロパティ名は、"PARTIAL_TRUST_VISIBLE_ASSEMBLIES"です。</span><span class="sxs-lookup"><span data-stu-id="a6144-108">Currently, the only property name that is recognized by this method is "PARTIAL_TRUST_VISIBLE_ASSEMBLIES".</span></span>  
  
 `pwszPropertyValues`  
 <span data-ttu-id="a6144-109">[in]プロパティの値、またはプロパティがない場合は null の配列。</span><span class="sxs-lookup"><span data-stu-id="a6144-109">[in] An array of property values, or null if there are no properties.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a6144-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="a6144-110">Return Value</span></span>  
 <span data-ttu-id="a6144-111">このメソッドは、次の特定の HRESULT と、メソッドの失敗を示す HRESULT エラーも返します。</span><span class="sxs-lookup"><span data-stu-id="a6144-111">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="a6144-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a6144-112">HRESULT</span></span>|<span data-ttu-id="a6144-113">説明</span><span class="sxs-lookup"><span data-stu-id="a6144-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a6144-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="a6144-114">S_OK</span></span>|<span data-ttu-id="a6144-115">メソッドは正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="a6144-115">The method completed successfully.</span></span>|  
|<span data-ttu-id="a6144-116">HRESULT_FROM_WIN32(ERROR_UNKNOWN_PROPERTY)</span><span class="sxs-lookup"><span data-stu-id="a6144-116">HRESULT_FROM_WIN32(ERROR_UNKNOWN_PROPERTY)</span></span>|<span data-ttu-id="a6144-117">`pwszPropertyNames` このメソッドによって認識されないプロパティ名が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a6144-117">`pwszPropertyNames` includes a property name that is not recognized by this method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a6144-118">Remarks</span><span class="sxs-lookup"><span data-stu-id="a6144-118">Remarks</span></span>  
 <span data-ttu-id="a6144-119">"PARTIAL_TRUST_VISIBLE_ASSEMBLIES"のプロパティの値は、条件付きのアセンブリのリスト<xref:System.Security.AllowPartiallyTrustedCallersAttribute>(APTCA) 属性を<xref:System.Security.PartialTrustVisibilityLevel.NotVisibleByDefault?displayProperty=nameWithType>フラグは、既定のアプリケーションで部分的に信頼された呼び出し元を表示するようにするのにはドメイン。</span><span class="sxs-lookup"><span data-stu-id="a6144-119">The property value for "PARTIAL_TRUST_VISIBLE_ASSEMBLIES" is a list of assemblies that have the conditional <xref:System.Security.AllowPartiallyTrustedCallersAttribute> (APTCA) attribute with the <xref:System.Security.PartialTrustVisibilityLevel.NotVisibleByDefault?displayProperty=nameWithType> flag, which are to be made visible to partially trusted callers in the default application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a6144-120">必要条件</span><span class="sxs-lookup"><span data-stu-id="a6144-120">Requirements</span></span>  
 <span data-ttu-id="a6144-121">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6144-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6144-122">**ヘッダー:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="a6144-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="a6144-123">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="a6144-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a6144-124">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6144-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6144-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="a6144-125">See also</span></span>

- [<span data-ttu-id="a6144-126">ホスティング</span><span class="sxs-lookup"><span data-stu-id="a6144-126">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
- [<span data-ttu-id="a6144-127">ICLRDomainManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a6144-127">ICLRDomainManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-interface.md)
