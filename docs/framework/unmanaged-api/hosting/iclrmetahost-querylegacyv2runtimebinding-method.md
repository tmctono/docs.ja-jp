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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e7312a50137ab8a5c066d5e140a1742ee1918b44
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776563"
---
# <a name="iclrmetahostquerylegacyv2runtimebinding-method"></a><span data-ttu-id="bf517-102">ICLRMetaHost::QueryLegacyV2RuntimeBinding メソッド</span><span class="sxs-lookup"><span data-stu-id="bf517-102">ICLRMetaHost::QueryLegacyV2RuntimeBinding Method</span></span>
<span data-ttu-id="bf517-103">レガシ アクティブ化ポリシーが関連付けられてなどを使用してランタイムを表すインターフェイスを返します、`useLegacyV2RuntimeActivationPolicy`属性を[ \<startup > 要素](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)ダイレクトを使用して、構成ファイルのエントリレガシ アクティブ化 Api、または呼び出すことによって、 [iclrruntimeinfo::bindaslegacyv2runtime](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-bindaslegacyv2runtime-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="bf517-103">Returns an interface that represents a runtime to which legacy activation policy has been bound, for example, by using the `useLegacyV2RuntimeActivationPolicy` attribute on the [\<startup> element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) configuration file entry, by direct use of the legacy activation APIs, or by calling the [ICLRRuntimeInfo::BindAsLegacyV2Runtime](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-bindaslegacyv2runtime-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf517-104">構文</span><span class="sxs-lookup"><span data-stu-id="bf517-104">Syntax</span></span>  
  
```cpp  
HRESULT QueryLegacyV2RuntimeBinding (  
    [in] REFIID riid,  
    [out, iid_is(riid), retval] LPVOID *ppUnk);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bf517-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="bf517-105">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="bf517-106">[in]このパラメーターの唯一の有効な値は Required.Currently`IID_ICLRRuntimeInfo`します。</span><span class="sxs-lookup"><span data-stu-id="bf517-106">[in] Required.Currently the only valid value for this parameter is `IID_ICLRRuntimeInfo`.</span></span>  
  
 `ppUnk`  
 <span data-ttu-id="bf517-107">[out] 必須。</span><span class="sxs-lookup"><span data-stu-id="bf517-107">[out] Required.</span></span> <span data-ttu-id="bf517-108">このメソッドから制御が戻るときにへのポインターを格納、 [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)レガシ アクティブ化ポリシーにバインドされているランタイムを表すインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="bf517-108">When this method returns, contains a pointer to the [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface that represents a runtime that has been bound to legacy activation policy.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bf517-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="bf517-109">Return Value</span></span>  
 <span data-ttu-id="bf517-110">このメソッドは、次の特定の HRESULT と、メソッドの失敗を示す HRESULT エラーも返します。</span><span class="sxs-lookup"><span data-stu-id="bf517-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="bf517-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="bf517-111">HRESULT</span></span>|<span data-ttu-id="bf517-112">説明</span><span class="sxs-lookup"><span data-stu-id="bf517-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="bf517-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="bf517-113">S_OK</span></span>|<span data-ttu-id="bf517-114">メソッドは正常に完了し、レガシ アクティブ化ポリシーにバインドされているランタイムが返されました。</span><span class="sxs-lookup"><span data-stu-id="bf517-114">The method completed successfully and returned a runtime that was bound to legacy activation policy.</span></span>|  
|<span data-ttu-id="bf517-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="bf517-115">S_FALSE</span></span>|<span data-ttu-id="bf517-116">メソッドは正常に完了しましたが、レガシ ランタイムはまだバインドされていません。</span><span class="sxs-lookup"><span data-stu-id="bf517-116">The method completed successfully, but a legacy runtime has not yet been bound.</span></span>|  
|<span data-ttu-id="bf517-117">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="bf517-117">E_NOINTERFACE</span></span>|<span data-ttu-id="bf517-118">メソッドで、レガシ アクティブ化ポリシーにバインドされているランタイムが見つかりましたが、`riid` はそのランタイムでサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="bf517-118">The method found a runtime that was bound to legacy activation policy, but `riid` is not supported by that runtime.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bf517-119">Remarks</span><span class="sxs-lookup"><span data-stu-id="bf517-119">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf517-120">必要条件</span><span class="sxs-lookup"><span data-stu-id="bf517-120">Requirements</span></span>  
 <span data-ttu-id="bf517-121">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bf517-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf517-122">**ヘッダー:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="bf517-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="bf517-123">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="bf517-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bf517-124">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bf517-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf517-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="bf517-125">See also</span></span>

- [<span data-ttu-id="bf517-126">ICLRMetaHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bf517-126">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)
- [<span data-ttu-id="bf517-127">ホスティング</span><span class="sxs-lookup"><span data-stu-id="bf517-127">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
