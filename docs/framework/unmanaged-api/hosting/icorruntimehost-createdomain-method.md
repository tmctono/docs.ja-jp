---
title: ICorRuntimeHost::CreateDomain メソッド
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.CreateDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CreateDomain
helpviewer_keywords:
- CreateDomain method [.NET Framework hosting]
- ICorRuntimeHost::CreateDomain method [.NET Framework hosting]
ms.assetid: b96c5ef3-a9df-4c7c-9952-432d3272cb5c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9fdacb690b31e7b9930825e5d54ef8fc95bb3a5a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67762132"
---
# <a name="icorruntimehostcreatedomain-method"></a><span data-ttu-id="8e280-102">ICorRuntimeHost::CreateDomain メソッド</span><span class="sxs-lookup"><span data-stu-id="8e280-102">ICorRuntimeHost::CreateDomain Method</span></span>
<span data-ttu-id="8e280-103">アプリケーション ドメインを作成します。</span><span class="sxs-lookup"><span data-stu-id="8e280-103">Creates an application domain.</span></span> <span data-ttu-id="8e280-104">呼び出し元が型のインターフェイス ポインターを受け取る<xref:System._AppDomain>型のインスタンスに<xref:System.AppDomain?displayProperty=nameWithType>します。</span><span class="sxs-lookup"><span data-stu-id="8e280-104">The caller receives an interface pointer of type <xref:System._AppDomain> to an instance of type <xref:System.AppDomain?displayProperty=nameWithType>.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e280-105">構文</span><span class="sxs-lookup"><span data-stu-id="8e280-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateDomain (  
    [in] LPWSTR    pwzFriendlyName,  
    [in] IUnknown* pIdentityArray,  
    [out] void   **pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8e280-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8e280-106">Parameters</span></span>  
 `pwzFriendlyName`  
 <span data-ttu-id="8e280-107">[in]ドメインにわかりやすい名前を指定するために使用する省略可能なパラメーター。</span><span class="sxs-lookup"><span data-stu-id="8e280-107">[in] An optional parameter used to give a friendly name to the domain.</span></span> <span data-ttu-id="8e280-108">この表示名は、ドメインを識別するためにデバッガーなどのユーザー インターフェイスで表示できます。</span><span class="sxs-lookup"><span data-stu-id="8e280-108">This friendly name can be displayed in user interfaces such as debuggers to identify the domain.</span></span>  
  
 `pIdentityArray`  
 <span data-ttu-id="8e280-109">[in]ポインターの省略可能な配列`IIdentity`権限セットを確立するためにセキュリティ ポリシーを通じて割り当てられる証拠を表すインスタンス。</span><span class="sxs-lookup"><span data-stu-id="8e280-109">[in] An optional array of pointers to `IIdentity` instances that represent evidence mapped through security policy to establish a  permission set.</span></span> <span data-ttu-id="8e280-110">`IIdentity`オブジェクトを取得するには呼び出すことによって、 [CreateEvidence](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createevidence-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="8e280-110">An `IIdentity` object can be obtained by calling the [CreateEvidence](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createevidence-method.md) method.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="8e280-111">[out]型のインターフェイス ポインターを<xref:System._AppDomain>のインスタンスに<xref:System.AppDomain?displayProperty=nameWithType>さらに、ドメインを制御できます。</span><span class="sxs-lookup"><span data-stu-id="8e280-111">[out] An interface pointer of type <xref:System._AppDomain> to an instance of <xref:System.AppDomain?displayProperty=nameWithType> that can be used to further control the domain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8e280-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="8e280-112">Return Value</span></span>  
  
|<span data-ttu-id="8e280-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8e280-113">HRESULT</span></span>|<span data-ttu-id="8e280-114">説明</span><span class="sxs-lookup"><span data-stu-id="8e280-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8e280-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="8e280-115">S_OK</span></span>|<span data-ttu-id="8e280-116">操作が正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="8e280-116">The operation was successful.</span></span>|  
|<span data-ttu-id="8e280-117">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="8e280-117">S_FALSE</span></span>|<span data-ttu-id="8e280-118">操作を完了できませんでした。</span><span class="sxs-lookup"><span data-stu-id="8e280-118">The operation failed to complete.</span></span>|  
|<span data-ttu-id="8e280-119">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8e280-119">E_FAIL</span></span>|<span data-ttu-id="8e280-120">未知の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="8e280-120">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="8e280-121">場合は、メソッドは、E_FAIL を返します、共通言語ランタイム (CLR) はプロセスで使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="8e280-121">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="8e280-122">Api をホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="8e280-122">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="8e280-123">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8e280-123">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8e280-124">プロセスに CLR が読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="8e280-124">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8e280-125">必要条件</span><span class="sxs-lookup"><span data-stu-id="8e280-125">Requirements</span></span>  
 <span data-ttu-id="8e280-126">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e280-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e280-127">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8e280-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8e280-128">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="8e280-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8e280-129">**.NET framework のバージョン:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="8e280-129">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e280-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="8e280-130">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [<span data-ttu-id="8e280-131">ICorRuntimeHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8e280-131">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
