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
ms.openlocfilehash: 4e5856fbcda83c1dd30559c6f59f63495faea78d
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762345"
---
# <a name="icorruntimehostcreatedomainex-method"></a><span data-ttu-id="2b77d-102">ICorRuntimeHost::CreateDomainEx メソッド</span><span class="sxs-lookup"><span data-stu-id="2b77d-102">ICorRuntimeHost::CreateDomainEx Method</span></span>
<span data-ttu-id="2b77d-103">アプリケーションドメインを作成します。</span><span class="sxs-lookup"><span data-stu-id="2b77d-103">Creates an application domain.</span></span> <span data-ttu-id="2b77d-104">呼び出し元は、型のインターフェイスポインターを <xref:System._AppDomain> 型のインスタンスに受信し <xref:System.AppDomain?displayProperty=nameWithType> ます。</span><span class="sxs-lookup"><span data-stu-id="2b77d-104">The caller receives an interface pointer, of type <xref:System._AppDomain>, to an instance of type <xref:System.AppDomain?displayProperty=nameWithType>.</span></span> <span data-ttu-id="2b77d-105">このメソッドを使用すると、呼び出し元は IAppDomainSetup インスタンスを渡して、返されたインスタンスの追加の機能を構成でき <xref:System._AppDomain> ます。</span><span class="sxs-lookup"><span data-stu-id="2b77d-105">This method allows the caller to pass an IAppDomainSetup instance to configure additional features of the returned <xref:System._AppDomain> instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b77d-106">構文</span><span class="sxs-lookup"><span data-stu-id="2b77d-106">Syntax</span></span>  
  
```cpp  
HRESULT CreateDomainEx (  
    [in] LPCWSTR     pwzFriendlyName,  
    [in] IUnknown*   pSetup,  
    [in] IUnknown*   pIdentityArray,  
    [out] IUnknown** pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2b77d-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2b77d-107">Parameters</span></span>  
 `pwzFriendlyName`  
 <span data-ttu-id="2b77d-108">からドメインのフレンドリ名を指定するために使用される省略可能なパラメーター。</span><span class="sxs-lookup"><span data-stu-id="2b77d-108">[in] An optional parameter used to give a friendly name to the domain.</span></span> <span data-ttu-id="2b77d-109">このフレンドリ名は、ドメインを識別するためのデバッガーなどのユーザーインターフェイスに表示できます。</span><span class="sxs-lookup"><span data-stu-id="2b77d-109">This friendly name can be displayed in user interfaces such as debuggers to identify the domain.</span></span>  
  
 `pSetup`  
 <span data-ttu-id="2b77d-110">から`IAppDomainSetup` [ICorRuntimeHost:: CreateDomainSetup](icorruntimehost-createdomainsetup-method.md)メソッドの呼び出しによって取得される、型の省略可能なインターフェイスポインター。</span><span class="sxs-lookup"><span data-stu-id="2b77d-110">[in] An optional interface pointer of type `IAppDomainSetup`, obtained by a call to the [ICorRuntimeHost::CreateDomainSetup](icorruntimehost-createdomainsetup-method.md) method.</span></span>  
  
 `pIdentityArray`  
 <span data-ttu-id="2b77d-111">から`IIdentity`アクセス許可セットを確立するためにセキュリティポリシーによってマップされた証拠を表す、インスタンスへのポインターの配列 (省略可能)。</span><span class="sxs-lookup"><span data-stu-id="2b77d-111">[in] An optional array of pointers to `IIdentity` instances that represent evidence mapped through security policy to establish a permission set.</span></span> <span data-ttu-id="2b77d-112">`IIdentity`オブジェクトは、 [createevidence](icorruntimehost-createevidence-method.md)メソッドを呼び出すことによって取得できます。</span><span class="sxs-lookup"><span data-stu-id="2b77d-112">An `IIdentity` object can be obtained by calling the [CreateEvidence](icorruntimehost-createevidence-method.md) method.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="2b77d-113">入出力<xref:System._AppDomain> <xref:System.AppDomain?displayProperty=nameWithType> ドメインをさらに制御するために使用できるのインスタンスへの型のインターフェイスポインター。</span><span class="sxs-lookup"><span data-stu-id="2b77d-113">[out] An interface pointer of type <xref:System._AppDomain> to an instance of <xref:System.AppDomain?displayProperty=nameWithType> that can be used to further control the domain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2b77d-114">戻り値</span><span class="sxs-lookup"><span data-stu-id="2b77d-114">Return Value</span></span>  
  
|<span data-ttu-id="2b77d-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2b77d-115">HRESULT</span></span>|<span data-ttu-id="2b77d-116">説明</span><span class="sxs-lookup"><span data-stu-id="2b77d-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2b77d-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="2b77d-117">S_OK</span></span>|<span data-ttu-id="2b77d-118">操作に成功しました。</span><span class="sxs-lookup"><span data-stu-id="2b77d-118">The operation was successful.</span></span>|  
|<span data-ttu-id="2b77d-119">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="2b77d-119">S_FALSE</span></span>|<span data-ttu-id="2b77d-120">操作を完了できませんでした。</span><span class="sxs-lookup"><span data-stu-id="2b77d-120">The operation failed to complete.</span></span>|  
|<span data-ttu-id="2b77d-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2b77d-121">E_FAIL</span></span>|<span data-ttu-id="2b77d-122">不明な重大なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="2b77d-122">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="2b77d-123">メソッドが E_FAIL を返す場合、このプロセスでは共通言語ランタイム (CLR) は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="2b77d-123">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="2b77d-124">後続のホスト Api への呼び出しでは HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="2b77d-124">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="2b77d-125">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2b77d-125">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2b77d-126">CLR がプロセスに読み込まれていないか、CLR がマネージドコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="2b77d-126">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2b77d-127">解説</span><span class="sxs-lookup"><span data-stu-id="2b77d-127">Remarks</span></span>  
 <span data-ttu-id="2b77d-128">`CreateDomainEx`は、呼び出し元がインスタンスにアプリケーションドメインを構成するためのプロパティ値を渡すことができるようにすることで、 [Createdomain](icorruntimehost-createdomain-method.md)の機能を拡張し `IAppDomainSetup` ます。</span><span class="sxs-lookup"><span data-stu-id="2b77d-128">`CreateDomainEx` extends the capabilities of [CreateDomain](icorruntimehost-createdomain-method.md) by allowing the caller to pass in an `IAppDomainSetup` instance with property values for configuring the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b77d-129">要件</span><span class="sxs-lookup"><span data-stu-id="2b77d-129">Requirements</span></span>  
 <span data-ttu-id="2b77d-130">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b77d-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b77d-131">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="2b77d-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2b77d-132">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="2b77d-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2b77d-133">**.NET Framework バージョン:** 1.0、1.1</span><span class="sxs-lookup"><span data-stu-id="2b77d-133">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b77d-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="2b77d-134">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- <xref:System.IAppDomainSetup?displayProperty=nameWithType>
- [<span data-ttu-id="2b77d-135">CreateDomain メソッド</span><span class="sxs-lookup"><span data-stu-id="2b77d-135">CreateDomain Method</span></span>](icorruntimehost-createdomain-method.md)
- [<span data-ttu-id="2b77d-136">ICorRuntimeHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2b77d-136">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
