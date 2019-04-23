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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9eacd3802c51cb6ccf3f7ba874c75a2d2774439d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59091194"
---
# <a name="iclrcontrolsetappdomainmanagertype-method"></a><span data-ttu-id="35b23-102">ICLRControl::SetAppDomainManagerType メソッド</span><span class="sxs-lookup"><span data-stu-id="35b23-102">ICLRControl::SetAppDomainManagerType Method</span></span>
<span data-ttu-id="35b23-103">派生した型を設定<xref:System.AppDomainManager>アプリケーション ドメイン マネージャーの型として。</span><span class="sxs-lookup"><span data-stu-id="35b23-103">Sets a type derived from <xref:System.AppDomainManager> as the type for application domain managers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35b23-104">構文</span><span class="sxs-lookup"><span data-stu-id="35b23-104">Syntax</span></span>  
  
```  
HRESULT SetAppDomainManagerType (  
    [in] LPCWSTR pwzAppDomainManagerAssembly,  
    [in] LPCWSTR pwzAppDomainManagerType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="35b23-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="35b23-105">Parameters</span></span>  
 `pwzAppDomainManagerAssembly`  
 <span data-ttu-id="35b23-106">[in]要求された型から派生するアセンブリの名前<xref:System.AppDomainManager>実装されます。</span><span class="sxs-lookup"><span data-stu-id="35b23-106">[in] The name of the assembly in which the requested type derived from <xref:System.AppDomainManager> is implemented.</span></span>  
  
 `pwzAppDomainManagerType`  
 <span data-ttu-id="35b23-107">[in]実装された型の名前、`pwzAppDomainManagerAssembly`パラメーターの機能を実装する<xref:System.AppDomainManager>します。</span><span class="sxs-lookup"><span data-stu-id="35b23-107">[in] The name of the type implemented in the `pwzAppDomainManagerAssembly` parameter that implements the capabilities of <xref:System.AppDomainManager>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="35b23-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="35b23-108">Return Value</span></span>  
  
|<span data-ttu-id="35b23-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="35b23-109">HRESULT</span></span>|<span data-ttu-id="35b23-110">説明</span><span class="sxs-lookup"><span data-stu-id="35b23-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="35b23-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="35b23-111">S_OK</span></span>|<span data-ttu-id="35b23-112">メソッドが正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="35b23-112">The method returned successfully.</span></span>|  
|<span data-ttu-id="35b23-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="35b23-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="35b23-114">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="35b23-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="35b23-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="35b23-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="35b23-116">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="35b23-116">The call timed out.</span></span>|  
|<span data-ttu-id="35b23-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="35b23-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="35b23-118">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="35b23-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="35b23-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="35b23-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="35b23-120">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="35b23-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="35b23-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="35b23-121">E_FAIL</span></span>|<span data-ttu-id="35b23-122">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="35b23-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="35b23-123">メソッドには、E_FAIL が返された、後に、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="35b23-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="35b23-124">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="35b23-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="35b23-125">必要条件</span><span class="sxs-lookup"><span data-stu-id="35b23-125">Requirements</span></span>  
 <span data-ttu-id="35b23-126">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="35b23-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35b23-127">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="35b23-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="35b23-128">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="35b23-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="35b23-129">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35b23-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35b23-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="35b23-130">See also</span></span>

- [<span data-ttu-id="35b23-131">ICLRControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="35b23-131">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="35b23-132">IHostControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="35b23-132">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
