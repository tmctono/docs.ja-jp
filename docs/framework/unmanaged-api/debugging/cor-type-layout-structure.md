---
title: COR_TYPE_LAYOUT 構造体
ms.date: 03/30/2017
api_name:
- COR_TYPE_LAYOUT
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_TYPE_LAYOUT
helpviewer_keywords:
- COR_TYPE_LAYOUT structure [.NET Framework debugging]
ms.assetid: 43a7addd-f25a-4049-9907-abec3eb17af2
topic_type:
- apiref
ms.openlocfilehash: 12c594f157c803d5fc179e09a8ca6c0ef40f3f44
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73099020"
---
# <a name="cor_type_layout-structure"></a><span data-ttu-id="6bcef-102">COR_TYPE_LAYOUT 構造体</span><span class="sxs-lookup"><span data-stu-id="6bcef-102">COR_TYPE_LAYOUT Structure</span></span>
<span data-ttu-id="6bcef-103">メモリ内のオブジェクトのレイアウトに関する情報が提供されます。</span><span class="sxs-lookup"><span data-stu-id="6bcef-103">Provides information about the layout of an object in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6bcef-104">構文</span><span class="sxs-lookup"><span data-stu-id="6bcef-104">Syntax</span></span>  
  
```cpp  
typedef struct COR_TYPE_LAYOUT {  
    COR_TYPEID parentID;  
    ULONG32 objectSize;  
    ULONG32 numFields;  
    ULONG32 boxOffset;  
    CorElementType type;  
} COR_TYPE_LAYOUT;  
```  
  
## <a name="members"></a><span data-ttu-id="6bcef-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="6bcef-105">Members</span></span>  
  
|<span data-ttu-id="6bcef-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="6bcef-106">Member</span></span>|<span data-ttu-id="6bcef-107">説明</span><span class="sxs-lookup"><span data-stu-id="6bcef-107">Description</span></span>|  
|------------|-----------------|  
|`parentID`|<span data-ttu-id="6bcef-108">この型への親の型の識別子。</span><span class="sxs-lookup"><span data-stu-id="6bcef-108">The identifier of the parent type to this type.</span></span> <span data-ttu-id="6bcef-109">型 id が <xref:System.Object?displayProperty=nameWithType>に対応する場合、これは NULL 型 id (token1 = 0, token2 = 0) になります。</span><span class="sxs-lookup"><span data-stu-id="6bcef-109">This will be the NULL type id (token1= 0, token2 = 0) if the type id corresponds to <xref:System.Object?displayProperty=nameWithType>.</span></span>|  
|`objectSize`|<span data-ttu-id="6bcef-110">この型のオブジェクトの基本サイズ。</span><span class="sxs-lookup"><span data-stu-id="6bcef-110">The base size of an object of this type.</span></span> <span data-ttu-id="6bcef-111">これは、変数サイズが設定されていないオブジェクトの合計サイズです。</span><span class="sxs-lookup"><span data-stu-id="6bcef-111">This is the total size for non-variable sized objects.</span></span>|  
|`numFields`|<span data-ttu-id="6bcef-112">この型のオブジェクトに含まれるフィールドの数。</span><span class="sxs-lookup"><span data-stu-id="6bcef-112">The number of fields included in objects of this type.</span></span>|  
|`boxOffset`|<span data-ttu-id="6bcef-113">この型がボックス化されている場合は、オブジェクトのフィールドの開始オフセット。</span><span class="sxs-lookup"><span data-stu-id="6bcef-113">If this type is boxed, the beginning offset of an object's fields.</span></span> <span data-ttu-id="6bcef-114">このフィールドは、プリミティブや構造体などの値型に対してのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="6bcef-114">This field is valid only for value types such as primitives and structures.</span></span>|  
|`type`|<span data-ttu-id="6bcef-115">この型が属する CorElementType。</span><span class="sxs-lookup"><span data-stu-id="6bcef-115">The CorElementType to which this type belongs.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6bcef-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="6bcef-116">Remarks</span></span>  
 <span data-ttu-id="6bcef-117">`numFields` が0より大きい場合は、 [ICorDebugProcess5:: GetTypeFields](icordebugprocess5-gettypefields-method.md)メソッドを呼び出して、この型のフィールドに関する情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="6bcef-117">If `numFields` is greater than zero, you can call the [ICorDebugProcess5::GetTypeFields](icordebugprocess5-gettypefields-method.md) method to obtain information about the fields in this type.</span></span> <span data-ttu-id="6bcef-118">`type` が `ELEMENT_TYPE_STRING`、`ELEMENT_TYPE_ARRAY`、または `ELEMENT_TYPE_SZARRAY`の場合、この型のオブジェクトのサイズは可変になり、 [COR_TYPEID](cor-typeid-structure.md)構造体を[ICorDebugProcess5:: getarraylayout](icordebugprocess5-getarraylayout-method.md)メソッドに渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="6bcef-118">If `type` is `ELEMENT_TYPE_STRING`, `ELEMENT_TYPE_ARRAY`, or `ELEMENT_TYPE_SZARRAY`, the size of objects of this type is variable, and you can pass the [COR_TYPEID](cor-typeid-structure.md) structure to the [ICorDebugProcess5::GetArrayLayout](icordebugprocess5-getarraylayout-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6bcef-119">［要件］</span><span class="sxs-lookup"><span data-stu-id="6bcef-119">Requirements</span></span>  
 <span data-ttu-id="6bcef-120">**:** 「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6bcef-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6bcef-121">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6bcef-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6bcef-122">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6bcef-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6bcef-123">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6bcef-123">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bcef-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="6bcef-124">See also</span></span>

- [<span data-ttu-id="6bcef-125">デバッグ構造体</span><span class="sxs-lookup"><span data-stu-id="6bcef-125">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="6bcef-126">デバッグ</span><span class="sxs-lookup"><span data-stu-id="6bcef-126">Debugging</span></span>](index.md)
