---
title: IHostControl::SetAppDomainManager メソッド
ms.date: 03/30/2017
api_name:
- IHostControl.SetAppDomainManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostControl::SetAppDomainManager
helpviewer_keywords:
- IHostControl::SetAppDomainManager method [.NET Framework hosting]
- SetAppDomainManager method [.NET Framework hosting]
ms.assetid: 6562bbe7-0d67-4c50-a958-3a18cf680375
topic_type:
- apiref
ms.openlocfilehash: de264135450190fd028eb8cf12017d94cc65ffac
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134720"
---
# <a name="ihostcontrolsetappdomainmanager-method"></a><span data-ttu-id="5951c-102">IHostControl::SetAppDomainManager メソッド</span><span class="sxs-lookup"><span data-stu-id="5951c-102">IHostControl::SetAppDomainManager Method</span></span>
<span data-ttu-id="5951c-103">アプリケーションドメインが作成されたことをホストに通知します。</span><span class="sxs-lookup"><span data-stu-id="5951c-103">Notifies the host that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5951c-104">構文</span><span class="sxs-lookup"><span data-stu-id="5951c-104">Syntax</span></span>  
  
```cpp  
HRESULT SetAppDomainManager (  
    [in] DWORD     dwAppDomainID,  
    [in] IUnknown* pUnkAppDomainManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5951c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5951c-105">Parameters</span></span>  
 `dwAppDomainID`  
 <span data-ttu-id="5951c-106">から選択された <xref:System.AppDomain>の数値識別子。</span><span class="sxs-lookup"><span data-stu-id="5951c-106">[in] The numeric identifier of the selected <xref:System.AppDomain>.</span></span>  
  
 `pUnkAppDomainManager`  
 <span data-ttu-id="5951c-107">からホストが `IUnknown`として実装する <xref:System.AppDomainManager> オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="5951c-107">[in] A pointer to the <xref:System.AppDomainManager> object that the host implements as `IUnknown`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5951c-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="5951c-108">Return Value</span></span>  
  
|<span data-ttu-id="5951c-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5951c-109">HRESULT</span></span>|<span data-ttu-id="5951c-110">説明</span><span class="sxs-lookup"><span data-stu-id="5951c-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5951c-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="5951c-111">S_OK</span></span>|<span data-ttu-id="5951c-112">`SetAppDomainManager` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="5951c-112">`SetAppDomainManager` returned successfully.</span></span>|  
|<span data-ttu-id="5951c-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5951c-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5951c-114">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="5951c-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5951c-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5951c-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5951c-116">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="5951c-116">The call timed out.</span></span>|  
|<span data-ttu-id="5951c-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5951c-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5951c-118">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="5951c-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5951c-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5951c-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5951c-120">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="5951c-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5951c-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5951c-121">E_FAIL</span></span>|<span data-ttu-id="5951c-122">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="5951c-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5951c-123">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="5951c-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5951c-124">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="5951c-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5951c-125">Remarks</span><span class="sxs-lookup"><span data-stu-id="5951c-125">Remarks</span></span>  
 <span data-ttu-id="5951c-126"><xref:System.AppDomainManager> によって、ホストは、マネージコードにブートストラップし、各 <xref:System.AppDomain>の作成と設定を制御するメカニズムを提供します。</span><span class="sxs-lookup"><span data-stu-id="5951c-126">The <xref:System.AppDomainManager> provides the host with a mechanism to bootstrap into managed code and to control the creation and settings of each <xref:System.AppDomain>.</span></span> <span data-ttu-id="5951c-127">この <xref:System.AppDomain> が作成されると、<xref:System.AppDomainManager> が各 <xref:System.AppDomain> に読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="5951c-127">The <xref:System.AppDomainManager> is loaded into each <xref:System.AppDomain> when that <xref:System.AppDomain> is created.</span></span> <span data-ttu-id="5951c-128">このオプションを選択した場合、CLR は `pUnkAppDomainManager` パラメーターの値を設定することによって、アプリケーションドメインが作成されたことをホストに通知します。</span><span class="sxs-lookup"><span data-stu-id="5951c-128">If it chooses, the CLR notifies the host that the application domain has been created by setting the value of the `pUnkAppDomainManager` parameter.</span></span>  
  
 <span data-ttu-id="5951c-129">`SetAppDomainManager` メソッドの実装では、ホストはアプリケーションドメインマネージャーのアセンブリ名と型を設定できます。</span><span class="sxs-lookup"><span data-stu-id="5951c-129">In its implementation of the `SetAppDomainManager` method, the host can set the assembly name and type for the application domain manager.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5951c-130">［要件］</span><span class="sxs-lookup"><span data-stu-id="5951c-130">Requirements</span></span>  
 <span data-ttu-id="5951c-131">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5951c-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5951c-132">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="5951c-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5951c-133">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="5951c-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5951c-134">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5951c-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5951c-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="5951c-135">See also</span></span>

- <xref:System.AppDomain>
- <xref:System.AppDomainManager>
- [<span data-ttu-id="5951c-136">IHostControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5951c-136">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
