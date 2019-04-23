---
title: ICorRuntimeHost::NextDomain メソッド
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.NextDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::NextDomain
helpviewer_keywords:
- ICorRuntimeHost::NextDomain method [.NET Framework hosting]
- NextDomain method [.NET Framework hosting]
ms.assetid: fe07a05b-f6d6-44b5-ab01-b9a6eb15c350
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2c3ff0c91713a6bb7449791bae6a754c43659335
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59225275"
---
# <a name="icorruntimehostnextdomain-method"></a><span data-ttu-id="6389c-102">ICorRuntimeHost::NextDomain メソッド</span><span class="sxs-lookup"><span data-stu-id="6389c-102">ICorRuntimeHost::NextDomain Method</span></span>
<span data-ttu-id="6389c-103">列挙体で、次のドメインへのインターフェイス ポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="6389c-103">Gets an interface pointer to the next domain in the enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6389c-104">構文</span><span class="sxs-lookup"><span data-stu-id="6389c-104">Syntax</span></span>  
  
```  
HRESULT NextDomain (  
    [in] HCORENUM hEnum,  
    [out] void** pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6389c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6389c-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="6389c-106">[in]列挙子を呼び出すことによって取得された[EnumDomains](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-enumdomains-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="6389c-106">[in] The enumerator that was obtained through a call to [EnumDomains](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-enumdomains-method.md).</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="6389c-107">[out]インターフェイス ポインター、<xref:System._AppDomain?displayProperty=nameWithType>以上ドメインがない場合は、列挙型、または null の場合、次のドメインを表す型。</span><span class="sxs-lookup"><span data-stu-id="6389c-107">[out] An interface pointer to the <xref:System._AppDomain?displayProperty=nameWithType> type that represents the next domain in the enumeration, or null, if no more domains exist.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6389c-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="6389c-108">Return Value</span></span>  
  
|<span data-ttu-id="6389c-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6389c-109">HRESULT</span></span>|<span data-ttu-id="6389c-110">説明</span><span class="sxs-lookup"><span data-stu-id="6389c-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6389c-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="6389c-111">S_OK</span></span>|<span data-ttu-id="6389c-112">操作が正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="6389c-112">The operation was successful.</span></span>|  
|<span data-ttu-id="6389c-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="6389c-113">S_FALSE</span></span>|<span data-ttu-id="6389c-114">完了するには、操作に失敗しました、または列挙体のない複数のドメインがあります。</span><span class="sxs-lookup"><span data-stu-id="6389c-114">The operation failed to complete, or there are no more domains in the enumeration.</span></span>|  
|<span data-ttu-id="6389c-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6389c-115">E_FAIL</span></span>|<span data-ttu-id="6389c-116">未知の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="6389c-116">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="6389c-117">場合は、メソッドは、E_FAIL を返します、共通言語ランタイム (CLR) はプロセスで使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="6389c-117">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="6389c-118">Api をホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="6389c-118">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="6389c-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6389c-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6389c-120">プロセスに CLR が読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="6389c-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6389c-121">必要条件</span><span class="sxs-lookup"><span data-stu-id="6389c-121">Requirements</span></span>  
 <span data-ttu-id="6389c-122">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6389c-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6389c-123">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6389c-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6389c-124">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="6389c-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6389c-125">**.NET framework のバージョン:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="6389c-125">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6389c-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="6389c-126">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [<span data-ttu-id="6389c-127">ICorRuntimeHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6389c-127">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
