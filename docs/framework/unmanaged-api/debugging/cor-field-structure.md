---
title: COR_FIELD 構造体
ms.date: 03/30/2017
api_name:
- COR_FIELD
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_FIELD
helpviewer_keywords:
- COR_FIELD structure [.NET Framework debugging]
ms.assetid: c0822423-a9df-4961-950d-50dcc152f863
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2efe159eaa8b49d4d3825e9737593d0a12fc4d4c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67740738"
---
# <a name="corfield-structure"></a><span data-ttu-id="4a24f-102">COR_FIELD 構造体</span><span class="sxs-lookup"><span data-stu-id="4a24f-102">COR_FIELD Structure</span></span>
<span data-ttu-id="4a24f-103">オブジェクトのフィールドに関する情報が提供されます。</span><span class="sxs-lookup"><span data-stu-id="4a24f-103">Provides information about a field in an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a24f-104">構文</span><span class="sxs-lookup"><span data-stu-id="4a24f-104">Syntax</span></span>  
  
```cpp  
typedef struct COR_FIELD{  
    mdFieldDef token;  
    ULONG32 offset;  
    COR_TYPEID id;  
    CorElementType fieldType;  
} COR_FIELD;  
```  
  
## <a name="members"></a><span data-ttu-id="4a24f-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="4a24f-105">Members</span></span>  
  
|<span data-ttu-id="4a24f-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="4a24f-106">Member</span></span>|<span data-ttu-id="4a24f-107">説明</span><span class="sxs-lookup"><span data-stu-id="4a24f-107">Description</span></span>|  
|------------|-----------------|  
|`token`|<span data-ttu-id="4a24f-108">`mdFieldDef`フィールド情報を取得するために使用できるトークン。</span><span class="sxs-lookup"><span data-stu-id="4a24f-108">An `mdFieldDef` token that can be used to get field information.</span></span>|  
|`offset`|<span data-ttu-id="4a24f-109">オブジェクトのフィールドのデータへのバイト オフセット。</span><span class="sxs-lookup"><span data-stu-id="4a24f-109">The offset, in bytes, to the field data in the object.</span></span>|  
|`id`|<span data-ttu-id="4a24f-110">A [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md)をこのフィールドの型を識別する値。</span><span class="sxs-lookup"><span data-stu-id="4a24f-110">A [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) value that identifies the type of this field.</span></span>|  
|`fieldType`|<span data-ttu-id="4a24f-111">フィールドの種類を示す CorElementType 列挙値。</span><span class="sxs-lookup"><span data-stu-id="4a24f-111">A CorElementType enumeration value that indicates the type of the field.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4a24f-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="4a24f-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a24f-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="4a24f-113">Requirements</span></span>  
 <span data-ttu-id="4a24f-114">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a24f-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a24f-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4a24f-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4a24f-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4a24f-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4a24f-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a24f-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a24f-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="4a24f-118">See also</span></span>

- [<span data-ttu-id="4a24f-119">デバッグ構造体</span><span class="sxs-lookup"><span data-stu-id="4a24f-119">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="4a24f-120">デバッグ</span><span class="sxs-lookup"><span data-stu-id="4a24f-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
