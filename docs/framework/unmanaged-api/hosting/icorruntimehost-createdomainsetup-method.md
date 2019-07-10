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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1f8e9284283247ec46a225470ae3063dac539f43
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780020"
---
# <a name="icorruntimehostcreatedomainsetup-method"></a><span data-ttu-id="c8d8b-102">ICorRuntimeHost::CreateDomainSetup メソッド</span><span class="sxs-lookup"><span data-stu-id="c8d8b-102">ICorRuntimeHost::CreateDomainSetup Method</span></span>
<span data-ttu-id="c8d8b-103">インターフェイス ポインターの型を IAppDomainSetup の取得、<xref:System.AppDomainSetup?displayProperty=nameWithType>インスタンス。</span><span class="sxs-lookup"><span data-stu-id="c8d8b-103">Gets an interface pointer of type IAppDomainSetup to an <xref:System.AppDomainSetup?displayProperty=nameWithType> instance.</span></span> <span data-ttu-id="c8d8b-104">`IAppDomainSetup` 作成される前に、アプリケーション ドメインの側面を構成する方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="c8d8b-104">`IAppDomainSetup` provides methods to configure aspects of an application domain before it is created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8d8b-105">構文</span><span class="sxs-lookup"><span data-stu-id="c8d8b-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateDomainSetup (  
    [out] IUnknown** pAppDomainSetup  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c8d8b-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c8d8b-106">Parameters</span></span>  
 `pAppDomainSetup`  
 <span data-ttu-id="c8d8b-107">[out]インターフェイス ポインターを<xref:System.AppDomainSetup?displayProperty=nameWithType>インスタンス。</span><span class="sxs-lookup"><span data-stu-id="c8d8b-107">[out] An interface pointer to an <xref:System.AppDomainSetup?displayProperty=nameWithType> instance.</span></span> <span data-ttu-id="c8d8b-108">このパラメーターとして型指定された`IUnknown`呼び出し元は一般に呼び出す必要がありますので、`QueryInterface`型のインターフェイス ポインターを取得するには、このポインターを`IAppDomainSetup`します。</span><span class="sxs-lookup"><span data-stu-id="c8d8b-108">This parameter is typed as `IUnknown`, so callers should generally call `QueryInterface` on this pointer to obtain an interface pointer of type `IAppDomainSetup`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c8d8b-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="c8d8b-109">Return Value</span></span>  
  
|<span data-ttu-id="c8d8b-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c8d8b-110">HRESULT</span></span>|<span data-ttu-id="c8d8b-111">説明</span><span class="sxs-lookup"><span data-stu-id="c8d8b-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c8d8b-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="c8d8b-112">S_OK</span></span>|<span data-ttu-id="c8d8b-113">操作が正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="c8d8b-113">The operation was successful.</span></span>|  
|<span data-ttu-id="c8d8b-114">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="c8d8b-114">S_FALSE</span></span>|<span data-ttu-id="c8d8b-115">操作を完了できませんでした。</span><span class="sxs-lookup"><span data-stu-id="c8d8b-115">The operation failed to complete.</span></span>|  
|<span data-ttu-id="c8d8b-116">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c8d8b-116">E_FAIL</span></span>|<span data-ttu-id="c8d8b-117">未知の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="c8d8b-117">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="c8d8b-118">場合は、メソッドは、E_FAIL を返します、共通言語ランタイム (CLR) はプロセスで使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="c8d8b-118">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="c8d8b-119">Api をホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="c8d8b-119">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="c8d8b-120">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c8d8b-120">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c8d8b-121">プロセスに CLR が読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="c8d8b-121">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c8d8b-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="c8d8b-122">Remarks</span></span>  
 <span data-ttu-id="c8d8b-123">このメソッドから返されるポインターは通常のパラメーターとして渡さ、 [CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="c8d8b-123">The pointer returned from this method is typically passed as a parameter to the [CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8d8b-124">必要条件</span><span class="sxs-lookup"><span data-stu-id="c8d8b-124">Requirements</span></span>  
 <span data-ttu-id="c8d8b-125">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8d8b-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8d8b-126">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c8d8b-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c8d8b-127">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="c8d8b-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c8d8b-128">**.NET framework のバージョン:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="c8d8b-128">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8d8b-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="c8d8b-129">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- <xref:System.AppDomainSetup>
- <xref:System.IAppDomainSetup?displayProperty=nameWithType>
- [<span data-ttu-id="c8d8b-130">ICorRuntimeHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c8d8b-130">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
