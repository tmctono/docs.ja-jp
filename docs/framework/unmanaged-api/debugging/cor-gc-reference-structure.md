---
title: COR_GC_REFERENCE 構造体
ms.date: 03/30/2017
api_name:
- COR_GC_REFERENCE
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_GC_REFERENCE
helpviewer_keywords:
- COR_GC_REFERENCE structure [.NET Framework debugging]
ms.assetid: 162e8179-0cd4-4110-8f06-5f387698bd62
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 61a9cad9d0ce807d62c811e77402b8cc6d8c6905
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67740695"
---
# <a name="corgcreference-structure"></a><span data-ttu-id="f0c2f-102">COR_GC_REFERENCE 構造体</span><span class="sxs-lookup"><span data-stu-id="f0c2f-102">COR_GC_REFERENCE Structure</span></span>
<span data-ttu-id="f0c2f-103">ガベージ コレクトされるオブジェクトに関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f0c2f-103">Contains information about an object that is to be garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0c2f-104">構文</span><span class="sxs-lookup"><span data-stu-id="f0c2f-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_GC_REFERENCE {  
    ICorDebugAppDomain *domain;   
    ICorDebugValue *location;  
    CorGCReferenceType type;  
    UINT64 extraData;  
} COR_GC_REFERENCE;  
```  
  
## <a name="members"></a><span data-ttu-id="f0c2f-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="f0c2f-105">Members</span></span>  
  
|<span data-ttu-id="f0c2f-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="f0c2f-106">Member</span></span>|<span data-ttu-id="f0c2f-107">説明</span><span class="sxs-lookup"><span data-stu-id="f0c2f-107">Description</span></span>|  
|------------|-----------------|  
|`domain`|<span data-ttu-id="f0c2f-108">ハンドルまたはオブジェクトが所属するアプリケーション ドメインへのポインター。</span><span class="sxs-lookup"><span data-stu-id="f0c2f-108">A pointer to the application domain to which the handle or object belongs.</span></span> <span data-ttu-id="f0c2f-109">その値があります`null`します。</span><span class="sxs-lookup"><span data-stu-id="f0c2f-109">Its value may be `null`.</span></span>|  
|`location`|<span data-ttu-id="f0c2f-110">ICorDebugValue またはガベージ コレクトされるオブジェクトに対応する ICorDebugReferenceValue インターフェイスのいずれか。</span><span class="sxs-lookup"><span data-stu-id="f0c2f-110">Either an ICorDebugValue or an ICorDebugReferenceValue interface that corresponds to the object to be garbage-collected.</span></span>|  
|`type`|<span data-ttu-id="f0c2f-111">A [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md)ルートの出所を示す列挙値。</span><span class="sxs-lookup"><span data-stu-id="f0c2f-111">A [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) enumeration value that indicates where the root came from.</span></span> <span data-ttu-id="f0c2f-112">詳細については、「解説」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0c2f-112">For more information, see the Remarks section.</span></span>|  
|`extraData`|<span data-ttu-id="f0c2f-113">ガベージ コレクトされるオブジェクトに関する追加データ。</span><span class="sxs-lookup"><span data-stu-id="f0c2f-113">Additional data about the object to be garbage-collected.</span></span> <span data-ttu-id="f0c2f-114">この情報は、によって示される、オブジェクトのソースとは異なります。、`type`フィールド。</span><span class="sxs-lookup"><span data-stu-id="f0c2f-114">This information depends on the source of the object, as indicated by the `type` field.</span></span> <span data-ttu-id="f0c2f-115">詳細については、「解説」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0c2f-115">For more information, see the Remarks section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f0c2f-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="f0c2f-116">Remarks</span></span>  
 <span data-ttu-id="f0c2f-117">`type`フィールドは、 [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md)参照の出所を示す列挙値。</span><span class="sxs-lookup"><span data-stu-id="f0c2f-117">The `type` field is a [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) enumeration value that indicates where the reference came from.</span></span> <span data-ttu-id="f0c2f-118">特定の`COR_GC_REFERENCE`値は次のようなマネージ オブジェクトのいずれかを反映できます。</span><span class="sxs-lookup"><span data-stu-id="f0c2f-118">A particular `COR_GC_REFERENCE` value can reflect any of the following kinds of managed objects:</span></span>  
  
- <span data-ttu-id="f0c2f-119">すべてのマネージ スタックからオブジェクト (`CorGCReferenceType.CorReferenceStack`)。</span><span class="sxs-lookup"><span data-stu-id="f0c2f-119">Objects from all managed stacks (`CorGCReferenceType.CorReferenceStack`).</span></span> <span data-ttu-id="f0c2f-120">これには、共通言語ランタイムによって作成されたオブジェクトと同様に、マネージ コードでのライブ参照が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f0c2f-120">This includes live references in managed code, as well as objects created by the common language runtime.</span></span>  
  
- <span data-ttu-id="f0c2f-121">オブジェクト ハンドル テーブルから (`CorGCReferenceType.CorHandle*`)。</span><span class="sxs-lookup"><span data-stu-id="f0c2f-121">Objects from the handle table (`CorGCReferenceType.CorHandle*`).</span></span> <span data-ttu-id="f0c2f-122">強い参照が含まれます (`HNDTYPE_STRONG`と`HNDTYPE_REFCOUNT`) とモジュールの静的変数。</span><span class="sxs-lookup"><span data-stu-id="f0c2f-122">This includes strong references (`HNDTYPE_STRONG` and `HNDTYPE_REFCOUNT`) and static variables in a module.</span></span>  
  
- <span data-ttu-id="f0c2f-123">ファイナライザー キューからオブジェクト (`CorGCReferenceType.CorReferenceFinalizer`)。</span><span class="sxs-lookup"><span data-stu-id="f0c2f-123">Objects from the finalizer queue (`CorGCReferenceType.CorReferenceFinalizer`).</span></span> <span data-ttu-id="f0c2f-124">ファイナライザー キューでは、ファイナライザーが実行されるまでオブジェクトがルートします。</span><span class="sxs-lookup"><span data-stu-id="f0c2f-124">The finalizer queue roots objects until the finalizer has run.</span></span>  
  
 <span data-ttu-id="f0c2f-125">`extraData`フィールドには参照のソース (または型) によって追加のデータが含まれています。</span><span class="sxs-lookup"><span data-stu-id="f0c2f-125">The `extraData` field contains extra data depending on the source (or type) of the reference.</span></span> <span data-ttu-id="f0c2f-126">指定できる値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f0c2f-126">Possible values are:</span></span>  
  
- <span data-ttu-id="f0c2f-127">`DependentSource`。</span><span class="sxs-lookup"><span data-stu-id="f0c2f-127">`DependentSource`.</span></span> <span data-ttu-id="f0c2f-128">場合、`type`は`CorGCREferenceType.CorHandleStrongDependent`、このフィールドはオブジェクトでガベージ コレクトされるオブジェクトの場合は、ルートを`COR_GC_REFERENCE.Location`します。</span><span class="sxs-lookup"><span data-stu-id="f0c2f-128">If the `type` is `CorGCREferenceType.CorHandleStrongDependent`, this field is the object that, if alive, roots the object to be garbage-collected at `COR_GC_REFERENCE.Location`.</span></span>  
  
- <span data-ttu-id="f0c2f-129">`RefCount`。</span><span class="sxs-lookup"><span data-stu-id="f0c2f-129">`RefCount`.</span></span> <span data-ttu-id="f0c2f-130">場合、`type`は`CorGCREferenceType.CorHandleStrongRefCount`、このフィールドは、ハンドルの参照カウントします。</span><span class="sxs-lookup"><span data-stu-id="f0c2f-130">If the `type` is `CorGCREferenceType.CorHandleStrongRefCount`, this field is the reference count of the handle.</span></span>  
  
- <span data-ttu-id="f0c2f-131">`Size`。</span><span class="sxs-lookup"><span data-stu-id="f0c2f-131">`Size`.</span></span> <span data-ttu-id="f0c2f-132">場合、`type`は`CorGCREferenceType.CorHandleStrongSizedByref`、このフィールドは、ガベージ コレクターがオブジェクトのルートを計算するオブジェクト ツリーの最後のサイズ。</span><span class="sxs-lookup"><span data-stu-id="f0c2f-132">If the `type` is `CorGCREferenceType.CorHandleStrongSizedByref`, this field is the last size of the object tree for which the garbage collector calculated the object roots.</span></span> <span data-ttu-id="f0c2f-133">この計算は必ずしも最新ではないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="f0c2f-133">Note that this calculation is not necessarily up to date.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0c2f-134">必要条件</span><span class="sxs-lookup"><span data-stu-id="f0c2f-134">Requirements</span></span>  
 <span data-ttu-id="f0c2f-135">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0c2f-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0c2f-136">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f0c2f-136">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f0c2f-137">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f0c2f-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f0c2f-138">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0c2f-138">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0c2f-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="f0c2f-139">See also</span></span>

- [<span data-ttu-id="f0c2f-140">デバッグ構造体</span><span class="sxs-lookup"><span data-stu-id="f0c2f-140">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="f0c2f-141">デバッグ</span><span class="sxs-lookup"><span data-stu-id="f0c2f-141">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
