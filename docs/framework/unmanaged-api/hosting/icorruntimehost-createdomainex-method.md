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
ms.openlocfilehash: a3a2d1827774ddedc00eb849f64256e3f425b3fa
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127718"
---
# <a name="icorruntimehostcreatedomainex-method"></a><span data-ttu-id="1f0a9-102">ICorRuntimeHost::CreateDomainEx メソッド</span><span class="sxs-lookup"><span data-stu-id="1f0a9-102">ICorRuntimeHost::CreateDomainEx Method</span></span>
<span data-ttu-id="1f0a9-103">アプリケーションドメインを作成します。</span><span class="sxs-lookup"><span data-stu-id="1f0a9-103">Creates an application domain.</span></span> <span data-ttu-id="1f0a9-104">呼び出し元は、型 <xref:System._AppDomain>のインターフェイスポインターを <xref:System.AppDomain?displayProperty=nameWithType>型のインスタンスに受信します。</span><span class="sxs-lookup"><span data-stu-id="1f0a9-104">The caller receives an interface pointer, of type <xref:System._AppDomain>, to an instance of type <xref:System.AppDomain?displayProperty=nameWithType>.</span></span> <span data-ttu-id="1f0a9-105">このメソッドを使用すると、呼び出し元は IAppDomainSetup インスタンスを渡して、返された <xref:System._AppDomain> インスタンスの追加機能を構成できます。</span><span class="sxs-lookup"><span data-stu-id="1f0a9-105">This method allows the caller to pass an IAppDomainSetup instance to configure additional features of the returned <xref:System._AppDomain> instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f0a9-106">構文</span><span class="sxs-lookup"><span data-stu-id="1f0a9-106">Syntax</span></span>  
  
```cpp  
HRESULT CreateDomainEx (  
    [in] LPCWSTR     pwzFriendlyName,  
    [in] IUnknown*   pSetup,  
    [in] IUnknown*   pIdentityArray,  
    [out] IUnknown** pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1f0a9-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1f0a9-107">Parameters</span></span>  
 `pwzFriendlyName`  
 <span data-ttu-id="1f0a9-108">からドメインのフレンドリ名を指定するために使用される省略可能なパラメーター。</span><span class="sxs-lookup"><span data-stu-id="1f0a9-108">[in] An optional parameter used to give a friendly name to the domain.</span></span> <span data-ttu-id="1f0a9-109">このフレンドリ名は、ドメインを識別するためのデバッガーなどのユーザーインターフェイスに表示できます。</span><span class="sxs-lookup"><span data-stu-id="1f0a9-109">This friendly name can be displayed in user interfaces such as debuggers to identify the domain.</span></span>  
  
 `pSetup`  
 <span data-ttu-id="1f0a9-110">から[ICorRuntimeHost:: CreateDomainSetup](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainsetup-method.md)メソッドの呼び出しによって取得される、`IAppDomainSetup`型の省略可能なインターフェイスポインター。</span><span class="sxs-lookup"><span data-stu-id="1f0a9-110">[in] An optional interface pointer of type `IAppDomainSetup`, obtained by a call to the [ICorRuntimeHost::CreateDomainSetup](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainsetup-method.md) method.</span></span>  
  
 `pIdentityArray`  
 <span data-ttu-id="1f0a9-111">からアクセス許可セットを確立するためにセキュリティポリシーによってマップされた証拠を表す、`IIdentity` のインスタンスへのポインターの配列 (省略可能)。</span><span class="sxs-lookup"><span data-stu-id="1f0a9-111">[in] An optional array of pointers to `IIdentity` instances that represent evidence mapped through security policy to establish a permission set.</span></span> <span data-ttu-id="1f0a9-112">`IIdentity` オブジェクトは、 [Createevidence](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createevidence-method.md)メソッドを呼び出すことによって取得できます。</span><span class="sxs-lookup"><span data-stu-id="1f0a9-112">An `IIdentity` object can be obtained by calling the [CreateEvidence](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createevidence-method.md) method.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="1f0a9-113">入出力ドメインをさらに制御するために使用できる <xref:System.AppDomain?displayProperty=nameWithType> のインスタンスに <xref:System._AppDomain> 型のインターフェイスポインター。</span><span class="sxs-lookup"><span data-stu-id="1f0a9-113">[out] An interface pointer of type <xref:System._AppDomain> to an instance of <xref:System.AppDomain?displayProperty=nameWithType> that can be used to further control the domain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1f0a9-114">戻り値</span><span class="sxs-lookup"><span data-stu-id="1f0a9-114">Return Value</span></span>  
  
|<span data-ttu-id="1f0a9-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1f0a9-115">HRESULT</span></span>|<span data-ttu-id="1f0a9-116">説明</span><span class="sxs-lookup"><span data-stu-id="1f0a9-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1f0a9-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="1f0a9-117">S_OK</span></span>|<span data-ttu-id="1f0a9-118">操作は成功しました。</span><span class="sxs-lookup"><span data-stu-id="1f0a9-118">The operation was successful.</span></span>|  
|<span data-ttu-id="1f0a9-119">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="1f0a9-119">S_FALSE</span></span>|<span data-ttu-id="1f0a9-120">操作を完了できませんでした。</span><span class="sxs-lookup"><span data-stu-id="1f0a9-120">The operation failed to complete.</span></span>|  
|<span data-ttu-id="1f0a9-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1f0a9-121">E_FAIL</span></span>|<span data-ttu-id="1f0a9-122">不明な重大なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="1f0a9-122">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="1f0a9-123">メソッドから E_FAIL が返された場合、そのプロセスでは共通言語ランタイム (CLR) は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="1f0a9-123">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="1f0a9-124">後続のホスト Api への呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="1f0a9-124">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="1f0a9-125">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1f0a9-125">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1f0a9-126">CLR がプロセスに読み込まれていないか、CLR がマネージドコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="1f0a9-126">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1f0a9-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="1f0a9-127">Remarks</span></span>  
 <span data-ttu-id="1f0a9-128">`CreateDomainEx` は、呼び出し元が `IAppDomainSetup` インスタンスにアプリケーションドメインを構成するためのプロパティ値を渡して渡すことができるようにすることで、 [Createdomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md)の機能を拡張します。</span><span class="sxs-lookup"><span data-stu-id="1f0a9-128">`CreateDomainEx` extends the capabilities of [CreateDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md) by allowing the caller to pass in an `IAppDomainSetup` instance with property values for configuring the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1f0a9-129">［要件］</span><span class="sxs-lookup"><span data-stu-id="1f0a9-129">Requirements</span></span>  
 <span data-ttu-id="1f0a9-130">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f0a9-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1f0a9-131">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="1f0a9-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1f0a9-132">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="1f0a9-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1f0a9-133">**.NET Framework バージョン:** 1.0、1.1</span><span class="sxs-lookup"><span data-stu-id="1f0a9-133">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f0a9-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="1f0a9-134">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- <xref:System.IAppDomainSetup?displayProperty=nameWithType>
- [<span data-ttu-id="1f0a9-135">CreateDomain メソッド</span><span class="sxs-lookup"><span data-stu-id="1f0a9-135">CreateDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md)
- [<span data-ttu-id="1f0a9-136">ICorRuntimeHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1f0a9-136">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
