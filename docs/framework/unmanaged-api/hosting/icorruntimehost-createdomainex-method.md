---
title: ICorRuntimeHost::CreateDomainEx メソッド
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.CreateDomainEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CreateDomainEx
helpviewer_keywords:
- ICorRuntimeHost::CreateDomainEx method [.NET Framework hosting]
- CreateDomainEx method [.NET Framework hosting]
ms.assetid: 1bdde382-f8ba-4cc8-94b2-d1ac919c585e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2e51c5cda8eca1737e2daab4cbe94a78433c8608
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67762120"
---
# <a name="icorruntimehostcreatedomainex-method"></a><span data-ttu-id="fab2e-102">ICorRuntimeHost::CreateDomainEx メソッド</span><span class="sxs-lookup"><span data-stu-id="fab2e-102">ICorRuntimeHost::CreateDomainEx Method</span></span>
<span data-ttu-id="fab2e-103">アプリケーション ドメインを作成します。</span><span class="sxs-lookup"><span data-stu-id="fab2e-103">Creates an application domain.</span></span> <span data-ttu-id="fab2e-104">呼び出し元が型のインターフェイス ポインターを受け取る<xref:System._AppDomain>、型のインスタンスに<xref:System.AppDomain?displayProperty=nameWithType>します。</span><span class="sxs-lookup"><span data-stu-id="fab2e-104">The caller receives an interface pointer, of type <xref:System._AppDomain>, to an instance of type <xref:System.AppDomain?displayProperty=nameWithType>.</span></span> <span data-ttu-id="fab2e-105">この方法により、呼び出し、返された追加の機能を構成する IAppDomainSetup インスタンス<xref:System._AppDomain>インスタンス。</span><span class="sxs-lookup"><span data-stu-id="fab2e-105">This method allows the caller to pass an IAppDomainSetup instance to configure additional features of the returned <xref:System._AppDomain> instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fab2e-106">構文</span><span class="sxs-lookup"><span data-stu-id="fab2e-106">Syntax</span></span>  
  
```cpp  
HRESULT CreateDomainEx (  
    [in] LPCWSTR     pwzFriendlyName,  
    [in] IUnknown*   pSetup,  
    [in] IUnknown*   pIdentityArray,  
    [out] IUnknown** pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fab2e-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="fab2e-107">Parameters</span></span>  
 `pwzFriendlyName`  
 <span data-ttu-id="fab2e-108">[in]ドメインにわかりやすい名前を指定するために使用する省略可能なパラメーター。</span><span class="sxs-lookup"><span data-stu-id="fab2e-108">[in] An optional parameter used to give a friendly name to the domain.</span></span> <span data-ttu-id="fab2e-109">この表示名は、ドメインを識別するためにデバッガーなどのユーザー インターフェイスで表示できます。</span><span class="sxs-lookup"><span data-stu-id="fab2e-109">This friendly name can be displayed in user interfaces such as debuggers to identify the domain.</span></span>  
  
 `pSetup`  
 <span data-ttu-id="fab2e-110">[in]型の省略可能なインターフェイス ポインターを`IAppDomainSetup`への呼び出しで取得した、 [icorruntimehost::createdomainsetup](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainsetup-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="fab2e-110">[in] An optional interface pointer of type `IAppDomainSetup`, obtained by a call to the [ICorRuntimeHost::CreateDomainSetup](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainsetup-method.md) method.</span></span>  
  
 `pIdentityArray`  
 <span data-ttu-id="fab2e-111">[in]ポインターの省略可能な配列`IIdentity`権限セットを確立するためにセキュリティ ポリシーを通じて割り当てられる証拠を表すインスタンス。</span><span class="sxs-lookup"><span data-stu-id="fab2e-111">[in] An optional array of pointers to `IIdentity` instances that represent evidence mapped through security policy to establish a permission set.</span></span> <span data-ttu-id="fab2e-112">`IIdentity`オブジェクトを取得するには呼び出すことによって、 [CreateEvidence](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createevidence-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="fab2e-112">An `IIdentity` object can be obtained by calling the [CreateEvidence](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createevidence-method.md) method.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="fab2e-113">[out]型のインターフェイス ポインターを<xref:System._AppDomain>のインスタンスに<xref:System.AppDomain?displayProperty=nameWithType>さらに、ドメインを制御できます。</span><span class="sxs-lookup"><span data-stu-id="fab2e-113">[out] An interface pointer of type <xref:System._AppDomain> to an instance of <xref:System.AppDomain?displayProperty=nameWithType> that can be used to further control the domain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fab2e-114">戻り値</span><span class="sxs-lookup"><span data-stu-id="fab2e-114">Return Value</span></span>  
  
|<span data-ttu-id="fab2e-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fab2e-115">HRESULT</span></span>|<span data-ttu-id="fab2e-116">説明</span><span class="sxs-lookup"><span data-stu-id="fab2e-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fab2e-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="fab2e-117">S_OK</span></span>|<span data-ttu-id="fab2e-118">操作が正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="fab2e-118">The operation was successful.</span></span>|  
|<span data-ttu-id="fab2e-119">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="fab2e-119">S_FALSE</span></span>|<span data-ttu-id="fab2e-120">操作を完了できませんでした。</span><span class="sxs-lookup"><span data-stu-id="fab2e-120">The operation failed to complete.</span></span>|  
|<span data-ttu-id="fab2e-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="fab2e-121">E_FAIL</span></span>|<span data-ttu-id="fab2e-122">未知の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="fab2e-122">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="fab2e-123">場合は、メソッドは、E_FAIL を返します、共通言語ランタイム (CLR) はプロセスで使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="fab2e-123">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="fab2e-124">Api をホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="fab2e-124">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="fab2e-125">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="fab2e-125">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="fab2e-126">プロセスに CLR が読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="fab2e-126">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fab2e-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="fab2e-127">Remarks</span></span>  
 <span data-ttu-id="fab2e-128">`CreateDomainEx` 機能を拡張[CreateDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md)を渡す呼び出し元を許可することで、`IAppDomainSetup`アプリケーション ドメインを構成するためのプロパティの値を持つインスタンス。</span><span class="sxs-lookup"><span data-stu-id="fab2e-128">`CreateDomainEx` extends the capabilities of [CreateDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md) by allowing the caller to pass in an `IAppDomainSetup` instance with property values for configuring the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fab2e-129">必要条件</span><span class="sxs-lookup"><span data-stu-id="fab2e-129">Requirements</span></span>  
 <span data-ttu-id="fab2e-130">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fab2e-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fab2e-131">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="fab2e-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fab2e-132">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="fab2e-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fab2e-133">**.NET framework のバージョン:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="fab2e-133">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fab2e-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="fab2e-134">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- <xref:System.IAppDomainSetup?displayProperty=nameWithType>
- [<span data-ttu-id="fab2e-135">CreateDomain メソッド</span><span class="sxs-lookup"><span data-stu-id="fab2e-135">CreateDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md)
- [<span data-ttu-id="fab2e-136">ICorRuntimeHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fab2e-136">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
