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
ms.openlocfilehash: 861d5daa481132d3d6527e8d5fbccfab6436c5fe
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139115"
---
# <a name="variablelocationtype-enumeration"></a><span data-ttu-id="7cf18-102">VariableLocationType 列挙型</span><span class="sxs-lookup"><span data-stu-id="7cf18-102">VariableLocationType Enumeration</span></span>
<span data-ttu-id="7cf18-103">変数のネイティブな場所の種類を示します。</span><span class="sxs-lookup"><span data-stu-id="7cf18-103">Indicates the native location type of a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7cf18-104">構文</span><span class="sxs-lookup"><span data-stu-id="7cf18-104">Syntax</span></span>  
  
```cpp  
typedef enum VariableLocationType  
{  
    VLT_REGISTER,               
    VLT_REGISTER_RELATIVE,      
    VLT_INVALID  
} VariableLocationType;  
```  
  
## <a name="members"></a><span data-ttu-id="7cf18-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="7cf18-105">Members</span></span>  
  
|<span data-ttu-id="7cf18-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="7cf18-106">Member</span></span>|<span data-ttu-id="7cf18-107">説明</span><span class="sxs-lookup"><span data-stu-id="7cf18-107">Description</span></span>|  
|------------|-----------------|  
|`VLT_REGISTER`|<span data-ttu-id="7cf18-108">変数はレジスタにあります。</span><span class="sxs-lookup"><span data-stu-id="7cf18-108">The variable is in a register.</span></span>|  
|`VLT_REGISTER_RELATIVE`|<span data-ttu-id="7cf18-109">変数は、レジスタ相対メモリの場所にあります。</span><span class="sxs-lookup"><span data-stu-id="7cf18-109">The variable is in a register-relative memory location.</span></span>|  
|`VLT_INVALID`|<span data-ttu-id="7cf18-110">変数はレジスタまたはレジスタの相対メモリ位置に格納されません。</span><span class="sxs-lookup"><span data-stu-id="7cf18-110">The variable is not stored in a register or a register-relative memory location.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7cf18-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="7cf18-111">Remarks</span></span>  
 <span data-ttu-id="7cf18-112">`VariableLocationType` 列挙体のメンバーは、 [GetLocationType](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getlocationtype-method.md)メソッドによって返されます。</span><span class="sxs-lookup"><span data-stu-id="7cf18-112">A member of the `VariableLocationType` enumeration is returned by the [ICorDebugVariableHome::GetLocationType](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getlocationtype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7cf18-113">［要件］</span><span class="sxs-lookup"><span data-stu-id="7cf18-113">Requirements</span></span>  
 <span data-ttu-id="7cf18-114">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7cf18-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7cf18-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7cf18-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7cf18-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7cf18-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7cf18-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7cf18-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cf18-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="7cf18-118">See also</span></span>

- [<span data-ttu-id="7cf18-119">列挙型のデバッグ</span><span class="sxs-lookup"><span data-stu-id="7cf18-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
