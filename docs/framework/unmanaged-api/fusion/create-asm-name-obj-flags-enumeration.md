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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9897e396424b9076da8f30c61b5a14cfa9539690
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795424"
---
# <a name="create_asm_name_obj_flags-enumeration"></a><span data-ttu-id="167d7-102">CREATE_ASM_NAME_OBJ_FLAGS 列挙型</span><span class="sxs-lookup"><span data-stu-id="167d7-102">CREATE_ASM_NAME_OBJ_FLAGS Enumeration</span></span>
<span data-ttu-id="167d7-103">[Createassemblynameobject](createassemblynameobject-function.md)関数によって構築されるときに、 [IAssemblyName Interface](iassemblyname-interface.md)オブジェクトの属性を指定します。</span><span class="sxs-lookup"><span data-stu-id="167d7-103">Specifies the attributes of an [IAssemblyName Interface](iassemblyname-interface.md) object when it is constructed by the [CreateAssemblyNameObject](createassemblynameobject-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="167d7-104">構文</span><span class="sxs-lookup"><span data-stu-id="167d7-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
  
    CANOF_PARSE_DISPLAY_NAME            = 0x1,  
    CANOF_SET_DEFAULT_VALUES            = 0x2,  
    CANOF_VERIFY_FRIEND_ASSEMBLYNAME    = 0x4,  
    CANOF_PARSE_FRIEND_DISPLAY_NAME     =   
        CANOF_PARSE_DISPLAY_NAME | CANOF_VERIFY_FRIEND_ASSEMBLYNAME  
  
} CREATE_ASM_NAME_OBJ_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="167d7-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="167d7-105">Members</span></span>  
  
|<span data-ttu-id="167d7-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="167d7-106">Member</span></span>|<span data-ttu-id="167d7-107">説明</span><span class="sxs-lookup"><span data-stu-id="167d7-107">Description</span></span>|  
|------------|-----------------|  
|`CANOF_PARSE_DISPLAY_NAME`|<span data-ttu-id="167d7-108">渡されたパラメーターがテキスト形式の id であることを示します。</span><span class="sxs-lookup"><span data-stu-id="167d7-108">Indicates that the parameter passed is a textual identity.</span></span>|  
|`CANOF_SET_DEFAULT_VALUES`|<span data-ttu-id="167d7-109">いくつかの既定値を設定します。</span><span class="sxs-lookup"><span data-stu-id="167d7-109">Sets a few default values.</span></span>|  
|`CANOF_VERIFY_FRIEND_ASSEMBLYNAME`|<span data-ttu-id="167d7-110">フレンドアセンブリの規則 (名前と公開キーのみ) を確認します。</span><span class="sxs-lookup"><span data-stu-id="167d7-110">Verifies the friend assembly rule (only name and public key).</span></span> <span data-ttu-id="167d7-111">このメンバーは内部でのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="167d7-111">This member is for internal use only.</span></span>|  
|`CANOF_PARSE_FRIEND_DISPLAY_NAME`|<span data-ttu-id="167d7-112">フラグ`CANOF_PARSE_DISPLAY_NAME` と`CANOF_VERIFY_FRIEND_ASSEMBLYNAME`フラグの組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="167d7-112">A combination of the `CANOF_PARSE_DISPLAY_NAME` and `CANOF_VERIFY_FRIEND_ASSEMBLYNAME` flags.</span></span> <span data-ttu-id="167d7-113">このメンバーは内部でのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="167d7-113">This member is for internal use only.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="167d7-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="167d7-114">Requirements</span></span>  
 <span data-ttu-id="167d7-115">**・** [システム要件](../../get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="167d7-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="167d7-116">**ヘッダー:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="167d7-116">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="167d7-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="167d7-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="167d7-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="167d7-118">See also</span></span>

- [<span data-ttu-id="167d7-119">IAssemblyName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="167d7-119">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="167d7-120">CreateAssemblyNameObject 関数</span><span class="sxs-lookup"><span data-stu-id="167d7-120">CreateAssemblyNameObject Function</span></span>](createassemblynameobject-function.md)
- [<span data-ttu-id="167d7-121">Fusion 列挙型</span><span class="sxs-lookup"><span data-stu-id="167d7-121">Fusion Enumerations</span></span>](fusion-enumerations.md)
