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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2093466c78b039a06a01e2d850b88ff4543d0ab3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67752463"
---
# <a name="variablelocationtype-enumeration"></a><span data-ttu-id="85fb0-102">VariableLocationType 列挙型</span><span class="sxs-lookup"><span data-stu-id="85fb0-102">VariableLocationType Enumeration</span></span>
<span data-ttu-id="85fb0-103">変数のネイティブの場所の種類を示します。</span><span class="sxs-lookup"><span data-stu-id="85fb0-103">Indicates the native location type of a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85fb0-104">構文</span><span class="sxs-lookup"><span data-stu-id="85fb0-104">Syntax</span></span>  
  
```cpp  
typedef enum VariableLocationType  
{  
    VLT_REGISTER,               
    VLT_REGISTER_RELATIVE,      
    VLT_INVALID  
} VariableLocationType;  
```  
  
## <a name="members"></a><span data-ttu-id="85fb0-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="85fb0-105">Members</span></span>  
  
|<span data-ttu-id="85fb0-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="85fb0-106">Member</span></span>|<span data-ttu-id="85fb0-107">説明</span><span class="sxs-lookup"><span data-stu-id="85fb0-107">Description</span></span>|  
|------------|-----------------|  
|`VLT_REGISTER`|<span data-ttu-id="85fb0-108">変数はレジスタでは。</span><span class="sxs-lookup"><span data-stu-id="85fb0-108">The variable is in a register.</span></span>|  
|`VLT_REGISTER_RELATIVE`|<span data-ttu-id="85fb0-109">変数は、レジスタの相対メモリの場所には。</span><span class="sxs-lookup"><span data-stu-id="85fb0-109">The variable is in a register-relative memory location.</span></span>|  
|`VLT_INVALID`|<span data-ttu-id="85fb0-110">変数はレジスタやレジスタの相対メモリの場所は保存されません。</span><span class="sxs-lookup"><span data-stu-id="85fb0-110">The variable is not stored in a register or a register-relative memory location.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="85fb0-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="85fb0-111">Remarks</span></span>  
 <span data-ttu-id="85fb0-112">メンバー、`VariableLocationType`列挙体は、によって返される、 [ICorDebugVariableHome::GetLocationType](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getlocationtype-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="85fb0-112">A member of the `VariableLocationType` enumeration is returned by the [ICorDebugVariableHome::GetLocationType](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getlocationtype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85fb0-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="85fb0-113">Requirements</span></span>  
 <span data-ttu-id="85fb0-114">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="85fb0-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85fb0-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="85fb0-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="85fb0-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="85fb0-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="85fb0-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="85fb0-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85fb0-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="85fb0-118">See also</span></span>

- [<span data-ttu-id="85fb0-119">列挙型のデバッグ</span><span class="sxs-lookup"><span data-stu-id="85fb0-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
