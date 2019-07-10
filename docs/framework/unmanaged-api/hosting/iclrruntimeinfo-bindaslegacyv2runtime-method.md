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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a0ea4bd222500015f6c78cb0455539aa2c24e681
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67765621"
---
# <a name="iclrruntimeinfobindaslegacyv2runtime-method"></a><span data-ttu-id="d5451-102">ICLRRuntimeInfo::BindAsLegacyV2Runtime メソッド</span><span class="sxs-lookup"><span data-stu-id="d5451-102">ICLRRuntimeInfo::BindAsLegacyV2Runtime Method</span></span>
<span data-ttu-id="d5451-103">すべてレガシ共通言語ランタイム (CLR) バージョン 2 のライセンス認証ポリシーの決定の現在のランタイムをバインドします。</span><span class="sxs-lookup"><span data-stu-id="d5451-103">Binds the current runtime for all legacy common language runtime (CLR) version 2 activation policy decisions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5451-104">構文</span><span class="sxs-lookup"><span data-stu-id="d5451-104">Syntax</span></span>  
  
```cpp  
HRESULT BindAsLegacyV2Runtime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="d5451-105">戻り値</span><span class="sxs-lookup"><span data-stu-id="d5451-105">Return Value</span></span>  
 <span data-ttu-id="d5451-106">このメソッドは、次の特定の Hresult を返します。</span><span class="sxs-lookup"><span data-stu-id="d5451-106">This method returns the following specific HRESULTs:</span></span>  
  
|<span data-ttu-id="d5451-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d5451-107">HRESULT</span></span>|<span data-ttu-id="d5451-108">説明</span><span class="sxs-lookup"><span data-stu-id="d5451-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d5451-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="d5451-109">S_OK</span></span>|<span data-ttu-id="d5451-110">バインドが成功したか、このランタイムは、従来の CLR バージョン 2 のアクティブ化ポリシー ランタイムと既にバインドされています。</span><span class="sxs-lookup"><span data-stu-id="d5451-110">Either binding succeeded, or this runtime was already bound as the legacy CLR version 2 activation policy runtime.</span></span>|  
|<span data-ttu-id="d5451-111">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span><span class="sxs-lookup"><span data-stu-id="d5451-111">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span></span>|<span data-ttu-id="d5451-112">別のランタイムは、従来の CLR バージョン 2 のアクティブ化ポリシーに既にバインドされています。</span><span class="sxs-lookup"><span data-stu-id="d5451-112">A different runtime was already bound to the legacy CLR version 2 activation policy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d5451-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="d5451-113">Remarks</span></span>  
 <span data-ttu-id="d5451-114">現在のランタイムがすべてレガシ CLR バージョン 2 のライセンス認証ポリシーの決定に既にバインドされている場合 (などを使用して、`useLegacyV2RuntimeActivationPolicy`属性を[ \<startup > 要素](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)構成ファイルで)、このメソッドエラーの結果を返しません代わりに、なりますメソッドがレガシ アクティブ化ポリシーを正常にバインドしたかどうかと同様に、結果は、s_ok を返します。</span><span class="sxs-lookup"><span data-stu-id="d5451-114">If the current runtime is already bound for all legacy CLR version 2 activation policy decisions (for example, by using the `useLegacyV2RuntimeActivationPolicy` attribute on the [\<startup> element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) in the configuration file), this method does not return an error result; instead, the result is S_OK, just as it would be if the method had successfully bound legacy activation policy.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d5451-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="d5451-115">Requirements</span></span>  
 <span data-ttu-id="d5451-116">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d5451-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5451-117">**ヘッダー:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="d5451-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="d5451-118">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="d5451-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d5451-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5451-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5451-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="d5451-120">See also</span></span>

- [<span data-ttu-id="d5451-121">ICLRRuntimeInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d5451-121">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="d5451-122">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d5451-122">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="d5451-123">ホスティング</span><span class="sxs-lookup"><span data-stu-id="d5451-123">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
- [<span data-ttu-id="d5451-124">\<startup> 要素</span><span class="sxs-lookup"><span data-stu-id="d5451-124">\<startup> Element</span></span>](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)
