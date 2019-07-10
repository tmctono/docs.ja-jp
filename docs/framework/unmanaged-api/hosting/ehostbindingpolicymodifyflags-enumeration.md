---
title: EHostBindingPolicyModifyFlags 列挙型
ms.date: 03/30/2017
api_name:
- EHostBindingPolicyModifyFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EHostBindingPolicyModifyFlags
helpviewer_keywords:
- EHostBindingPolicyModifyFlags enumeration [.NET Framework hosting]
ms.assetid: 0339af16-ee1d-48ec-837d-a79d9a9c89f8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d70f7dd872cefbadce56c577ce2ecc9cbcb663b3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67765854"
---
# <a name="ehostbindingpolicymodifyflags-enumeration"></a><span data-ttu-id="788ee-102">EHostBindingPolicyModifyFlags 列挙型</span><span class="sxs-lookup"><span data-stu-id="788ee-102">EHostBindingPolicyModifyFlags Enumeration</span></span>
<span data-ttu-id="788ee-103">により、ホストは、ターゲット アセンブリにソース アセンブリからポリシーの変更を適用するときに、共通言語ランタイム (CLR) を実行する必要がありますのリダイレクトの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="788ee-103">Allows the host to specify the type of redirection the common language runtime (CLR) should perform when applying policy modifications from a source assembly to a target assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="788ee-104">構文</span><span class="sxs-lookup"><span data-stu-id="788ee-104">Syntax</span></span>  
  
```cpp  
typedef enum _hostBindingPolicyModifyFlags {  
    HOST_BINDING_POLICY_MODIFY_DEFAULT  = 0,  
    HOST_BINDING_POLICY_MODIFY_CHAIN    = 1,  
    HOST_BINDING_POLICY_MODIFY_REMOVE   = 2,  
    HOST_BINDING_POLICY_MODIFY_MAX      = 3  
} EHostBindingPolicyModifyFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="788ee-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="788ee-105">Members</span></span>  
  
|<span data-ttu-id="788ee-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="788ee-106">Member</span></span>|<span data-ttu-id="788ee-107">説明</span><span class="sxs-lookup"><span data-stu-id="788ee-107">Description</span></span>|  
|------------|-----------------|  
|`HOST_BINDING_POLICY_MODIFY_CHAIN`|<span data-ttu-id="788ee-108">CLR がターゲット アセンブリの上にソース アセンブリのポリシー値をチェーンするを指定します。</span><span class="sxs-lookup"><span data-stu-id="788ee-108">Specifies that the CLR will chain policy values of the source assembly onto those of the target assembly.</span></span>|  
|`HOST_BINDING_POLICY_MODIFY_DEFAULT`|<span data-ttu-id="788ee-109">CLR が既定のアクションを実行することを指定します。</span><span class="sxs-lookup"><span data-stu-id="788ee-109">Specifies that the CLR will perform the default action.</span></span>|  
|`HOST_BINDING_POLICY_MODIFY_MAX`|<span data-ttu-id="788ee-110">CLR が最大値にターゲット アセンブリのポリシー値を設定するを指定します。</span><span class="sxs-lookup"><span data-stu-id="788ee-110">Specifies that the CLR will set the policy values of the target assembly to the maximum values.</span></span>|  
|`HOST_BINDING_POLICY_MODIFY_REMOVE`|<span data-ttu-id="788ee-111">CLR がソース アセンブリのターゲット アセンブリのポリシー値を置き換えることを指定します。</span><span class="sxs-lookup"><span data-stu-id="788ee-111">Specifies that the CLR will replace policy values of the target assembly with those of the source assembly.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="788ee-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="788ee-112">Remarks</span></span>  
 <span data-ttu-id="788ee-113">[Iclrhostbindingpolicymanager::modifyapplicationpolicy](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md)メソッドは、型のパラメーターを受け取る`EHostBindingPolicyModifyFlags`します。</span><span class="sxs-lookup"><span data-stu-id="788ee-113">The [ICLRHostBindingPolicyManager::ModifyApplicationPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md) method takes a parameter of type `EHostBindingPolicyModifyFlags`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="788ee-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="788ee-114">Requirements</span></span>  
 <span data-ttu-id="788ee-115">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="788ee-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="788ee-116">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="788ee-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="788ee-117">**ライブラリ:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="788ee-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="788ee-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="788ee-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="788ee-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="788ee-119">See also</span></span>

- [<span data-ttu-id="788ee-120">ICLRHostBindingPolicyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="788ee-120">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
- [<span data-ttu-id="788ee-121">ホスティングの列挙型</span><span class="sxs-lookup"><span data-stu-id="788ee-121">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
