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
ms.openlocfilehash: a15c912cdf0eef1b8f131e8425ad9b5b01289982
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "84006728"
---
# <a name="metahost_config_flags-enumeration"></a><span data-ttu-id="cd32c-102">METAHOST_CONFIG_FLAGS 列挙体</span><span class="sxs-lookup"><span data-stu-id="cd32c-102">METAHOST_CONFIG_FLAGS Enumeration</span></span>
<span data-ttu-id="cd32c-103">`pdwConfigFlags` [ICLRMetaHostPolicy:: GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)メソッドのパラメーターで返されるフラグについて説明します。これは、 `useLegacyV2RuntimeActivationPolicy` 構成ファイルの[ \<startup> 要素](../../configure-apps/file-schema/startup/startup-element.md)内の属性の存在と設定を示します。</span><span class="sxs-lookup"><span data-stu-id="cd32c-103">Describes the possible flags returned in the `pdwConfigFlags` parameter of the [ICLRMetaHostPolicy::GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) method, indicating the presence and setting of the `useLegacyV2RuntimeActivationPolicy` attribute in the [\<startup> element](../../configure-apps/file-schema/startup/startup-element.md) of the configuration file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd32c-104">構文</span><span class="sxs-lookup"><span data-stu-id="cd32c-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_UNSET  = 0x00,  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_TRUE   = 0x01,  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_FALSE  = 0x02,  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_MASK   = 0x03  
} METAHOST_CONFIG_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="cd32c-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="cd32c-105">Members</span></span>  
  
|<span data-ttu-id="cd32c-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="cd32c-106">Member</span></span>|<span data-ttu-id="cd32c-107">説明</span><span class="sxs-lookup"><span data-stu-id="cd32c-107">Description</span></span>|  
|------------|-----------------|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_UNSET`|<span data-ttu-id="cd32c-108">`useLegacyV2RuntimeActivationPolicy`属性が[ \<startup> 要素](../../configure-apps/file-schema/startup/startup-element.md)内に存在しませんでした。</span><span class="sxs-lookup"><span data-stu-id="cd32c-108">The `useLegacyV2RuntimeActivationPolicy` attribute was not present in the [\<startup> Element](../../configure-apps/file-schema/startup/startup-element.md).</span></span>|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_TRUE`|<span data-ttu-id="cd32c-109">`useLegacyV2RuntimeActivationPolicy`属性が存在し、がに設定されて `true` います。</span><span class="sxs-lookup"><span data-stu-id="cd32c-109">The `useLegacyV2RuntimeActivationPolicy` attribute was present and set to `true`.</span></span>|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_FALSE`|<span data-ttu-id="cd32c-110">`useLegacyV2RuntimeActivationPolicy`属性が存在し、がに設定されて `false` います。</span><span class="sxs-lookup"><span data-stu-id="cd32c-110">The `useLegacyV2RuntimeActivationPolicy` attribute was present and set to `false`.</span></span>|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_MASK`|<span data-ttu-id="cd32c-111">に関連する値を取得するには、このマスクをで返される値に適用 `pdwConfigFlags` `useLegacyV2RuntimeActivationPolicy` します。</span><span class="sxs-lookup"><span data-stu-id="cd32c-111">Apply this mask to the value returned in `pdwConfigFlags` to get the values relevant to `useLegacyV2RuntimeActivationPolicy`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cd32c-112">解説</span><span class="sxs-lookup"><span data-stu-id="cd32c-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd32c-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="cd32c-113">Requirements</span></span>  
 <span data-ttu-id="cd32c-114">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cd32c-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd32c-115">**ヘッダー:** メタホスト .h</span><span class="sxs-lookup"><span data-stu-id="cd32c-115">**Header:** Metahost.h</span></span>  
  
 <span data-ttu-id="cd32c-116">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="cd32c-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cd32c-117">**.NET Framework のバージョン:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd32c-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd32c-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="cd32c-118">See also</span></span>

- [<span data-ttu-id="cd32c-119">ホスティングの列挙型</span><span class="sxs-lookup"><span data-stu-id="cd32c-119">Hosting Enumerations</span></span>](hosting-enumerations.md)
- [<span data-ttu-id="cd32c-120">GetRequestedRuntime メソッド</span><span class="sxs-lookup"><span data-stu-id="cd32c-120">GetRequestedRuntime Method</span></span>](iclrmetahostpolicy-getrequestedruntime-method.md)
- [<span data-ttu-id="cd32c-121">\<startup>Element</span><span class="sxs-lookup"><span data-stu-id="cd32c-121">\<startup> Element</span></span>](../../configure-apps/file-schema/startup/startup-element.md)
