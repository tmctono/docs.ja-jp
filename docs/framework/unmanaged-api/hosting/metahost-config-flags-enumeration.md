---
title: METAHOST_CONFIG_FLAGS 列挙体
ms.date: 03/30/2017
api_name:
- METAHOST_CONFIG_FLAGS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- METAHOST_CONFIG_FLAGS
helpviewer_keywords:
- METAHOST_CONFIG_FLAGS enumeration [.NET Framework hosting]
ms.assetid: 6f1e389f-ed99-4d6a-a0ba-72d7d869a01d
topic_type:
- apiref
ms.openlocfilehash: 07cab119810c4da25d16a4ad7c13f2d2bda16455
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140313"
---
# <a name="metahost_config_flags-enumeration"></a><span data-ttu-id="f09bc-102">METAHOST_CONFIG_FLAGS 列挙体</span><span class="sxs-lookup"><span data-stu-id="f09bc-102">METAHOST_CONFIG_FLAGS Enumeration</span></span>
<span data-ttu-id="f09bc-103">[ICLRMetaHostPolicy:: GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)メソッドの `pdwConfigFlags` パラメーターで返されるフラグについて説明します。これは、の[\<スタートアップ > 要素](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)の `useLegacyV2RuntimeActivationPolicy` 属性の存在と設定を示します。構成ファイル。</span><span class="sxs-lookup"><span data-stu-id="f09bc-103">Describes the possible flags returned in the `pdwConfigFlags` parameter of the [ICLRMetaHostPolicy::GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) method, indicating the presence and setting of the `useLegacyV2RuntimeActivationPolicy` attribute in the [\<startup> element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) of the configuration file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f09bc-104">構文</span><span class="sxs-lookup"><span data-stu-id="f09bc-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_UNSET  = 0x00,  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_TRUE   = 0x01,  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_FALSE  = 0x02,  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_MASK   = 0x03  
} METAHOST_CONFIG_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="f09bc-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="f09bc-105">Members</span></span>  
  
|<span data-ttu-id="f09bc-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="f09bc-106">Member</span></span>|<span data-ttu-id="f09bc-107">説明</span><span class="sxs-lookup"><span data-stu-id="f09bc-107">Description</span></span>|  
|------------|-----------------|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_UNSET`|<span data-ttu-id="f09bc-108">`useLegacyV2RuntimeActivationPolicy` 属性が[\<スタートアップ > 要素](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)に存在しませんでした。</span><span class="sxs-lookup"><span data-stu-id="f09bc-108">The `useLegacyV2RuntimeActivationPolicy` attribute was not present in the [\<startup> Element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md).</span></span>|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_TRUE`|<span data-ttu-id="f09bc-109">`useLegacyV2RuntimeActivationPolicy` 属性が存在し、`true`に設定されています。</span><span class="sxs-lookup"><span data-stu-id="f09bc-109">The `useLegacyV2RuntimeActivationPolicy` attribute was present and set to `true`.</span></span>|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_FALSE`|<span data-ttu-id="f09bc-110">`useLegacyV2RuntimeActivationPolicy` 属性が存在し、`false`に設定されています。</span><span class="sxs-lookup"><span data-stu-id="f09bc-110">The `useLegacyV2RuntimeActivationPolicy` attribute was present and set to `false`.</span></span>|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_MASK`|<span data-ttu-id="f09bc-111">`useLegacyV2RuntimeActivationPolicy`に関連する値を取得するには、このマスクを `pdwConfigFlags` に返される値に適用します。</span><span class="sxs-lookup"><span data-stu-id="f09bc-111">Apply this mask to the value returned in `pdwConfigFlags` to get the values relevant to `useLegacyV2RuntimeActivationPolicy`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f09bc-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="f09bc-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f09bc-113">［要件］</span><span class="sxs-lookup"><span data-stu-id="f09bc-113">Requirements</span></span>  
 <span data-ttu-id="f09bc-114">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f09bc-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f09bc-115">**ヘッダー:** メタホスト .h</span><span class="sxs-lookup"><span data-stu-id="f09bc-115">**Header:** Metahost.h</span></span>  
  
 <span data-ttu-id="f09bc-116">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="f09bc-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f09bc-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f09bc-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f09bc-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="f09bc-118">See also</span></span>

- [<span data-ttu-id="f09bc-119">ホスティングの列挙型</span><span class="sxs-lookup"><span data-stu-id="f09bc-119">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
- [<span data-ttu-id="f09bc-120">GetRequestedRuntime メソッド</span><span class="sxs-lookup"><span data-stu-id="f09bc-120">GetRequestedRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)
- [<span data-ttu-id="f09bc-121">\<startup> 要素</span><span class="sxs-lookup"><span data-stu-id="f09bc-121">\<startup> Element</span></span>](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)
