---
title: ICLRRuntimeInfo::BindAsLegacyV2Runtime メソッド
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.BindAsLegacyV2Runtime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::BindAsLegacyV2Runtime
helpviewer_keywords:
- ICLRRuntimeInfo::BindAsLegacyV2Runtime method [.NET Framework hosting]
- BindAsLegacyV2Runtime method [.NET Framework hosting]
ms.assetid: 65fd55ac-4a24-4479-9384-a2e8013bfb2b
topic_type:
- apiref
ms.openlocfilehash: d37ec8e17e62f58212a5f79f4d6b6aa75f57bf7c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120254"
---
# <a name="iclrruntimeinfobindaslegacyv2runtime-method"></a><span data-ttu-id="10484-102">ICLRRuntimeInfo::BindAsLegacyV2Runtime メソッド</span><span class="sxs-lookup"><span data-stu-id="10484-102">ICLRRuntimeInfo::BindAsLegacyV2Runtime Method</span></span>
<span data-ttu-id="10484-103">すべてのレガシ共通言語ランタイム (CLR) バージョン2アクティブ化ポリシーの決定に現在のランタイムをバインドします。</span><span class="sxs-lookup"><span data-stu-id="10484-103">Binds the current runtime for all legacy common language runtime (CLR) version 2 activation policy decisions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10484-104">構文</span><span class="sxs-lookup"><span data-stu-id="10484-104">Syntax</span></span>  
  
```cpp  
HRESULT BindAsLegacyV2Runtime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="10484-105">戻り値</span><span class="sxs-lookup"><span data-stu-id="10484-105">Return Value</span></span>  
 <span data-ttu-id="10484-106">このメソッドは、次の特定の Hresult を返します。</span><span class="sxs-lookup"><span data-stu-id="10484-106">This method returns the following specific HRESULTs:</span></span>  
  
|<span data-ttu-id="10484-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="10484-107">HRESULT</span></span>|<span data-ttu-id="10484-108">説明</span><span class="sxs-lookup"><span data-stu-id="10484-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="10484-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="10484-109">S_OK</span></span>|<span data-ttu-id="10484-110">バインドが成功したか、またはこのランタイムが従来の CLR バージョン2アクティブ化ポリシーのランタイムとして既にバインドされています。</span><span class="sxs-lookup"><span data-stu-id="10484-110">Either binding succeeded, or this runtime was already bound as the legacy CLR version 2 activation policy runtime.</span></span>|  
|<span data-ttu-id="10484-111">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span><span class="sxs-lookup"><span data-stu-id="10484-111">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span></span>|<span data-ttu-id="10484-112">以前の CLR バージョン2のアクティブ化ポリシーに、別のランタイムが既にバインドされています。</span><span class="sxs-lookup"><span data-stu-id="10484-112">A different runtime was already bound to the legacy CLR version 2 activation policy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="10484-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="10484-113">Remarks</span></span>  
 <span data-ttu-id="10484-114">現在のランタイムが、すべてのレガシ CLR バージョン2アクティブ化ポリシーの決定に対して既にバインドされている場合 (たとえば、構成ファイルの[\<startup > 要素](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)の `useLegacyV2RuntimeActivationPolicy` 属性を使用した場合)、このメソッドはエラー結果を返しません。代わりに、メソッドが従来のアクティブ化ポリシーに正常にバインドされている場合と同様に、結果は S_OK になります。</span><span class="sxs-lookup"><span data-stu-id="10484-114">If the current runtime is already bound for all legacy CLR version 2 activation policy decisions (for example, by using the `useLegacyV2RuntimeActivationPolicy` attribute on the [\<startup> element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) in the configuration file), this method does not return an error result; instead, the result is S_OK, just as it would be if the method had successfully bound legacy activation policy.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10484-115">［要件］</span><span class="sxs-lookup"><span data-stu-id="10484-115">Requirements</span></span>  
 <span data-ttu-id="10484-116">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10484-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10484-117">**ヘッダー:** メタホスト .h</span><span class="sxs-lookup"><span data-stu-id="10484-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="10484-118">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="10484-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="10484-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10484-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10484-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="10484-120">See also</span></span>

- [<span data-ttu-id="10484-121">ICLRRuntimeInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="10484-121">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="10484-122">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="10484-122">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="10484-123">ホスティング</span><span class="sxs-lookup"><span data-stu-id="10484-123">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
- [<span data-ttu-id="10484-124">\<startup> 要素</span><span class="sxs-lookup"><span data-stu-id="10484-124">\<startup> Element</span></span>](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)
