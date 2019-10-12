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
ms.openlocfilehash: 5d76fa4b2352da18b5ef0e547ebc4e2e99d980b8
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2019
ms.locfileid: "71273996"
---
# <a name="cor_typeid-structure"></a><span data-ttu-id="bda63-102">COR_TYPEID 構造体</span><span class="sxs-lookup"><span data-stu-id="bda63-102">COR_TYPEID Structure</span></span>
<span data-ttu-id="bda63-103">型識別子が含まれます。</span><span class="sxs-lookup"><span data-stu-id="bda63-103">Contains a type identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bda63-104">構文</span><span class="sxs-lookup"><span data-stu-id="bda63-104">Syntax</span></span>  
  
```cpp  
typedef struct COR_TYPEID{  
    UINT64 token1;  
    UINT64 token2;  
} COR_TYPEID;  
```  
  
## <a name="members"></a><span data-ttu-id="bda63-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="bda63-105">Members</span></span>  
  
|<span data-ttu-id="bda63-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="bda63-106">Member</span></span>|<span data-ttu-id="bda63-107">説明</span><span class="sxs-lookup"><span data-stu-id="bda63-107">Description</span></span>|  
|------------|-----------------|  
|`token1`|<span data-ttu-id="bda63-108">最初のトークン。</span><span class="sxs-lookup"><span data-stu-id="bda63-108">The first token.</span></span>|  
|`token2`|<span data-ttu-id="bda63-109">2番目のトークン。</span><span class="sxs-lookup"><span data-stu-id="bda63-109">The second token.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bda63-110">コメント</span><span class="sxs-lookup"><span data-stu-id="bda63-110">Remarks</span></span>  
 <span data-ttu-id="bda63-111">構造`COR_TYPEID`体は、ガベージコレクションされるオブジェクトに関する情報を提供する多数のデバッグメソッドによって返されます。</span><span class="sxs-lookup"><span data-stu-id="bda63-111">The `COR_TYPEID` structure is returned by a number of debugging methods that provide information about objects to be garbage-collected.</span></span> <span data-ttu-id="bda63-112">その後、その項目に関する追加情報を提供する他のデバッグメソッドに引数として渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="bda63-112">It can then be passed as an argument to other debugging methods that provide additional information about that item.</span></span> <span data-ttu-id="bda63-113">たとえば、COR_HEAPOBJECT [ICorDebugHeapEnum](icordebugheapenum-interface.md)オブジェクトを列挙することによって、マネージヒープ上の個々のオブジェクトを表す個々の[COR_HEAPOBJECT](cor-heapobject-structure.md)オブジェクトを取得できます。</span><span class="sxs-lookup"><span data-stu-id="bda63-113">For example, by enumerating an [ICorDebugHeapEnum](icordebugheapenum-interface.md) object, you can retrieve individual [COR_HEAPOBJECT](cor-heapobject-structure.md) objects that represent individual objects on the managed heap.</span></span> <span data-ttu-id="bda63-114">次に、 `COR_HEAPOBJECT.type`フィールドの`COR_TYPEID`値を[ICorDebugProcess5:: gettypefortypeid](icordebugprocess5-gettypefortypeid-method.md)メソッドに渡して、オブジェクトに関する型情報を提供する、テキストオブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="bda63-114">You can then pass the `COR_TYPEID` value from the `COR_HEAPOBJECT.type` field to the [ICorDebugProcess5::GetTypeForTypeID](icordebugprocess5-gettypefortypeid-method.md) method to retrieve an ICorDebugType object that provides type information about the object.</span></span>  
  
 <span data-ttu-id="bda63-115">`COR_TYPEID`オブジェクトは不透明であることが想定されています。</span><span class="sxs-lookup"><span data-stu-id="bda63-115">A `COR_TYPEID` object is intended to be opaque.</span></span> <span data-ttu-id="bda63-116">個々のフィールドにアクセスしたり操作したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="bda63-116">Its individual fields should not be accessed or manipulated.</span></span> <span data-ttu-id="bda63-117">唯一の用途は、メソッドの呼び出しで`out`パラメーターとして指定された識別子として使用され、さらに情報を提供するために他のメソッドに渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="bda63-117">Its sole use is as an identifier that is provided as an `out` parameter in a method call and that can, in turn, be passed to other methods to provide additional information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bda63-118">要件</span><span class="sxs-lookup"><span data-stu-id="bda63-118">Requirements</span></span>  
 <span data-ttu-id="bda63-119">**・** [システム要件](../../get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bda63-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bda63-120">**ヘッダー:** CorDebug .idl、CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="bda63-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bda63-121">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="bda63-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bda63-122">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bda63-122">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bda63-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="bda63-123">See also</span></span>

- [<span data-ttu-id="bda63-124">デバッグ構造体</span><span class="sxs-lookup"><span data-stu-id="bda63-124">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="bda63-125">デバッグ</span><span class="sxs-lookup"><span data-stu-id="bda63-125">Debugging</span></span>](index.md)
