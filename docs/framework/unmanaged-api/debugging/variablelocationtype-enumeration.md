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
ms.openlocfilehash: 392254efcd099aca60e58b3cc0bc61ca85aa2c66
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59099951"
---
# <a name="variablelocationtype-enumeration"></a><span data-ttu-id="bdfad-102">VariableLocationType 列挙型</span><span class="sxs-lookup"><span data-stu-id="bdfad-102">VariableLocationType Enumeration</span></span>
<span data-ttu-id="bdfad-103">変数のネイティブの場所の種類を示します。</span><span class="sxs-lookup"><span data-stu-id="bdfad-103">Indicates the native location type of a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bdfad-104">構文</span><span class="sxs-lookup"><span data-stu-id="bdfad-104">Syntax</span></span>  
  
```  
typedef enum VariableLocationType  
{  
    VLT_REGISTER,               
    VLT_REGISTER_RELATIVE,      
    VLT_INVALID  
} VariableLocationType;  
```  
  
## <a name="members"></a><span data-ttu-id="bdfad-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="bdfad-105">Members</span></span>  
  
|<span data-ttu-id="bdfad-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="bdfad-106">Member</span></span>|<span data-ttu-id="bdfad-107">説明</span><span class="sxs-lookup"><span data-stu-id="bdfad-107">Description</span></span>|  
|------------|-----------------|  
|`VLT_REGISTER`|<span data-ttu-id="bdfad-108">変数はレジスタでは。</span><span class="sxs-lookup"><span data-stu-id="bdfad-108">The variable is in a register.</span></span>|  
|`VLT_REGISTER_RELATIVE`|<span data-ttu-id="bdfad-109">変数は、レジスタの相対メモリの場所には。</span><span class="sxs-lookup"><span data-stu-id="bdfad-109">The variable is in a register-relative memory location.</span></span>|  
|`VLT_INVALID`|<span data-ttu-id="bdfad-110">変数はレジスタやレジスタの相対メモリの場所は保存されません。</span><span class="sxs-lookup"><span data-stu-id="bdfad-110">The variable is not stored in a register or a register-relative memory location.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bdfad-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="bdfad-111">Remarks</span></span>  
 <span data-ttu-id="bdfad-112">メンバー、`VariableLocationType`列挙体は、によって返される、 [ICorDebugVariableHome::GetLocationType](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getlocationtype-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="bdfad-112">A member of the `VariableLocationType` enumeration is returned by the [ICorDebugVariableHome::GetLocationType](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getlocationtype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bdfad-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="bdfad-113">Requirements</span></span>  
 <span data-ttu-id="bdfad-114">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bdfad-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bdfad-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bdfad-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bdfad-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bdfad-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="bdfad-117">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="bdfad-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="bdfad-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="bdfad-118">See also</span></span>

- [<span data-ttu-id="bdfad-119">列挙体のデバッグ</span><span class="sxs-lookup"><span data-stu-id="bdfad-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
