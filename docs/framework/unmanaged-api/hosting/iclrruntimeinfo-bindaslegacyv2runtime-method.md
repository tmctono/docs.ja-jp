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
ms.openlocfilehash: 4390f379e5092cc59d123631f5e6d8da82e2bd7f
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703895"
---
# <a name="iclrruntimeinfobindaslegacyv2runtime-method"></a><span data-ttu-id="7bd7d-102">ICLRRuntimeInfo::BindAsLegacyV2Runtime メソッド</span><span class="sxs-lookup"><span data-stu-id="7bd7d-102">ICLRRuntimeInfo::BindAsLegacyV2Runtime Method</span></span>
<span data-ttu-id="7bd7d-103">すべてのレガシ共通言語ランタイム (CLR) バージョン2アクティブ化ポリシーの決定に現在のランタイムをバインドします。</span><span class="sxs-lookup"><span data-stu-id="7bd7d-103">Binds the current runtime for all legacy common language runtime (CLR) version 2 activation policy decisions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7bd7d-104">構文</span><span class="sxs-lookup"><span data-stu-id="7bd7d-104">Syntax</span></span>  
  
```cpp  
HRESULT BindAsLegacyV2Runtime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="7bd7d-105">戻り値</span><span class="sxs-lookup"><span data-stu-id="7bd7d-105">Return Value</span></span>  
 <span data-ttu-id="7bd7d-106">このメソッドは、次の特定の Hresult を返します。</span><span class="sxs-lookup"><span data-stu-id="7bd7d-106">This method returns the following specific HRESULTs:</span></span>  
  
|<span data-ttu-id="7bd7d-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7bd7d-107">HRESULT</span></span>|<span data-ttu-id="7bd7d-108">説明</span><span class="sxs-lookup"><span data-stu-id="7bd7d-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7bd7d-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="7bd7d-109">S_OK</span></span>|<span data-ttu-id="7bd7d-110">バインドが成功したか、またはこのランタイムが従来の CLR バージョン2アクティブ化ポリシーのランタイムとして既にバインドされています。</span><span class="sxs-lookup"><span data-stu-id="7bd7d-110">Either binding succeeded, or this runtime was already bound as the legacy CLR version 2 activation policy runtime.</span></span>|  
|<span data-ttu-id="7bd7d-111">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span><span class="sxs-lookup"><span data-stu-id="7bd7d-111">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span></span>|<span data-ttu-id="7bd7d-112">以前の CLR バージョン2のアクティブ化ポリシーに、別のランタイムが既にバインドされています。</span><span class="sxs-lookup"><span data-stu-id="7bd7d-112">A different runtime was already bound to the legacy CLR version 2 activation policy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7bd7d-113">解説</span><span class="sxs-lookup"><span data-stu-id="7bd7d-113">Remarks</span></span>  
 <span data-ttu-id="7bd7d-114">現在のランタイムがすべてのレガシ CLR バージョン2アクティブ化ポリシーの決定に対して既にバインドされている場合 (たとえば、 `useLegacyV2RuntimeActivationPolicy` 構成ファイルの[ \< startup> 要素](../../configure-apps/file-schema/startup/startup-element.md)で属性を使用する場合)、このメソッドはエラー結果を返しません。その代わり、メソッドが従来のアクティブ化ポリシーを正常にバインドした場合と同じように、結果は S_OK ます</span><span class="sxs-lookup"><span data-stu-id="7bd7d-114">If the current runtime is already bound for all legacy CLR version 2 activation policy decisions (for example, by using the `useLegacyV2RuntimeActivationPolicy` attribute on the [\<startup> element](../../configure-apps/file-schema/startup/startup-element.md) in the configuration file), this method does not return an error result; instead, the result is S_OK, just as it would be if the method had successfully bound legacy activation policy.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7bd7d-115">要件</span><span class="sxs-lookup"><span data-stu-id="7bd7d-115">Requirements</span></span>  
 <span data-ttu-id="7bd7d-116">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7bd7d-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7bd7d-117">**ヘッダー:** メタホスト .h</span><span class="sxs-lookup"><span data-stu-id="7bd7d-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="7bd7d-118">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="7bd7d-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7bd7d-119">**.NET Framework のバージョン:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7bd7d-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bd7d-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="7bd7d-120">See also</span></span>

- [<span data-ttu-id="7bd7d-121">ICLRRuntimeInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7bd7d-121">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="7bd7d-122">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7bd7d-122">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="7bd7d-123">ホスティング</span><span class="sxs-lookup"><span data-stu-id="7bd7d-123">Hosting</span></span>](index.md)
- [<span data-ttu-id="7bd7d-124">\<スタートアップ> 要素</span><span class="sxs-lookup"><span data-stu-id="7bd7d-124">\<startup> Element</span></span>](../../configure-apps/file-schema/startup/startup-element.md)
