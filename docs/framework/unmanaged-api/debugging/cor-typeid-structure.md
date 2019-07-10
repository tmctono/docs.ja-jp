---
title: COR_TYPEID 構造体
ms.date: 03/30/2017
api_name:
- COR_TYPEID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_TYPEID
helpviewer_keywords:
- COR_TYPEID structure [.NET Framework debugging]
ms.assetid: 1e172b14-ee22-4943-b3b8-3740e7bdcd2e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 426420175a7d05f39859b9e217a888a8c01b6d63
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67740502"
---
# <a name="cortypeid-structure"></a><span data-ttu-id="29bd4-102">COR_TYPEID 構造体</span><span class="sxs-lookup"><span data-stu-id="29bd4-102">COR_TYPEID Structure</span></span>
<span data-ttu-id="29bd4-103">型識別子が含まれます。</span><span class="sxs-lookup"><span data-stu-id="29bd4-103">Contains a type identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29bd4-104">構文</span><span class="sxs-lookup"><span data-stu-id="29bd4-104">Syntax</span></span>  
  
```cpp  
typedef struct COR_TYPEID{  
    UINT64 token1;  
    UINT64 token2;  
} COR_TYPEID;  
```  
  
## <a name="members"></a><span data-ttu-id="29bd4-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="29bd4-105">Members</span></span>  
  
|<span data-ttu-id="29bd4-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="29bd4-106">Member</span></span>|<span data-ttu-id="29bd4-107">説明</span><span class="sxs-lookup"><span data-stu-id="29bd4-107">Description</span></span>|  
|------------|-----------------|  
|`token1`|<span data-ttu-id="29bd4-108">最初のトークンです。</span><span class="sxs-lookup"><span data-stu-id="29bd4-108">The first token.</span></span>|  
|`token2`|<span data-ttu-id="29bd4-109">2 つ目のトークンです。</span><span class="sxs-lookup"><span data-stu-id="29bd4-109">The second token.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="29bd4-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="29bd4-110">Remarks</span></span>  
 <span data-ttu-id="29bd4-111">`COR_TYPEID`数ガベージ コレクトされるオブジェクトに関する情報を提供するデバッグの方法で構造体が返されます。</span><span class="sxs-lookup"><span data-stu-id="29bd4-111">The `COR_TYPEID` structure is returned by a number of debugging methods that provide information about objects to be garbage-collected.</span></span> <span data-ttu-id="29bd4-112">その項目に関する追加情報を提供するその他のデバッグ方法の引数として渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="29bd4-112">It can then be passed as an argument to other debugging methods that provide additional information about that item.</span></span> <span data-ttu-id="29bd4-113">たとえば、列挙することによって、 [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md)オブジェクト、個々 が取得することができます[COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md)マネージ ヒープ上の個々 のオブジェクトを表すオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="29bd4-113">For example, by enumerating an [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) object, you can retrieve individual [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) objects that represent individual objects on the managed heap.</span></span> <span data-ttu-id="29bd4-114">渡すことができますし、`COR_TYPEID`値から、`COR_HEAPOBJECT.type`フィールドを[icordebugprocess 5::gettypefortypeid](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefortypeid-method.md)オブジェクトに関する型情報を提供する ICorDebugType オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="29bd4-114">You can then pass the `COR_TYPEID` value from the `COR_HEAPOBJECT.type` field to the [ICorDebugProcess5::GetTypeForTypeID](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefortypeid-method.md) method to retrieve an ICorDebugType object that provides type information about the object.</span></span>  
  
 <span data-ttu-id="29bd4-115">A`COR_TYPEID`オブジェクトが不透明にする対象としています。</span><span class="sxs-lookup"><span data-stu-id="29bd4-115">A `COR_TYPEID` object is intended to be opaque.</span></span> <span data-ttu-id="29bd4-116">個別のフィールドをアクセスまたは操作する必要があります。</span><span class="sxs-lookup"><span data-stu-id="29bd4-116">Its individual fields should not be accessed or manipulated.</span></span> <span data-ttu-id="29bd4-117">として指定された識別子として唯一使用することは、`out`メソッドの呼び出しと、ことができるパラメーターは、追加情報を提供するその他のメソッドに渡される、します。</span><span class="sxs-lookup"><span data-stu-id="29bd4-117">Its sole use is as an identifier that is provided as an `out` parameter in a method call and that can, in turn, be passed to other methods to provide additional information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="29bd4-118">必要条件</span><span class="sxs-lookup"><span data-stu-id="29bd4-118">Requirements</span></span>  
 <span data-ttu-id="29bd4-119">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="29bd4-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="29bd4-120">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="29bd4-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="29bd4-121">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="29bd4-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="29bd4-122">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="29bd4-122">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29bd4-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="29bd4-123">See also</span></span>

- [<span data-ttu-id="29bd4-124">デバッグ構造体</span><span class="sxs-lookup"><span data-stu-id="29bd4-124">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="29bd4-125">デバッグ</span><span class="sxs-lookup"><span data-stu-id="29bd4-125">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
