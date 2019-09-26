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
ms.openlocfilehash: cc0b67621f77c0741e0b63b84ab1794530d6280b
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274222"
---
# <a name="cor_gc_reference-structure"></a><span data-ttu-id="78591-102">COR_GC_REFERENCE 構造体</span><span class="sxs-lookup"><span data-stu-id="78591-102">COR_GC_REFERENCE Structure</span></span>
<span data-ttu-id="78591-103">ガベージ コレクトされるオブジェクトに関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="78591-103">Contains information about an object that is to be garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78591-104">構文</span><span class="sxs-lookup"><span data-stu-id="78591-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_GC_REFERENCE {  
    ICorDebugAppDomain *domain;   
    ICorDebugValue *location;  
    CorGCReferenceType type;  
    UINT64 extraData;  
} COR_GC_REFERENCE;  
```  
  
## <a name="members"></a><span data-ttu-id="78591-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="78591-105">Members</span></span>  
  
|<span data-ttu-id="78591-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="78591-106">Member</span></span>|<span data-ttu-id="78591-107">説明</span><span class="sxs-lookup"><span data-stu-id="78591-107">Description</span></span>|  
|------------|-----------------|  
|`domain`|<span data-ttu-id="78591-108">ハンドルまたはオブジェクトが属するアプリケーションドメインへのポインター。</span><span class="sxs-lookup"><span data-stu-id="78591-108">A pointer to the application domain to which the handle or object belongs.</span></span> <span data-ttu-id="78591-109">この値は`null`、の場合もあります。</span><span class="sxs-lookup"><span data-stu-id="78591-109">Its value may be `null`.</span></span>|  
|`location`|<span data-ttu-id="78591-110">ガベージコレクションされるオブジェクトに対応する ICorDebugValue またはの値のインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="78591-110">Either an ICorDebugValue or an ICorDebugReferenceValue interface that corresponds to the object to be garbage-collected.</span></span>|  
|`type`|<span data-ttu-id="78591-111">ルートの取得元を示す[Corgcreの Encetype](corgcreferencetype-enumeration.md)列挙値。</span><span class="sxs-lookup"><span data-stu-id="78591-111">A [CorGCReferenceType](corgcreferencetype-enumeration.md) enumeration value that indicates where the root came from.</span></span> <span data-ttu-id="78591-112">詳細については、「解説」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="78591-112">For more information, see the Remarks section.</span></span>|  
|`extraData`|<span data-ttu-id="78591-113">ガベージコレクションされるオブジェクトに関する追加データ。</span><span class="sxs-lookup"><span data-stu-id="78591-113">Additional data about the object to be garbage-collected.</span></span> <span data-ttu-id="78591-114">この情報は`type` 、フィールドに示されているように、オブジェクトのソースによって異なります。</span><span class="sxs-lookup"><span data-stu-id="78591-114">This information depends on the source of the object, as indicated by the `type` field.</span></span> <span data-ttu-id="78591-115">詳細については、「解説」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="78591-115">For more information, see the Remarks section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="78591-116">コメント</span><span class="sxs-lookup"><span data-stu-id="78591-116">Remarks</span></span>  
 <span data-ttu-id="78591-117">フィールドは、参照の取得元を示す[corgcreの型](corgcreferencetype-enumeration.md)の列挙値です。 `type`</span><span class="sxs-lookup"><span data-stu-id="78591-117">The `type` field is a [CorGCReferenceType](corgcreferencetype-enumeration.md) enumeration value that indicates where the reference came from.</span></span> <span data-ttu-id="78591-118">特定`COR_GC_REFERENCE`の値には、次のいずれかの種類のマネージオブジェクトを反映できます。</span><span class="sxs-lookup"><span data-stu-id="78591-118">A particular `COR_GC_REFERENCE` value can reflect any of the following kinds of managed objects:</span></span>  
  
- <span data-ttu-id="78591-119">すべてのマネージスタックのオブジェクト`CorGCReferenceType.CorReferenceStack`()。</span><span class="sxs-lookup"><span data-stu-id="78591-119">Objects from all managed stacks (`CorGCReferenceType.CorReferenceStack`).</span></span> <span data-ttu-id="78591-120">これには、マネージコードのライブ参照や、共通言語ランタイムによって作成されたオブジェクトが含まれます。</span><span class="sxs-lookup"><span data-stu-id="78591-120">This includes live references in managed code, as well as objects created by the common language runtime.</span></span>  
  
- <span data-ttu-id="78591-121">ハンドルテーブルからのオブジェクト (`CorGCReferenceType.CorHandle*`)。</span><span class="sxs-lookup"><span data-stu-id="78591-121">Objects from the handle table (`CorGCReferenceType.CorHandle*`).</span></span> <span data-ttu-id="78591-122">これには、モジュール`HNDTYPE_STRONG`内`HNDTYPE_REFCOUNT`の厳密な参照 (および) と静的変数が含まれます。</span><span class="sxs-lookup"><span data-stu-id="78591-122">This includes strong references (`HNDTYPE_STRONG` and `HNDTYPE_REFCOUNT`) and static variables in a module.</span></span>  
  
- <span data-ttu-id="78591-123">ファイナライザーキュー (`CorGCReferenceType.CorReferenceFinalizer`) からのオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="78591-123">Objects from the finalizer queue (`CorGCReferenceType.CorReferenceFinalizer`).</span></span> <span data-ttu-id="78591-124">ファイナライザーが実行されるまで、ファイナライザーはオブジェクトをキューに置いています。</span><span class="sxs-lookup"><span data-stu-id="78591-124">The finalizer queue roots objects until the finalizer has run.</span></span>  
  
 <span data-ttu-id="78591-125">フィールド`extraData`には、参照のソース (または型) に応じて追加のデータが含まれます。</span><span class="sxs-lookup"><span data-stu-id="78591-125">The `extraData` field contains extra data depending on the source (or type) of the reference.</span></span> <span data-ttu-id="78591-126">指定できる値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="78591-126">Possible values are:</span></span>  
  
- <span data-ttu-id="78591-127">`DependentSource`。</span><span class="sxs-lookup"><span data-stu-id="78591-127">`DependentSource`.</span></span> <span data-ttu-id="78591-128">がの場合、このフィールドはオブジェクトであり、alive の場合、ガベージコレクト`COR_GC_REFERENCE.Location`されるオブジェクトがルートになります。 `CorGCREferenceType.CorHandleStrongDependent` `type`</span><span class="sxs-lookup"><span data-stu-id="78591-128">If the `type` is `CorGCREferenceType.CorHandleStrongDependent`, this field is the object that, if alive, roots the object to be garbage-collected at `COR_GC_REFERENCE.Location`.</span></span>  
  
- <span data-ttu-id="78591-129">`RefCount`。</span><span class="sxs-lookup"><span data-stu-id="78591-129">`RefCount`.</span></span> <span data-ttu-id="78591-130">`type` が`CorGCREferenceType.CorHandleStrongRefCount`の場合、このフィールドはハンドルの参照カウントです。</span><span class="sxs-lookup"><span data-stu-id="78591-130">If the `type` is `CorGCREferenceType.CorHandleStrongRefCount`, this field is the reference count of the handle.</span></span>  
  
- <span data-ttu-id="78591-131">`Size`。</span><span class="sxs-lookup"><span data-stu-id="78591-131">`Size`.</span></span> <span data-ttu-id="78591-132">がの場合`CorGCREferenceType.CorHandleStrongSizedByref`、このフィールドはガベージコレクターによってオブジェクトのルートが計算されたオブジェクトツリーの最後のサイズになります。 `type`</span><span class="sxs-lookup"><span data-stu-id="78591-132">If the `type` is `CorGCREferenceType.CorHandleStrongSizedByref`, this field is the last size of the object tree for which the garbage collector calculated the object roots.</span></span> <span data-ttu-id="78591-133">この計算は必ずしも最新の状態ではないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="78591-133">Note that this calculation is not necessarily up to date.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="78591-134">要件</span><span class="sxs-lookup"><span data-stu-id="78591-134">Requirements</span></span>  
 <span data-ttu-id="78591-135">**・** [システム要件](../../get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="78591-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="78591-136">**ヘッダー:** CorDebug .idl、CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="78591-136">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="78591-137">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="78591-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="78591-138">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="78591-138">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78591-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="78591-139">See also</span></span>

- [<span data-ttu-id="78591-140">デバッグ構造体</span><span class="sxs-lookup"><span data-stu-id="78591-140">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="78591-141">デバッグ</span><span class="sxs-lookup"><span data-stu-id="78591-141">Debugging</span></span>](index.md)
