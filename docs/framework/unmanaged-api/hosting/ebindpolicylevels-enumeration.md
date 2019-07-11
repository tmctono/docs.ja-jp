---
title: EBindPolicyLevels 列挙型
ms.date: 03/30/2017
api_name:
- EBindPolicyLevels
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EBindPolicyLevels
helpviewer_keywords:
- EBindPolicyLevels enumeration [.NET Framework hosting]
ms.assetid: a9e00b4f-b6d0-4257-bd88-4fe9af97b8fa
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e61acbb15844c5ddfc8b7aa98c41bb18c6e9ade5
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67769762"
---
# <a name="ebindpolicylevels-enumeration"></a><span data-ttu-id="d0277-102">EBindPolicyLevels 列挙型</span><span class="sxs-lookup"><span data-stu-id="d0277-102">EBindPolicyLevels Enumeration</span></span>
<span data-ttu-id="d0277-103">アセンブリのポリシーを変更または適用するレベルを指定するフラグを提供します。</span><span class="sxs-lookup"><span data-stu-id="d0277-103">Provides flags to specify the level at which to apply or modify assembly policy.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0277-104">構文</span><span class="sxs-lookup"><span data-stu-id="d0277-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    ePolicyLevelNone         = 0x0,  
    ePolicyLevelRetargetable = 0x1,  
    ePolicyUnifiedToCLR      = 0x2,  
    ePolicyLevelApp          = 0x4,  
    ePolicyLevelPublisher    = 0x8,  
    ePolicyLevelHost         = 0x10,  
    ePolicyLevelAdmin        = 0x20  
    ePolicyPortability       = 0x40  
} EBindPolicyLevels;  
```  
  
## <a name="members"></a><span data-ttu-id="d0277-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="d0277-105">Members</span></span>  
  
|<span data-ttu-id="d0277-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="d0277-106">Member</span></span>|<span data-ttu-id="d0277-107">説明</span><span class="sxs-lookup"><span data-stu-id="d0277-107">Description</span></span>|  
|------------|-----------------|  
|`ePolicyLevelAdmin`|<span data-ttu-id="d0277-108">ポリシーが、管理者レベルで適用することを指定します。</span><span class="sxs-lookup"><span data-stu-id="d0277-108">Specifies that policy should be applied at the administrator level.</span></span>|  
|`ePolicyLevelApp`|<span data-ttu-id="d0277-109">ポリシーが、アプリケーション レベルで適用することを指定します。</span><span class="sxs-lookup"><span data-stu-id="d0277-109">Specifies that policy should be applied at the application level.</span></span>|  
|`ePolicyLevelHost`|<span data-ttu-id="d0277-110">ポリシーが、ホスト レベルで適用することを指定します。</span><span class="sxs-lookup"><span data-stu-id="d0277-110">Specifies that policy should be applied at the host level.</span></span>|  
|`ePolicyLevelNone`|<span data-ttu-id="d0277-111">ポリシー レベルのフラグを指定しません。</span><span class="sxs-lookup"><span data-stu-id="d0277-111">Specifies no policy-level flags.</span></span>|  
|`ePolicyLevelPublisher`|<span data-ttu-id="d0277-112">ポリシーが、パブリッシャーのレベルで適用することを指定します。</span><span class="sxs-lookup"><span data-stu-id="d0277-112">Specifies that policy should be applied at the publisher level.</span></span>|  
|`ePolicyLevelRetargetable`|<span data-ttu-id="d0277-113">ポリシーをさまざまなレベルで適用できる必要がありますを指定します。</span><span class="sxs-lookup"><span data-stu-id="d0277-113">Specifies that policy should be applicable at variable levels.</span></span>|  
|`ePolicyPortability`|<span data-ttu-id="d0277-114">ポリシーが、.NET Framework アセンブリの実装間で移植性をサポートする必要がありますを指定します。</span><span class="sxs-lookup"><span data-stu-id="d0277-114">Specifies that policy should support portability between implementations of a .NET Framework assembly.</span></span> <span data-ttu-id="d0277-115">参照してください、 [ \<supportPortability >](../../../../docs/framework/configure-apps/file-schema/runtime/supportportability-element.md)構成ファイルの要素。</span><span class="sxs-lookup"><span data-stu-id="d0277-115">See the [\<supportPortability>](../../../../docs/framework/configure-apps/file-schema/runtime/supportportability-element.md) configuration file element.</span></span>|  
|`ePolicyUnifiedToCLR`|<span data-ttu-id="d0277-116">共通言語ランタイム (CLR) のポリシーを統合する必要がありますを指定します。</span><span class="sxs-lookup"><span data-stu-id="d0277-116">Specifies that policy should be unified to that of the common language runtime (CLR).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d0277-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="d0277-117">Remarks</span></span>  
 <span data-ttu-id="d0277-118">この列挙体は、のメソッドに渡される、 [ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)アプリケーション ポリシーの変更を指定するインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="d0277-118">This enumeration is passed to methods of the [ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md) interface to specify changes in application policy.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d0277-119">必要条件</span><span class="sxs-lookup"><span data-stu-id="d0277-119">Requirements</span></span>  
 <span data-ttu-id="d0277-120">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0277-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d0277-121">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d0277-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d0277-122">**ライブラリ:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d0277-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d0277-123">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d0277-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0277-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="d0277-124">See also</span></span>

- [<span data-ttu-id="d0277-125">ICLRAssemblyIdentityManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d0277-125">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="d0277-126">ホスティングの列挙型</span><span class="sxs-lookup"><span data-stu-id="d0277-126">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
