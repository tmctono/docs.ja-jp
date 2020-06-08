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
ms.openlocfilehash: b270a6691d4e4ee4a5d0b42f424694eb7993e4e7
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504148"
---
# <a name="iclrmetahostquerylegacyv2runtimebinding-method"></a><span data-ttu-id="4e3e6-102">ICLRMetaHost::QueryLegacyV2RuntimeBinding メソッド</span><span class="sxs-lookup"><span data-stu-id="4e3e6-102">ICLRMetaHost::QueryLegacyV2RuntimeBinding Method</span></span>
<span data-ttu-id="4e3e6-103">レガシアクティブ化ポリシーがバインドされているランタイムを表すインターフェイスを返します。たとえば、 `useLegacyV2RuntimeActivationPolicy` [ \<startup> 要素](../../configure-apps/file-schema/startup/startup-element.md)構成ファイルのエントリで属性を使用するか、レガシアクティベーション api を直接使用するか、 [ICLRRuntimeInfo:: BindAsLegacyV2Runtime](iclrruntimeinfo-bindaslegacyv2runtime-method.md)メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="4e3e6-103">Returns an interface that represents a runtime to which legacy activation policy has been bound, for example, by using the `useLegacyV2RuntimeActivationPolicy` attribute on the [\<startup> element](../../configure-apps/file-schema/startup/startup-element.md) configuration file entry, by direct use of the legacy activation APIs, or by calling the [ICLRRuntimeInfo::BindAsLegacyV2Runtime](iclrruntimeinfo-bindaslegacyv2runtime-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e3e6-104">構文</span><span class="sxs-lookup"><span data-stu-id="4e3e6-104">Syntax</span></span>  
  
```cpp  
HRESULT QueryLegacyV2RuntimeBinding (  
    [in] REFIID riid,  
    [out, iid_is(riid), retval] LPVOID *ppUnk);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4e3e6-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4e3e6-105">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="4e3e6-106">から必須。現時点では、このパラメーターの有効な `IID_ICLRRuntimeInfo` 値はのみです。</span><span class="sxs-lookup"><span data-stu-id="4e3e6-106">[in] Required.Currently the only valid value for this parameter is `IID_ICLRRuntimeInfo`.</span></span>  
  
 `ppUnk`  
 <span data-ttu-id="4e3e6-107">[out] 必須。</span><span class="sxs-lookup"><span data-stu-id="4e3e6-107">[out] Required.</span></span> <span data-ttu-id="4e3e6-108">このメソッドから制御が戻るときに、レガシアクティブ化ポリシーにバインドされているランタイムを表す[ICLRRuntimeInfo](iclrruntimeinfo-interface.md)インターフェイスへのポインターを格納します。</span><span class="sxs-lookup"><span data-stu-id="4e3e6-108">When this method returns, contains a pointer to the [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface that represents a runtime that has been bound to legacy activation policy.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4e3e6-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="4e3e6-109">Return Value</span></span>  
 <span data-ttu-id="4e3e6-110">このメソッドは、次の特定の HRESULT と、メソッドの失敗を示す HRESULT エラーも返します。</span><span class="sxs-lookup"><span data-stu-id="4e3e6-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="4e3e6-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4e3e6-111">HRESULT</span></span>|<span data-ttu-id="4e3e6-112">説明</span><span class="sxs-lookup"><span data-stu-id="4e3e6-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4e3e6-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="4e3e6-113">S_OK</span></span>|<span data-ttu-id="4e3e6-114">メソッドは正常に完了し、レガシ アクティブ化ポリシーにバインドされているランタイムが返されました。</span><span class="sxs-lookup"><span data-stu-id="4e3e6-114">The method completed successfully and returned a runtime that was bound to legacy activation policy.</span></span>|  
|<span data-ttu-id="4e3e6-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="4e3e6-115">S_FALSE</span></span>|<span data-ttu-id="4e3e6-116">メソッドは正常に完了しましたが、レガシ ランタイムはまだバインドされていません。</span><span class="sxs-lookup"><span data-stu-id="4e3e6-116">The method completed successfully, but a legacy runtime has not yet been bound.</span></span>|  
|<span data-ttu-id="4e3e6-117">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="4e3e6-117">E_NOINTERFACE</span></span>|<span data-ttu-id="4e3e6-118">メソッドで、レガシ アクティブ化ポリシーにバインドされているランタイムが見つかりましたが、`riid` はそのランタイムでサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="4e3e6-118">The method found a runtime that was bound to legacy activation policy, but `riid` is not supported by that runtime.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4e3e6-119">解説</span><span class="sxs-lookup"><span data-stu-id="4e3e6-119">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e3e6-120">必要条件</span><span class="sxs-lookup"><span data-stu-id="4e3e6-120">Requirements</span></span>  
 <span data-ttu-id="4e3e6-121">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4e3e6-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e3e6-122">**ヘッダー:** メタホスト .h</span><span class="sxs-lookup"><span data-stu-id="4e3e6-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="4e3e6-123">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="4e3e6-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4e3e6-124">**.NET Framework のバージョン:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e3e6-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e3e6-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="4e3e6-125">See also</span></span>

- [<span data-ttu-id="4e3e6-126">ICLRMetaHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4e3e6-126">ICLRMetaHost Interface</span></span>](iclrmetahost-interface.md)
- [<span data-ttu-id="4e3e6-127">ホスティング</span><span class="sxs-lookup"><span data-stu-id="4e3e6-127">Hosting</span></span>](index.md)
