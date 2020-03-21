---
title: VariableLocationType 列挙型
ms.date: 03/30/2017
api_name:
- VariableLocationType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- VariableLocationType
helpviewer_keywords:
- VariableLocationType enumeration [.NET Framework debugging]
ms.assetid: 8635ee3a-c84b-4626-876c-416bee54f787
topic_type:
- apiref
ms.openlocfilehash: e2fa5d5a998f51e0e90cfde22b40ec12f278307b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178357"
---
# <a name="variablelocationtype-enumeration"></a><span data-ttu-id="77191-102">VariableLocationType 列挙型</span><span class="sxs-lookup"><span data-stu-id="77191-102">VariableLocationType Enumeration</span></span>
<span data-ttu-id="77191-103">変数のネイティブな場所の型を示します。</span><span class="sxs-lookup"><span data-stu-id="77191-103">Indicates the native location type of a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77191-104">構文</span><span class="sxs-lookup"><span data-stu-id="77191-104">Syntax</span></span>  
  
```cpp  
typedef enum VariableLocationType  
{  
    VLT_REGISTER,
    VLT_REGISTER_RELATIVE,
    VLT_INVALID  
} VariableLocationType;  
```  
  
## <a name="members"></a><span data-ttu-id="77191-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="77191-105">Members</span></span>  
  
|<span data-ttu-id="77191-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="77191-106">Member</span></span>|<span data-ttu-id="77191-107">説明</span><span class="sxs-lookup"><span data-stu-id="77191-107">Description</span></span>|  
|------------|-----------------|  
|`VLT_REGISTER`|<span data-ttu-id="77191-108">変数はレジスタにあります。</span><span class="sxs-lookup"><span data-stu-id="77191-108">The variable is in a register.</span></span>|  
|`VLT_REGISTER_RELATIVE`|<span data-ttu-id="77191-109">変数はレジスタ相対メモリ位置にあります。</span><span class="sxs-lookup"><span data-stu-id="77191-109">The variable is in a register-relative memory location.</span></span>|  
|`VLT_INVALID`|<span data-ttu-id="77191-110">変数はレジスタまたはレジスタ相対メモリの場所に格納されません。</span><span class="sxs-lookup"><span data-stu-id="77191-110">The variable is not stored in a register or a register-relative memory location.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="77191-111">解説</span><span class="sxs-lookup"><span data-stu-id="77191-111">Remarks</span></span>  
 <span data-ttu-id="77191-112">列挙体の`VariableLocationType`メンバーは、メソッドによって返[されます](icordebugvariablehome-getlocationtype-method.md)。</span><span class="sxs-lookup"><span data-stu-id="77191-112">A member of the `VariableLocationType` enumeration is returned by the [ICorDebugVariableHome::GetLocationType](icordebugvariablehome-getlocationtype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="77191-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="77191-113">Requirements</span></span>  
 <span data-ttu-id="77191-114">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77191-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77191-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="77191-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="77191-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="77191-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="77191-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77191-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77191-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="77191-118">See also</span></span>

- [<span data-ttu-id="77191-119">列挙体のデバッグ</span><span class="sxs-lookup"><span data-stu-id="77191-119">Debugging Enumerations</span></span>](debugging-enumerations.md)
