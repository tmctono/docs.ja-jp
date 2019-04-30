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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 118e75cb28a4e474427f35f4516ec41850ebe99f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61967714"
---
# <a name="ihostcontrolsetappdomainmanager-method"></a><span data-ttu-id="0e62c-102">IHostControl::SetAppDomainManager メソッド</span><span class="sxs-lookup"><span data-stu-id="0e62c-102">IHostControl::SetAppDomainManager Method</span></span>
<span data-ttu-id="0e62c-103">アプリケーション ドメインが作成されたことをホストに通知します。</span><span class="sxs-lookup"><span data-stu-id="0e62c-103">Notifies the host that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e62c-104">構文</span><span class="sxs-lookup"><span data-stu-id="0e62c-104">Syntax</span></span>  
  
```  
HRESULT SetAppDomainManager (  
    [in] DWORD     dwAppDomainID,  
    [in] IUnknown* pUnkAppDomainManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0e62c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0e62c-105">Parameters</span></span>  
 `dwAppDomainID`  
 <span data-ttu-id="0e62c-106">[in]選択した数値識別子<xref:System.AppDomain>します。</span><span class="sxs-lookup"><span data-stu-id="0e62c-106">[in] The numeric identifier of the selected <xref:System.AppDomain>.</span></span>  
  
 `pUnkAppDomainManager`  
 <span data-ttu-id="0e62c-107">[in]ポインター、<xref:System.AppDomainManager>としてホストを実装するオブジェクト`IUnknown`します。</span><span class="sxs-lookup"><span data-stu-id="0e62c-107">[in] A pointer to the <xref:System.AppDomainManager> object that the host implements as `IUnknown`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0e62c-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="0e62c-108">Return Value</span></span>  
  
|<span data-ttu-id="0e62c-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0e62c-109">HRESULT</span></span>|<span data-ttu-id="0e62c-110">説明</span><span class="sxs-lookup"><span data-stu-id="0e62c-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0e62c-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="0e62c-111">S_OK</span></span>|<span data-ttu-id="0e62c-112">`SetAppDomainManager` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="0e62c-112">`SetAppDomainManager` returned successfully.</span></span>|  
|<span data-ttu-id="0e62c-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0e62c-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0e62c-114">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="0e62c-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0e62c-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0e62c-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0e62c-116">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="0e62c-116">The call timed out.</span></span>|  
|<span data-ttu-id="0e62c-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0e62c-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0e62c-118">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="0e62c-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0e62c-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0e62c-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0e62c-120">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="0e62c-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0e62c-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0e62c-121">E_FAIL</span></span>|<span data-ttu-id="0e62c-122">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="0e62c-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0e62c-123">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="0e62c-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0e62c-124">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="0e62c-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0e62c-125">Remarks</span><span class="sxs-lookup"><span data-stu-id="0e62c-125">Remarks</span></span>  
 <span data-ttu-id="0e62c-126"><xref:System.AppDomainManager>により、ホストにマネージ コードをブートス トラップを作成およびそれぞれの設定を制御するメカニズムで<xref:System.AppDomain>します。</span><span class="sxs-lookup"><span data-stu-id="0e62c-126">The <xref:System.AppDomainManager> provides the host with a mechanism to bootstrap into managed code and to control the creation and settings of each <xref:System.AppDomain>.</span></span> <span data-ttu-id="0e62c-127"><xref:System.AppDomainManager>それぞれに読み込まれる<xref:System.AppDomain>ときを<xref:System.AppDomain>が作成されます。</span><span class="sxs-lookup"><span data-stu-id="0e62c-127">The <xref:System.AppDomainManager> is loaded into each <xref:System.AppDomain> when that <xref:System.AppDomain> is created.</span></span> <span data-ttu-id="0e62c-128">選択した場合、CLR をホストに通知の値を設定して、アプリケーション ドメインが作成されたこと、`pUnkAppDomainManager`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="0e62c-128">If it chooses, the CLR notifies the host that the application domain has been created by setting the value of the `pUnkAppDomainManager` parameter.</span></span>  
  
 <span data-ttu-id="0e62c-129">実装で、`SetAppDomainManager`メソッド、ホスト設定できますアセンブリの名前と種類のアプリケーション ドメイン マネージャー。</span><span class="sxs-lookup"><span data-stu-id="0e62c-129">In its implementation of the `SetAppDomainManager` method, the host can set the assembly name and type for the application domain manager.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e62c-130">必要条件</span><span class="sxs-lookup"><span data-stu-id="0e62c-130">Requirements</span></span>  
 <span data-ttu-id="0e62c-131">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0e62c-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e62c-132">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0e62c-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0e62c-133">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="0e62c-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0e62c-134">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0e62c-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e62c-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="0e62c-135">See also</span></span>

- <xref:System.AppDomain>
- <xref:System.AppDomainManager>
- [<span data-ttu-id="0e62c-136">IHostControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0e62c-136">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
