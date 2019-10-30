---
title: ICLRControl::SetAppDomainManagerType メソッド
ms.date: 03/30/2017
api_name:
- ICLRControl.SetAppDomainManagerType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRControl::SetAppDomainManagerType
helpviewer_keywords:
- SetAppDomainManagerType method, ICLRControl interface [.NET Framework hosting]
- ICLRControl::SetAppDomainManagerType method [.NET Framework hosting]
ms.assetid: ec57828b-2aad-496d-a35a-e45d4bd7fe77
topic_type:
- apiref
ms.openlocfilehash: be29a4f83901b8e8fc338c2daa8f5703523402b2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126589"
---
# <a name="iclrcontrolsetappdomainmanagertype-method"></a><span data-ttu-id="c7ff0-102">ICLRControl::SetAppDomainManagerType メソッド</span><span class="sxs-lookup"><span data-stu-id="c7ff0-102">ICLRControl::SetAppDomainManagerType Method</span></span>
<span data-ttu-id="c7ff0-103"><xref:System.AppDomainManager> から派生した型を、アプリケーションドメインマネージャーの型として設定します。</span><span class="sxs-lookup"><span data-stu-id="c7ff0-103">Sets a type derived from <xref:System.AppDomainManager> as the type for application domain managers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7ff0-104">構文</span><span class="sxs-lookup"><span data-stu-id="c7ff0-104">Syntax</span></span>  
  
```cpp  
HRESULT SetAppDomainManagerType (  
    [in] LPCWSTR pwzAppDomainManagerAssembly,  
    [in] LPCWSTR pwzAppDomainManagerType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c7ff0-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c7ff0-105">Parameters</span></span>  
 `pwzAppDomainManagerAssembly`  
 <span data-ttu-id="c7ff0-106">から<xref:System.AppDomainManager> から派生した要求された型が実装されているアセンブリの名前。</span><span class="sxs-lookup"><span data-stu-id="c7ff0-106">[in] The name of the assembly in which the requested type derived from <xref:System.AppDomainManager> is implemented.</span></span>  
  
 `pwzAppDomainManagerType`  
 <span data-ttu-id="c7ff0-107">から<xref:System.AppDomainManager>の機能を実装する `pwzAppDomainManagerAssembly` パラメーターに実装されている型の名前。</span><span class="sxs-lookup"><span data-stu-id="c7ff0-107">[in] The name of the type implemented in the `pwzAppDomainManagerAssembly` parameter that implements the capabilities of <xref:System.AppDomainManager>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c7ff0-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="c7ff0-108">Return Value</span></span>  
  
|<span data-ttu-id="c7ff0-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c7ff0-109">HRESULT</span></span>|<span data-ttu-id="c7ff0-110">説明</span><span class="sxs-lookup"><span data-stu-id="c7ff0-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c7ff0-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="c7ff0-111">S_OK</span></span>|<span data-ttu-id="c7ff0-112">メソッドが正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="c7ff0-112">The method returned successfully.</span></span>|  
|<span data-ttu-id="c7ff0-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c7ff0-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c7ff0-114">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="c7ff0-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c7ff0-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c7ff0-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c7ff0-116">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="c7ff0-116">The call timed out.</span></span>|  
|<span data-ttu-id="c7ff0-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c7ff0-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c7ff0-118">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="c7ff0-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c7ff0-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c7ff0-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c7ff0-120">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="c7ff0-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c7ff0-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c7ff0-121">E_FAIL</span></span>|<span data-ttu-id="c7ff0-122">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="c7ff0-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c7ff0-123">メソッドから E_FAIL が返された後は、そのプロセス内で CLR を使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="c7ff0-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c7ff0-124">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="c7ff0-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c7ff0-125">［要件］</span><span class="sxs-lookup"><span data-stu-id="c7ff0-125">Requirements</span></span>  
 <span data-ttu-id="c7ff0-126">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c7ff0-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7ff0-127">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="c7ff0-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c7ff0-128">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="c7ff0-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c7ff0-129">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7ff0-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7ff0-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="c7ff0-130">See also</span></span>

- [<span data-ttu-id="c7ff0-131">ICLRControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c7ff0-131">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="c7ff0-132">IHostControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c7ff0-132">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
