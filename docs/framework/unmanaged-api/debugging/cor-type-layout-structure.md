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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1793547cfc0d9637352b62ff47beee41e9f5ac5c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67740504"
---
# <a name="cortypelayout-structure"></a><span data-ttu-id="85746-102">COR_TYPE_LAYOUT 構造体</span><span class="sxs-lookup"><span data-stu-id="85746-102">COR_TYPE_LAYOUT Structure</span></span>
<span data-ttu-id="85746-103">メモリ内のオブジェクトのレイアウトに関する情報が提供されます。</span><span class="sxs-lookup"><span data-stu-id="85746-103">Provides information about the layout of an object in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85746-104">構文</span><span class="sxs-lookup"><span data-stu-id="85746-104">Syntax</span></span>  
  
```cpp  
typedef struct COR_TYPE_LAYOUT {  
    COR_TYPEID parentID;  
    ULONG32 objectSize;  
    ULONG32 numFields;  
    ULONG32 boxOffset;  
    CorElementType type;  
} COR_TYPE_LAYOUT;  
```  
  
## <a name="members"></a><span data-ttu-id="85746-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="85746-105">Members</span></span>  
  
|<span data-ttu-id="85746-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="85746-106">Member</span></span>|<span data-ttu-id="85746-107">説明</span><span class="sxs-lookup"><span data-stu-id="85746-107">Description</span></span>|  
|------------|-----------------|  
|`parentID`|<span data-ttu-id="85746-108">この型に親の識別子を入力します。</span><span class="sxs-lookup"><span data-stu-id="85746-108">The identifier of the parent type to this type.</span></span> <span data-ttu-id="85746-109">NULL 型の id になります (token1 = 0、token2 = 0) に対応する型 id 場合<xref:System.Object?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="85746-109">This will be the NULL type id (token1= 0, token2 = 0) if the type id corresponds to <xref:System.Object?displayProperty=nameWithType>.</span></span>|  
|`objectSize`|<span data-ttu-id="85746-110">この型のオブジェクトの基本サイズ。</span><span class="sxs-lookup"><span data-stu-id="85746-110">The base size of an object of this type.</span></span> <span data-ttu-id="85746-111">これは、非可変サイズのオブジェクトの合計サイズです。</span><span class="sxs-lookup"><span data-stu-id="85746-111">This is the total size for non-variable sized objects.</span></span>|  
|`numFields`|<span data-ttu-id="85746-112">この型のオブジェクトに含まれるフィールドの数。</span><span class="sxs-lookup"><span data-stu-id="85746-112">The number of fields included in objects of this type.</span></span>|  
|`boxOffset`|<span data-ttu-id="85746-113">この型をボックス化すると、先頭は、オブジェクトのフィールドのオフセット。</span><span class="sxs-lookup"><span data-stu-id="85746-113">If this type is boxed, the beginning offset of an object's fields.</span></span> <span data-ttu-id="85746-114">このフィールドは、プリミティブと構造体などの値型に対してのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="85746-114">This field is valid only for value types such as primitives and structures.</span></span>|  
|`type`|<span data-ttu-id="85746-115">この型が所属する CorElementType します。</span><span class="sxs-lookup"><span data-stu-id="85746-115">The CorElementType to which this type belongs.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="85746-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="85746-116">Remarks</span></span>  
 <span data-ttu-id="85746-117">場合`numFields`はゼロより大きく、呼び出すことができます、 [icordebugprocess 5::gettypefields](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefields-method.md)メソッドをこの種類のフィールドについての情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="85746-117">If `numFields` is greater than zero, you can call the [ICorDebugProcess5::GetTypeFields](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefields-method.md) method to obtain information about the fields in this type.</span></span> <span data-ttu-id="85746-118">場合`type`は`ELEMENT_TYPE_STRING`、 `ELEMENT_TYPE_ARRAY`、または`ELEMENT_TYPE_SZARRAY`、この型のオブジェクトのサイズは、変数、および、渡すことができます、 [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md)構造体を[icordebugprocess 5::getarraylayout](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getarraylayout-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="85746-118">If `type` is `ELEMENT_TYPE_STRING`, `ELEMENT_TYPE_ARRAY`, or `ELEMENT_TYPE_SZARRAY`, the size of objects of this type is variable, and you can pass the [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) structure to the [ICorDebugProcess5::GetArrayLayout](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getarraylayout-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85746-119">必要条件</span><span class="sxs-lookup"><span data-stu-id="85746-119">Requirements</span></span>  
 <span data-ttu-id="85746-120">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="85746-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85746-121">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="85746-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="85746-122">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="85746-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="85746-123">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="85746-123">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85746-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="85746-124">See also</span></span>

- [<span data-ttu-id="85746-125">デバッグ構造体</span><span class="sxs-lookup"><span data-stu-id="85746-125">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="85746-126">デバッグ</span><span class="sxs-lookup"><span data-stu-id="85746-126">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
