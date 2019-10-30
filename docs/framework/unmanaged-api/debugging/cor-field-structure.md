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
ms.openlocfilehash: 78e34d9d33d34047e3ebd2effb4894bc7b709585
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132358"
---
# <a name="cor_field-structure"></a><span data-ttu-id="5015f-102">COR_FIELD 構造体</span><span class="sxs-lookup"><span data-stu-id="5015f-102">COR_FIELD Structure</span></span>
<span data-ttu-id="5015f-103">オブジェクトのフィールドに関する情報が提供されます。</span><span class="sxs-lookup"><span data-stu-id="5015f-103">Provides information about a field in an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5015f-104">構文</span><span class="sxs-lookup"><span data-stu-id="5015f-104">Syntax</span></span>  
  
```cpp  
typedef struct COR_FIELD{  
    mdFieldDef token;  
    ULONG32 offset;  
    COR_TYPEID id;  
    CorElementType fieldType;  
} COR_FIELD;  
```  
  
## <a name="members"></a><span data-ttu-id="5015f-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="5015f-105">Members</span></span>  
  
|<span data-ttu-id="5015f-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="5015f-106">Member</span></span>|<span data-ttu-id="5015f-107">説明</span><span class="sxs-lookup"><span data-stu-id="5015f-107">Description</span></span>|  
|------------|-----------------|  
|`token`|<span data-ttu-id="5015f-108">フィールド情報を取得するために使用できる `mdFieldDef` トークン。</span><span class="sxs-lookup"><span data-stu-id="5015f-108">An `mdFieldDef` token that can be used to get field information.</span></span>|  
|`offset`|<span data-ttu-id="5015f-109">オブジェクト内のフィールドデータへのオフセット (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="5015f-109">The offset, in bytes, to the field data in the object.</span></span>|  
|`id`|<span data-ttu-id="5015f-110">このフィールドの型を識別する[COR_TYPEID](cor-typeid-structure.md)値。</span><span class="sxs-lookup"><span data-stu-id="5015f-110">A [COR_TYPEID](cor-typeid-structure.md) value that identifies the type of this field.</span></span>|  
|`fieldType`|<span data-ttu-id="5015f-111">フィールドの型を示す CorElementType 列挙値。</span><span class="sxs-lookup"><span data-stu-id="5015f-111">A CorElementType enumeration value that indicates the type of the field.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5015f-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="5015f-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5015f-113">［要件］</span><span class="sxs-lookup"><span data-stu-id="5015f-113">Requirements</span></span>  
 <span data-ttu-id="5015f-114">**:** 「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5015f-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5015f-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5015f-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5015f-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5015f-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5015f-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5015f-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5015f-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="5015f-118">See also</span></span>

- [<span data-ttu-id="5015f-119">デバッグ構造体</span><span class="sxs-lookup"><span data-stu-id="5015f-119">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="5015f-120">デバッグ</span><span class="sxs-lookup"><span data-stu-id="5015f-120">Debugging</span></span>](index.md)
