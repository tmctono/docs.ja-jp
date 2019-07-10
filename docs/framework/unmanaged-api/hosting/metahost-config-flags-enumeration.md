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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 13a7ad5b59dd318f823645d28f9c3ccbec8a8cb0
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781086"
---
# <a name="metahostconfigflags-enumeration"></a><span data-ttu-id="9eb8d-102">METAHOST_CONFIG_FLAGS 列挙体</span><span class="sxs-lookup"><span data-stu-id="9eb8d-102">METAHOST_CONFIG_FLAGS Enumeration</span></span>
<span data-ttu-id="9eb8d-103">返される可能性のフラグについて説明します、`pdwConfigFlags`のパラメーター、 [iclrmetahostpolicy::getrequestedruntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)メソッド、および設定するかどうかを示す、`useLegacyV2RuntimeActivationPolicy`属性、 [ \<startup > 要素](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)の構成ファイル。</span><span class="sxs-lookup"><span data-stu-id="9eb8d-103">Describes the possible flags returned in the `pdwConfigFlags` parameter of the [ICLRMetaHostPolicy::GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) method, indicating the presence and setting of the `useLegacyV2RuntimeActivationPolicy` attribute in the [\<startup> element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) of the configuration file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9eb8d-104">構文</span><span class="sxs-lookup"><span data-stu-id="9eb8d-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_UNSET  = 0x00,  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_TRUE   = 0x01,  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_FALSE  = 0x02,  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_MASK   = 0x03  
} METAHOST_CONFIG_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="9eb8d-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="9eb8d-105">Members</span></span>  
  
|<span data-ttu-id="9eb8d-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="9eb8d-106">Member</span></span>|<span data-ttu-id="9eb8d-107">説明</span><span class="sxs-lookup"><span data-stu-id="9eb8d-107">Description</span></span>|  
|------------|-----------------|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_UNSET`|<span data-ttu-id="9eb8d-108">`useLegacyV2RuntimeActivationPolicy`属性されました内に存在しない、 [ \<startup > 要素](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)します。</span><span class="sxs-lookup"><span data-stu-id="9eb8d-108">The `useLegacyV2RuntimeActivationPolicy` attribute was not present in the [\<startup> Element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md).</span></span>|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_TRUE`|<span data-ttu-id="9eb8d-109">`useLegacyV2RuntimeActivationPolicy`属性が存在し、設定を`true`します。</span><span class="sxs-lookup"><span data-stu-id="9eb8d-109">The `useLegacyV2RuntimeActivationPolicy` attribute was present and set to `true`.</span></span>|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_FALSE`|<span data-ttu-id="9eb8d-110">`useLegacyV2RuntimeActivationPolicy`属性が存在し、設定を`false`します。</span><span class="sxs-lookup"><span data-stu-id="9eb8d-110">The `useLegacyV2RuntimeActivationPolicy` attribute was present and set to `false`.</span></span>|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_MASK`|<span data-ttu-id="9eb8d-111">このマスクで返される値に適用`pdwConfigFlags`に関連する値を取得する`useLegacyV2RuntimeActivationPolicy`します。</span><span class="sxs-lookup"><span data-stu-id="9eb8d-111">Apply this mask to the value returned in `pdwConfigFlags` to get the values relevant to `useLegacyV2RuntimeActivationPolicy`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9eb8d-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="9eb8d-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9eb8d-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="9eb8d-113">Requirements</span></span>  
 <span data-ttu-id="9eb8d-114">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9eb8d-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9eb8d-115">**ヘッダー:** Metahost.h</span><span class="sxs-lookup"><span data-stu-id="9eb8d-115">**Header:** Metahost.h</span></span>  
  
 <span data-ttu-id="9eb8d-116">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="9eb8d-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9eb8d-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9eb8d-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9eb8d-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="9eb8d-118">See also</span></span>

- [<span data-ttu-id="9eb8d-119">ホスティングの列挙型</span><span class="sxs-lookup"><span data-stu-id="9eb8d-119">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
- [<span data-ttu-id="9eb8d-120">GetRequestedRuntime メソッド</span><span class="sxs-lookup"><span data-stu-id="9eb8d-120">GetRequestedRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)
- [<span data-ttu-id="9eb8d-121">\<startup> 要素</span><span class="sxs-lookup"><span data-stu-id="9eb8d-121">\<startup> Element</span></span>](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)
