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
ms.openlocfilehash: 4a91f57126c0cf2074bd086ddb2fb4cd9e0716d4
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762319"
---
# <a name="icorruntimehostcreateevidence-method"></a><span data-ttu-id="504af-102">ICorRuntimeHost::CreateEvidence メソッド</span><span class="sxs-lookup"><span data-stu-id="504af-102">ICorRuntimeHost::CreateEvidence Method</span></span>
<span data-ttu-id="504af-103">型のインターフェイスポインターを取得し <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType> ます。これにより、ホストは、 [createdomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md)メソッドまたは[createdomainex](icorruntimehost-createdomainex-method.md)メソッドに渡すセキュリティ証拠を作成できます。</span><span class="sxs-lookup"><span data-stu-id="504af-103">Gets an interface pointer of type <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType>, which allows the host to create security evidence to pass to the [CreateDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md) or [CreateDomainEx](icorruntimehost-createdomainex-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="504af-104">構文</span><span class="sxs-lookup"><span data-stu-id="504af-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateEvidence (  
    [out] IUnknown** pEvidence  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="504af-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="504af-105">Parameters</span></span>  
 `pEvidence`  
 <span data-ttu-id="504af-106">入出力<xref:System.Security.Principal.IIdentity?displayProperty=nameWithType>セキュリティ証拠の作成に使用されるインスタンスへのインターフェイスポインター。</span><span class="sxs-lookup"><span data-stu-id="504af-106">[out] A interface pointer to an <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType> instance used to create security evidence.</span></span> <span data-ttu-id="504af-107">このポインターは型指定され `IUnknown` ているため、呼び出し元はへのポインターを取得するために、通常、このインターフェイスでを呼び出す必要があり `QueryInterface` <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType> ます。</span><span class="sxs-lookup"><span data-stu-id="504af-107">This pointer is typed `IUnknown`, so callers should typically call `QueryInterface` on this interface to obtain a pointer to an <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="504af-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="504af-108">Return Value</span></span>  
  
|<span data-ttu-id="504af-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="504af-109">HRESULT</span></span>|<span data-ttu-id="504af-110">説明</span><span class="sxs-lookup"><span data-stu-id="504af-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="504af-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="504af-111">S_OK</span></span>|<span data-ttu-id="504af-112">操作に成功しました。</span><span class="sxs-lookup"><span data-stu-id="504af-112">The operation was successful.</span></span>|  
|<span data-ttu-id="504af-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="504af-113">S_FALSE</span></span>|<span data-ttu-id="504af-114">操作を完了できませんでした。</span><span class="sxs-lookup"><span data-stu-id="504af-114">The operation failed to complete.</span></span>|  
|<span data-ttu-id="504af-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="504af-115">E_FAIL</span></span>|<span data-ttu-id="504af-116">不明な重大なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="504af-116">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="504af-117">メソッドが E_FAIL を返す場合、このプロセスでは共通言語ランタイム (CLR) は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="504af-117">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="504af-118">後続のホスト Api への呼び出しでは HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="504af-118">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="504af-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="504af-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="504af-120">CLR がプロセスに読み込まれていないか、CLR がマネージドコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="504af-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="504af-121">解説</span><span class="sxs-lookup"><span data-stu-id="504af-121">Remarks</span></span>  
 <span data-ttu-id="504af-122">このメソッドは、ネイティブコードから設定できない空のコレクションを返します。</span><span class="sxs-lookup"><span data-stu-id="504af-122">This method returns an empty collection that cannot be populated from native code.</span></span> <span data-ttu-id="504af-123">代わりに、メソッドを使用する必要があり <xref:System.Security.Policy.Evidence> ます。</span><span class="sxs-lookup"><span data-stu-id="504af-123">You should use the <xref:System.Security.Policy.Evidence> method instead.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="504af-124">要件</span><span class="sxs-lookup"><span data-stu-id="504af-124">Requirements</span></span>  
 <span data-ttu-id="504af-125">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="504af-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="504af-126">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="504af-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="504af-127">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="504af-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="504af-128">**.NET Framework バージョン:** 1.0、1.1</span><span class="sxs-lookup"><span data-stu-id="504af-128">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="504af-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="504af-129">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [<span data-ttu-id="504af-130">ICorRuntimeHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="504af-130">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
