---
title: CREATE_ASM_NAME_OBJ_FLAGS 列挙型
ms.date: 03/30/2017
api_name:
- CREATE_ASM_NAME_OBJ_FLAGS
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- CREATE_ASM_NAME_OBJ_FLAGS
helpviewer_keywords:
- CREATE_ASM_NAME_OBJ_FLAGS enumeration [.NET Framework fusion]
ms.assetid: a5ed2fd0-c7d2-4603-aaca-5d0caad92675
topic_type:
- apiref
ms.openlocfilehash: ee856dbd398d0fa5e3eee7d9b2b2cfc7c7a57ecf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176592"
---
# <a name="create_asm_name_obj_flags-enumeration"></a><span data-ttu-id="7d88c-102">CREATE_ASM_NAME_OBJ_FLAGS 列挙型</span><span class="sxs-lookup"><span data-stu-id="7d88c-102">CREATE_ASM_NAME_OBJ_FLAGS Enumeration</span></span>
<span data-ttu-id="7d88c-103">関数によって構築されるときに[、IAssemblyName インターフェイス](iassemblyname-interface.md)オブジェクトの属性を指定[します](createassemblynameobject-function.md)。</span><span class="sxs-lookup"><span data-stu-id="7d88c-103">Specifies the attributes of an [IAssemblyName Interface](iassemblyname-interface.md) object when it is constructed by the [CreateAssemblyNameObject](createassemblynameobject-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d88c-104">構文</span><span class="sxs-lookup"><span data-stu-id="7d88c-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
  
    CANOF_PARSE_DISPLAY_NAME            = 0x1,  
    CANOF_SET_DEFAULT_VALUES            = 0x2,  
    CANOF_VERIFY_FRIEND_ASSEMBLYNAME    = 0x4,  
    CANOF_PARSE_FRIEND_DISPLAY_NAME     =
        CANOF_PARSE_DISPLAY_NAME | CANOF_VERIFY_FRIEND_ASSEMBLYNAME  
  
} CREATE_ASM_NAME_OBJ_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="7d88c-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="7d88c-105">Members</span></span>  
  
|<span data-ttu-id="7d88c-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="7d88c-106">Member</span></span>|<span data-ttu-id="7d88c-107">説明</span><span class="sxs-lookup"><span data-stu-id="7d88c-107">Description</span></span>|  
|------------|-----------------|  
|`CANOF_PARSE_DISPLAY_NAME`|<span data-ttu-id="7d88c-108">渡されたパラメーターがテキスト ID であることを示します。</span><span class="sxs-lookup"><span data-stu-id="7d88c-108">Indicates that the parameter passed is a textual identity.</span></span>|  
|`CANOF_SET_DEFAULT_VALUES`|<span data-ttu-id="7d88c-109">いくつかのデフォルト値を設定します。</span><span class="sxs-lookup"><span data-stu-id="7d88c-109">Sets a few default values.</span></span>|  
|`CANOF_VERIFY_FRIEND_ASSEMBLYNAME`|<span data-ttu-id="7d88c-110">フレンド アセンブリの規則を検証します (名前と公開キーのみ)。</span><span class="sxs-lookup"><span data-stu-id="7d88c-110">Verifies the friend assembly rule (only name and public key).</span></span> <span data-ttu-id="7d88c-111">このメンバーは内部使用専用です。</span><span class="sxs-lookup"><span data-stu-id="7d88c-111">This member is for internal use only.</span></span>|  
|`CANOF_PARSE_FRIEND_DISPLAY_NAME`|<span data-ttu-id="7d88c-112">`CANOF_PARSE_DISPLAY_NAME`フラグと フラグ`CANOF_VERIFY_FRIEND_ASSEMBLYNAME`の組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="7d88c-112">A combination of the `CANOF_PARSE_DISPLAY_NAME` and `CANOF_VERIFY_FRIEND_ASSEMBLYNAME` flags.</span></span> <span data-ttu-id="7d88c-113">このメンバーは内部使用専用です。</span><span class="sxs-lookup"><span data-stu-id="7d88c-113">This member is for internal use only.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7d88c-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="7d88c-114">Requirements</span></span>  
 <span data-ttu-id="7d88c-115">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d88c-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d88c-116">**ヘッダー:** フュージョン.h</span><span class="sxs-lookup"><span data-stu-id="7d88c-116">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="7d88c-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d88c-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d88c-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="7d88c-118">See also</span></span>

- [<span data-ttu-id="7d88c-119">IAssemblyName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7d88c-119">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="7d88c-120">CreateAssemblyNameObject 関数</span><span class="sxs-lookup"><span data-stu-id="7d88c-120">CreateAssemblyNameObject Function</span></span>](createassemblynameobject-function.md)
- [<span data-ttu-id="7d88c-121">fusion 列挙体</span><span class="sxs-lookup"><span data-stu-id="7d88c-121">Fusion Enumerations</span></span>](fusion-enumerations.md)
