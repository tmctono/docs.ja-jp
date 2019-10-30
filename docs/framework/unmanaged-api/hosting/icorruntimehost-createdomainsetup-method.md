---
title: ICorRuntimeHost::CreateDomainSetup メソッド
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.CreateDomainSetup
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CreateDomainSetup
helpviewer_keywords:
- CreateDomainSetup method [.NET Framework hosting]
- ICorRuntimeHost::CreateDomainSetup method [.NET Framework hosting]
ms.assetid: c21dab60-fb65-47d9-8a94-7fd47ca53b48
topic_type:
- apiref
ms.openlocfilehash: 217874e625604613e67170a118a7bc3616e02c4d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139650"
---
# <a name="icorruntimehostcreatedomainsetup-method"></a><span data-ttu-id="b81f3-102">ICorRuntimeHost::CreateDomainSetup メソッド</span><span class="sxs-lookup"><span data-stu-id="b81f3-102">ICorRuntimeHost::CreateDomainSetup Method</span></span>
<span data-ttu-id="b81f3-103"><xref:System.AppDomainSetup?displayProperty=nameWithType> インスタンスへの型 IAppDomainSetup のインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="b81f3-103">Gets an interface pointer of type IAppDomainSetup to an <xref:System.AppDomainSetup?displayProperty=nameWithType> instance.</span></span> <span data-ttu-id="b81f3-104">`IAppDomainSetup` には、アプリケーションドメインを作成する前に構成するためのメソッドが用意されています。</span><span class="sxs-lookup"><span data-stu-id="b81f3-104">`IAppDomainSetup` provides methods to configure aspects of an application domain before it is created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b81f3-105">構文</span><span class="sxs-lookup"><span data-stu-id="b81f3-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateDomainSetup (  
    [out] IUnknown** pAppDomainSetup  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b81f3-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b81f3-106">Parameters</span></span>  
 `pAppDomainSetup`  
 <span data-ttu-id="b81f3-107">入出力<xref:System.AppDomainSetup?displayProperty=nameWithType> インスタンスへのインターフェイスポインター。</span><span class="sxs-lookup"><span data-stu-id="b81f3-107">[out] An interface pointer to an <xref:System.AppDomainSetup?displayProperty=nameWithType> instance.</span></span> <span data-ttu-id="b81f3-108">このパラメーターは `IUnknown`として型指定されるため、通常、呼び出し元はこのポインターの `QueryInterface` を呼び出して `IAppDomainSetup`型のインターフェイスポインターを取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b81f3-108">This parameter is typed as `IUnknown`, so callers should generally call `QueryInterface` on this pointer to obtain an interface pointer of type `IAppDomainSetup`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b81f3-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="b81f3-109">Return Value</span></span>  
  
|<span data-ttu-id="b81f3-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b81f3-110">HRESULT</span></span>|<span data-ttu-id="b81f3-111">説明</span><span class="sxs-lookup"><span data-stu-id="b81f3-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b81f3-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="b81f3-112">S_OK</span></span>|<span data-ttu-id="b81f3-113">操作は成功しました。</span><span class="sxs-lookup"><span data-stu-id="b81f3-113">The operation was successful.</span></span>|  
|<span data-ttu-id="b81f3-114">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="b81f3-114">S_FALSE</span></span>|<span data-ttu-id="b81f3-115">操作を完了できませんでした。</span><span class="sxs-lookup"><span data-stu-id="b81f3-115">The operation failed to complete.</span></span>|  
|<span data-ttu-id="b81f3-116">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b81f3-116">E_FAIL</span></span>|<span data-ttu-id="b81f3-117">不明な重大なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="b81f3-117">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="b81f3-118">メソッドから E_FAIL が返された場合、そのプロセスでは共通言語ランタイム (CLR) は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="b81f3-118">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="b81f3-119">後続のホスト Api への呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="b81f3-119">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="b81f3-120">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b81f3-120">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b81f3-121">CLR がプロセスに読み込まれていないか、CLR がマネージドコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="b81f3-121">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b81f3-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="b81f3-122">Remarks</span></span>  
 <span data-ttu-id="b81f3-123">このメソッドから返されるポインターは、通常、パラメーターとして[Createdomainex](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md)メソッドに渡されます。</span><span class="sxs-lookup"><span data-stu-id="b81f3-123">The pointer returned from this method is typically passed as a parameter to the [CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b81f3-124">［要件］</span><span class="sxs-lookup"><span data-stu-id="b81f3-124">Requirements</span></span>  
 <span data-ttu-id="b81f3-125">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b81f3-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b81f3-126">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="b81f3-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b81f3-127">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="b81f3-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b81f3-128">**.NET Framework バージョン:** 1.0、1.1</span><span class="sxs-lookup"><span data-stu-id="b81f3-128">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b81f3-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="b81f3-129">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- <xref:System.AppDomainSetup>
- <xref:System.IAppDomainSetup?displayProperty=nameWithType>
- [<span data-ttu-id="b81f3-130">ICorRuntimeHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b81f3-130">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
