---
title: ICLRMetaHost::QueryLegacyV2RuntimeBinding メソッド
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.RequestRuntimeLoadedNotification
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::QueryLegacyV2RuntimeBinding
helpviewer_keywords:
- QueryLegacyV2RuntimeBinding method [.NET Framework hosting]
- ICLRMetaHost::QueryLegacyV2RuntimeBinding method [.NET Framework hosting]
ms.assetid: 9929817e-acc9-40b7-960c-598664e04b60
topic_type:
- apiref
ms.openlocfilehash: 90474a61b16d65565889bd69ef75616804d8bc60
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140885"
---
# <a name="iclrmetahostquerylegacyv2runtimebinding-method"></a><span data-ttu-id="91d00-102">ICLRMetaHost::QueryLegacyV2RuntimeBinding メソッド</span><span class="sxs-lookup"><span data-stu-id="91d00-102">ICLRMetaHost::QueryLegacyV2RuntimeBinding Method</span></span>
<span data-ttu-id="91d00-103">レガシアクティブ化ポリシーがバインドされているランタイムを表すインターフェイスを返します。たとえば、 [\<スタートアップ > 要素](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)構成ファイルのエントリの `useLegacyV2RuntimeActivationPolicy` 属性を使用して、従来のアクティベーション api を直接使用したり、[ICLRRuntimeInfo:: BindAsLegacyV2Runtime](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-bindaslegacyv2runtime-method.md)メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="91d00-103">Returns an interface that represents a runtime to which legacy activation policy has been bound, for example, by using the `useLegacyV2RuntimeActivationPolicy` attribute on the [\<startup> element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) configuration file entry, by direct use of the legacy activation APIs, or by calling the [ICLRRuntimeInfo::BindAsLegacyV2Runtime](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-bindaslegacyv2runtime-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91d00-104">構文</span><span class="sxs-lookup"><span data-stu-id="91d00-104">Syntax</span></span>  
  
```cpp  
HRESULT QueryLegacyV2RuntimeBinding (  
    [in] REFIID riid,  
    [out, iid_is(riid), retval] LPVOID *ppUnk);  
```  
  
## <a name="parameters"></a><span data-ttu-id="91d00-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="91d00-105">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="91d00-106">から必須。現時点では、このパラメーターの有効な値は `IID_ICLRRuntimeInfo`のみです。</span><span class="sxs-lookup"><span data-stu-id="91d00-106">[in] Required.Currently the only valid value for this parameter is `IID_ICLRRuntimeInfo`.</span></span>  
  
 `ppUnk`  
 <span data-ttu-id="91d00-107">[out] 必須。</span><span class="sxs-lookup"><span data-stu-id="91d00-107">[out] Required.</span></span> <span data-ttu-id="91d00-108">このメソッドから制御が戻るときに、レガシアクティブ化ポリシーにバインドされているランタイムを表す[ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)インターフェイスへのポインターを格納します。</span><span class="sxs-lookup"><span data-stu-id="91d00-108">When this method returns, contains a pointer to the [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface that represents a runtime that has been bound to legacy activation policy.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="91d00-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="91d00-109">Return Value</span></span>  
 <span data-ttu-id="91d00-110">このメソッドは、次の特定の HRESULT と、メソッドの失敗を示す HRESULT エラーも返します。</span><span class="sxs-lookup"><span data-stu-id="91d00-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="91d00-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="91d00-111">HRESULT</span></span>|<span data-ttu-id="91d00-112">説明</span><span class="sxs-lookup"><span data-stu-id="91d00-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="91d00-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="91d00-113">S_OK</span></span>|<span data-ttu-id="91d00-114">メソッドは正常に完了し、レガシ アクティブ化ポリシーにバインドされているランタイムが返されました。</span><span class="sxs-lookup"><span data-stu-id="91d00-114">The method completed successfully and returned a runtime that was bound to legacy activation policy.</span></span>|  
|<span data-ttu-id="91d00-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="91d00-115">S_FALSE</span></span>|<span data-ttu-id="91d00-116">メソッドは正常に完了しましたが、レガシ ランタイムはまだバインドされていません。</span><span class="sxs-lookup"><span data-stu-id="91d00-116">The method completed successfully, but a legacy runtime has not yet been bound.</span></span>|  
|<span data-ttu-id="91d00-117">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="91d00-117">E_NOINTERFACE</span></span>|<span data-ttu-id="91d00-118">メソッドで、レガシ アクティブ化ポリシーにバインドされているランタイムが見つかりましたが、`riid` はそのランタイムでサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="91d00-118">The method found a runtime that was bound to legacy activation policy, but `riid` is not supported by that runtime.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="91d00-119">Remarks</span><span class="sxs-lookup"><span data-stu-id="91d00-119">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="91d00-120">［要件］</span><span class="sxs-lookup"><span data-stu-id="91d00-120">Requirements</span></span>  
 <span data-ttu-id="91d00-121">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="91d00-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="91d00-122">**ヘッダー:** メタホスト .h</span><span class="sxs-lookup"><span data-stu-id="91d00-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="91d00-123">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="91d00-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="91d00-124">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="91d00-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91d00-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="91d00-125">See also</span></span>

- [<span data-ttu-id="91d00-126">ICLRMetaHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="91d00-126">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)
- [<span data-ttu-id="91d00-127">ホスティング</span><span class="sxs-lookup"><span data-stu-id="91d00-127">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
