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
ms.openlocfilehash: e22269b76c230f702f4712298fddcd0df1fde50d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179327"
---
# <a name="cor_gc_reference-structure"></a><span data-ttu-id="3acd4-102">COR_GC_REFERENCE 構造体</span><span class="sxs-lookup"><span data-stu-id="3acd4-102">COR_GC_REFERENCE Structure</span></span>
<span data-ttu-id="3acd4-103">ガベージ コレクトされるオブジェクトに関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="3acd4-103">Contains information about an object that is to be garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3acd4-104">構文</span><span class="sxs-lookup"><span data-stu-id="3acd4-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_GC_REFERENCE {  
    ICorDebugAppDomain *domain;
    ICorDebugValue *location;  
    CorGCReferenceType type;  
    UINT64 extraData;  
} COR_GC_REFERENCE;  
```  
  
## <a name="members"></a><span data-ttu-id="3acd4-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="3acd4-105">Members</span></span>  
  
|<span data-ttu-id="3acd4-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="3acd4-106">Member</span></span>|<span data-ttu-id="3acd4-107">説明</span><span class="sxs-lookup"><span data-stu-id="3acd4-107">Description</span></span>|  
|------------|-----------------|  
|`domain`|<span data-ttu-id="3acd4-108">ハンドルまたはオブジェクトが属するアプリケーション ドメインへのポインター。</span><span class="sxs-lookup"><span data-stu-id="3acd4-108">A pointer to the application domain to which the handle or object belongs.</span></span> <span data-ttu-id="3acd4-109">その値は. `null`</span><span class="sxs-lookup"><span data-stu-id="3acd4-109">Its value may be `null`.</span></span>|  
|`location`|<span data-ttu-id="3acd4-110">ガベージ コレクションされるオブジェクトに対応するインターフェイスまたは ICorDebugReferenceValue インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="3acd4-110">Either an ICorDebugValue or an ICorDebugReferenceValue interface that corresponds to the object to be garbage-collected.</span></span>|  
|`type`|<span data-ttu-id="3acd4-111">ルートの取得元を示す[CorGCReferenceType](corgcreferencetype-enumeration.md)列挙値。</span><span class="sxs-lookup"><span data-stu-id="3acd4-111">A [CorGCReferenceType](corgcreferencetype-enumeration.md) enumeration value that indicates where the root came from.</span></span> <span data-ttu-id="3acd4-112">詳細については、「解説」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3acd4-112">For more information, see the Remarks section.</span></span>|  
|`extraData`|<span data-ttu-id="3acd4-113">ガベージ コレクションされるオブジェクトに関する追加データ。</span><span class="sxs-lookup"><span data-stu-id="3acd4-113">Additional data about the object to be garbage-collected.</span></span> <span data-ttu-id="3acd4-114">この情報は、`type`フィールドで示されるオブジェクトのソースによって異なります。</span><span class="sxs-lookup"><span data-stu-id="3acd4-114">This information depends on the source of the object, as indicated by the `type` field.</span></span> <span data-ttu-id="3acd4-115">詳細については、「解説」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3acd4-115">For more information, see the Remarks section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3acd4-116">解説</span><span class="sxs-lookup"><span data-stu-id="3acd4-116">Remarks</span></span>  
 <span data-ttu-id="3acd4-117">フィールド`type`は、参照の取得元を示す[CorGCReferenceType](corgcreferencetype-enumeration.md)列挙値です。</span><span class="sxs-lookup"><span data-stu-id="3acd4-117">The `type` field is a [CorGCReferenceType](corgcreferencetype-enumeration.md) enumeration value that indicates where the reference came from.</span></span> <span data-ttu-id="3acd4-118">特定`COR_GC_REFERENCE`の値は、次の種類の管理オブジェクトを反映できます。</span><span class="sxs-lookup"><span data-stu-id="3acd4-118">A particular `COR_GC_REFERENCE` value can reflect any of the following kinds of managed objects:</span></span>  
  
- <span data-ttu-id="3acd4-119">すべてのマネージ スタック (`CorGCReferenceType.CorReferenceStack`) からのオブジェクト</span><span class="sxs-lookup"><span data-stu-id="3acd4-119">Objects from all managed stacks (`CorGCReferenceType.CorReferenceStack`).</span></span> <span data-ttu-id="3acd4-120">これには、マネージ コード内のライブ参照と、共通言語ランタイムによって作成されたオブジェクトが含まれます。</span><span class="sxs-lookup"><span data-stu-id="3acd4-120">This includes live references in managed code, as well as objects created by the common language runtime.</span></span>  
  
- <span data-ttu-id="3acd4-121">ハンドル テーブル (`CorGCReferenceType.CorHandle*`) のオブジェクト</span><span class="sxs-lookup"><span data-stu-id="3acd4-121">Objects from the handle table (`CorGCReferenceType.CorHandle*`).</span></span> <span data-ttu-id="3acd4-122">これには、モジュール内の`HNDTYPE_STRONG`厳密`HNDTYPE_REFCOUNT`な参照 ( および ) と静的変数が含まれます。</span><span class="sxs-lookup"><span data-stu-id="3acd4-122">This includes strong references (`HNDTYPE_STRONG` and `HNDTYPE_REFCOUNT`) and static variables in a module.</span></span>  
  
- <span data-ttu-id="3acd4-123">ファイナライザー キュー (`CorGCReferenceType.CorReferenceFinalizer`) からのオブジェクト</span><span class="sxs-lookup"><span data-stu-id="3acd4-123">Objects from the finalizer queue (`CorGCReferenceType.CorReferenceFinalizer`).</span></span> <span data-ttu-id="3acd4-124">ファイナライザーが実行されるまで、ファイナライザー キューのルート オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="3acd4-124">The finalizer queue roots objects until the finalizer has run.</span></span>  
  
 <span data-ttu-id="3acd4-125">フィールド`extraData`には、参照のソース (またはタイプ) に応じて、追加のデータが含まれます。</span><span class="sxs-lookup"><span data-stu-id="3acd4-125">The `extraData` field contains extra data depending on the source (or type) of the reference.</span></span> <span data-ttu-id="3acd4-126">次のいずれかの値になります。</span><span class="sxs-lookup"><span data-stu-id="3acd4-126">Possible values are:</span></span>  
  
- <span data-ttu-id="3acd4-127">`DependentSource`.</span><span class="sxs-lookup"><span data-stu-id="3acd4-127">`DependentSource`.</span></span> <span data-ttu-id="3acd4-128">の`type`場合、`CorGCREferenceType.CorHandleStrongDependent`このフィールドは、生きている場合は、ガベージ コレクションされるオブジェクトをルートとするオブジェクト`COR_GC_REFERENCE.Location`です。</span><span class="sxs-lookup"><span data-stu-id="3acd4-128">If the `type` is `CorGCREferenceType.CorHandleStrongDependent`, this field is the object that, if alive, roots the object to be garbage-collected at `COR_GC_REFERENCE.Location`.</span></span>  
  
- <span data-ttu-id="3acd4-129">`RefCount`.</span><span class="sxs-lookup"><span data-stu-id="3acd4-129">`RefCount`.</span></span> <span data-ttu-id="3acd4-130">の`type`場合、`CorGCREferenceType.CorHandleStrongRefCount`このフィールドはハンドルの参照カウントです。</span><span class="sxs-lookup"><span data-stu-id="3acd4-130">If the `type` is `CorGCREferenceType.CorHandleStrongRefCount`, this field is the reference count of the handle.</span></span>  
  
- <span data-ttu-id="3acd4-131">`Size`.</span><span class="sxs-lookup"><span data-stu-id="3acd4-131">`Size`.</span></span> <span data-ttu-id="3acd4-132">の`type`場合、`CorGCREferenceType.CorHandleStrongSizedByref`このフィールドは、ガベージ コレクターがオブジェクト ルートを計算したオブジェクト ツリーの最後のサイズです。</span><span class="sxs-lookup"><span data-stu-id="3acd4-132">If the `type` is `CorGCREferenceType.CorHandleStrongSizedByref`, this field is the last size of the object tree for which the garbage collector calculated the object roots.</span></span> <span data-ttu-id="3acd4-133">この計算は必ずしも最新の計算ではありません。</span><span class="sxs-lookup"><span data-stu-id="3acd4-133">Note that this calculation is not necessarily up to date.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3acd4-134">必要条件</span><span class="sxs-lookup"><span data-stu-id="3acd4-134">Requirements</span></span>  
 <span data-ttu-id="3acd4-135">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3acd4-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3acd4-136">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3acd4-136">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3acd4-137">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3acd4-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3acd4-138">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3acd4-138">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3acd4-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="3acd4-139">See also</span></span>

- [<span data-ttu-id="3acd4-140">デバッグ構造体</span><span class="sxs-lookup"><span data-stu-id="3acd4-140">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="3acd4-141">デバッグ</span><span class="sxs-lookup"><span data-stu-id="3acd4-141">Debugging</span></span>](index.md)
