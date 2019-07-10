---
title: ICorRuntimeHost::CreateEvidence メソッド
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.CreateEvidence
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CreateEvidence
helpviewer_keywords:
- CreateEvidence method [.NET Framework hosting]
- ICorRuntimeHost::CreateEvidence method [.NET Framework hosting]
ms.assetid: e235ea80-b84c-4442-a4c3-fc96c25a8eb9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e3b17ca32051cd5fc0673ef26124b855a66f9785
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779983"
---
# <a name="icorruntimehostcreateevidence-method"></a><span data-ttu-id="81f81-102">ICorRuntimeHost::CreateEvidence メソッド</span><span class="sxs-lookup"><span data-stu-id="81f81-102">ICorRuntimeHost::CreateEvidence Method</span></span>
<span data-ttu-id="81f81-103">型のインターフェイス ポインターを取得<xref:System.Security.Principal.IIdentity?displayProperty=nameWithType>、ホストに渡すセキュリティ証拠を作成することができます、 [CreateDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md)または[CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="81f81-103">Gets an interface pointer of type <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType>, which allows the host to create security evidence to pass to the [CreateDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md) or [CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81f81-104">構文</span><span class="sxs-lookup"><span data-stu-id="81f81-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateEvidence (  
    [out] IUnknown** pEvidence  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="81f81-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="81f81-105">Parameters</span></span>  
 `pEvidence`  
 <span data-ttu-id="81f81-106">[out]インターフェイス ポインターを<xref:System.Security.Principal.IIdentity?displayProperty=nameWithType>インスタンスのセキュリティ証拠を作成するために使用します。</span><span class="sxs-lookup"><span data-stu-id="81f81-106">[out] A interface pointer to an <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType> instance used to create security evidence.</span></span> <span data-ttu-id="81f81-107">このポインターは型指定`IUnknown`呼び出し元が呼び出す通常必要がありますので、`QueryInterface`へのポインターを取得するには、このインターフェイスで、<xref:System.Security.Principal.IIdentity?displayProperty=nameWithType>します。</span><span class="sxs-lookup"><span data-stu-id="81f81-107">This pointer is typed `IUnknown`, so callers should typically call `QueryInterface` on this interface to obtain a pointer to an <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="81f81-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="81f81-108">Return Value</span></span>  
  
|<span data-ttu-id="81f81-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="81f81-109">HRESULT</span></span>|<span data-ttu-id="81f81-110">説明</span><span class="sxs-lookup"><span data-stu-id="81f81-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="81f81-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="81f81-111">S_OK</span></span>|<span data-ttu-id="81f81-112">操作が正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="81f81-112">The operation was successful.</span></span>|  
|<span data-ttu-id="81f81-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="81f81-113">S_FALSE</span></span>|<span data-ttu-id="81f81-114">操作を完了できませんでした。</span><span class="sxs-lookup"><span data-stu-id="81f81-114">The operation failed to complete.</span></span>|  
|<span data-ttu-id="81f81-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="81f81-115">E_FAIL</span></span>|<span data-ttu-id="81f81-116">未知の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="81f81-116">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="81f81-117">場合は、メソッドは、E_FAIL を返します、共通言語ランタイム (CLR) はプロセスで使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="81f81-117">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="81f81-118">Api をホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="81f81-118">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="81f81-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="81f81-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="81f81-120">プロセスに CLR が読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="81f81-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="81f81-121">Remarks</span><span class="sxs-lookup"><span data-stu-id="81f81-121">Remarks</span></span>  
 <span data-ttu-id="81f81-122">このメソッドは、ネイティブ コードから設定することはできません、空のコレクションを返します。</span><span class="sxs-lookup"><span data-stu-id="81f81-122">This method returns an empty collection that cannot be populated from native code.</span></span> <span data-ttu-id="81f81-123">使用する必要があります、<xref:System.Security.Policy.Evidence>メソッド代わりにします。</span><span class="sxs-lookup"><span data-stu-id="81f81-123">You should use the <xref:System.Security.Policy.Evidence> method instead.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="81f81-124">必要条件</span><span class="sxs-lookup"><span data-stu-id="81f81-124">Requirements</span></span>  
 <span data-ttu-id="81f81-125">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="81f81-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81f81-126">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="81f81-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="81f81-127">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="81f81-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="81f81-128">**.NET framework のバージョン:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="81f81-128">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81f81-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="81f81-129">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [<span data-ttu-id="81f81-130">ICorRuntimeHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="81f81-130">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
