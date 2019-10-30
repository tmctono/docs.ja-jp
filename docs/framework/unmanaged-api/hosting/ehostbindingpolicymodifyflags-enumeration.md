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
ms.openlocfilehash: a2faf22b48dd0b809d6c3668a37f2119733a9b18
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129449"
---
# <a name="ehostbindingpolicymodifyflags-enumeration"></a><span data-ttu-id="0ddb1-102">EHostBindingPolicyModifyFlags 列挙型</span><span class="sxs-lookup"><span data-stu-id="0ddb1-102">EHostBindingPolicyModifyFlags Enumeration</span></span>
<span data-ttu-id="0ddb1-103">ソースアセンブリからターゲットアセンブリにポリシー変更を適用するときに、共通言語ランタイム (CLR) が実行するリダイレクトの種類をホストが指定できるようにします。</span><span class="sxs-lookup"><span data-stu-id="0ddb1-103">Allows the host to specify the type of redirection the common language runtime (CLR) should perform when applying policy modifications from a source assembly to a target assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ddb1-104">構文</span><span class="sxs-lookup"><span data-stu-id="0ddb1-104">Syntax</span></span>  
  
```cpp  
typedef enum _hostBindingPolicyModifyFlags {  
    HOST_BINDING_POLICY_MODIFY_DEFAULT  = 0,  
    HOST_BINDING_POLICY_MODIFY_CHAIN    = 1,  
    HOST_BINDING_POLICY_MODIFY_REMOVE   = 2,  
    HOST_BINDING_POLICY_MODIFY_MAX      = 3  
} EHostBindingPolicyModifyFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="0ddb1-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="0ddb1-105">Members</span></span>  
  
|<span data-ttu-id="0ddb1-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="0ddb1-106">Member</span></span>|<span data-ttu-id="0ddb1-107">説明</span><span class="sxs-lookup"><span data-stu-id="0ddb1-107">Description</span></span>|  
|------------|-----------------|  
|`HOST_BINDING_POLICY_MODIFY_CHAIN`|<span data-ttu-id="0ddb1-108">CLR がソースアセンブリのポリシー値をターゲットアセンブリのポリシー値に連結するように指定します。</span><span class="sxs-lookup"><span data-stu-id="0ddb1-108">Specifies that the CLR will chain policy values of the source assembly onto those of the target assembly.</span></span>|  
|`HOST_BINDING_POLICY_MODIFY_DEFAULT`|<span data-ttu-id="0ddb1-109">CLR が既定のアクションを実行することを指定します。</span><span class="sxs-lookup"><span data-stu-id="0ddb1-109">Specifies that the CLR will perform the default action.</span></span>|  
|`HOST_BINDING_POLICY_MODIFY_MAX`|<span data-ttu-id="0ddb1-110">CLR がターゲットアセンブリのポリシー値を最大値に設定することを指定します。</span><span class="sxs-lookup"><span data-stu-id="0ddb1-110">Specifies that the CLR will set the policy values of the target assembly to the maximum values.</span></span>|  
|`HOST_BINDING_POLICY_MODIFY_REMOVE`|<span data-ttu-id="0ddb1-111">CLR がターゲットアセンブリのポリシー値をソースアセンブリのポリシー値に置き換えることを指定します。</span><span class="sxs-lookup"><span data-stu-id="0ddb1-111">Specifies that the CLR will replace policy values of the target assembly with those of the source assembly.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0ddb1-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="0ddb1-112">Remarks</span></span>  
 <span data-ttu-id="0ddb1-113">[ICLRHostBindingPolicyManager:: ModifyApplicationPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md)メソッドは `EHostBindingPolicyModifyFlags`型のパラメーターを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="0ddb1-113">The [ICLRHostBindingPolicyManager::ModifyApplicationPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md) method takes a parameter of type `EHostBindingPolicyModifyFlags`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ddb1-114">［要件］</span><span class="sxs-lookup"><span data-stu-id="0ddb1-114">Requirements</span></span>  
 <span data-ttu-id="0ddb1-115">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0ddb1-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ddb1-116">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="0ddb1-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0ddb1-117">**ライブラリ:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="0ddb1-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0ddb1-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ddb1-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ddb1-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="0ddb1-119">See also</span></span>

- [<span data-ttu-id="0ddb1-120">ICLRHostBindingPolicyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0ddb1-120">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
- [<span data-ttu-id="0ddb1-121">ホスティングの列挙型</span><span class="sxs-lookup"><span data-stu-id="0ddb1-121">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
