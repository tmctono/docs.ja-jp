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
ms.openlocfilehash: 635cb0c003889beb2f78e8413189cbfc4b064175
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73099143"
---
# <a name="cor_gc_reference-structure"></a><span data-ttu-id="ba3f9-102">COR_GC_REFERENCE 構造体</span><span class="sxs-lookup"><span data-stu-id="ba3f9-102">COR_GC_REFERENCE Structure</span></span>
<span data-ttu-id="ba3f9-103">ガベージ コレクトされるオブジェクトに関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="ba3f9-103">Contains information about an object that is to be garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba3f9-104">構文</span><span class="sxs-lookup"><span data-stu-id="ba3f9-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_GC_REFERENCE {  
    ICorDebugAppDomain *domain;   
    ICorDebugValue *location;  
    CorGCReferenceType type;  
    UINT64 extraData;  
} COR_GC_REFERENCE;  
```  
  
## <a name="members"></a><span data-ttu-id="ba3f9-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="ba3f9-105">Members</span></span>  
  
|<span data-ttu-id="ba3f9-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="ba3f9-106">Member</span></span>|<span data-ttu-id="ba3f9-107">説明</span><span class="sxs-lookup"><span data-stu-id="ba3f9-107">Description</span></span>|  
|------------|-----------------|  
|`domain`|<span data-ttu-id="ba3f9-108">ハンドルまたはオブジェクトが属するアプリケーションドメインへのポインター。</span><span class="sxs-lookup"><span data-stu-id="ba3f9-108">A pointer to the application domain to which the handle or object belongs.</span></span> <span data-ttu-id="ba3f9-109">この値は `null`にすることができます。</span><span class="sxs-lookup"><span data-stu-id="ba3f9-109">Its value may be `null`.</span></span>|  
|`location`|<span data-ttu-id="ba3f9-110">ガベージコレクションされるオブジェクトに対応する ICorDebugValue またはの値のインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="ba3f9-110">Either an ICorDebugValue or an ICorDebugReferenceValue interface that corresponds to the object to be garbage-collected.</span></span>|  
|`type`|<span data-ttu-id="ba3f9-111">ルートの取得元を示す[Corgcreの Encetype](corgcreferencetype-enumeration.md)列挙値。</span><span class="sxs-lookup"><span data-stu-id="ba3f9-111">A [CorGCReferenceType](corgcreferencetype-enumeration.md) enumeration value that indicates where the root came from.</span></span> <span data-ttu-id="ba3f9-112">詳細については、「解説」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ba3f9-112">For more information, see the Remarks section.</span></span>|  
|`extraData`|<span data-ttu-id="ba3f9-113">ガベージコレクションされるオブジェクトに関する追加データ。</span><span class="sxs-lookup"><span data-stu-id="ba3f9-113">Additional data about the object to be garbage-collected.</span></span> <span data-ttu-id="ba3f9-114">この情報は、[`type`] フィールドに示されているように、オブジェクトのソースによって異なります。</span><span class="sxs-lookup"><span data-stu-id="ba3f9-114">This information depends on the source of the object, as indicated by the `type` field.</span></span> <span data-ttu-id="ba3f9-115">詳細については、「解説」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ba3f9-115">For more information, see the Remarks section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ba3f9-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="ba3f9-116">Remarks</span></span>  
 <span data-ttu-id="ba3f9-117">`type` フィールドは、参照の取得元を示す[Corgcreの型](corgcreferencetype-enumeration.md)の列挙値です。</span><span class="sxs-lookup"><span data-stu-id="ba3f9-117">The `type` field is a [CorGCReferenceType](corgcreferencetype-enumeration.md) enumeration value that indicates where the reference came from.</span></span> <span data-ttu-id="ba3f9-118">特定の `COR_GC_REFERENCE` 値には、次のいずれかの種類のマネージオブジェクトを反映できます。</span><span class="sxs-lookup"><span data-stu-id="ba3f9-118">A particular `COR_GC_REFERENCE` value can reflect any of the following kinds of managed objects:</span></span>  
  
- <span data-ttu-id="ba3f9-119">すべてのマネージスタックのオブジェクト (`CorGCReferenceType.CorReferenceStack`)。</span><span class="sxs-lookup"><span data-stu-id="ba3f9-119">Objects from all managed stacks (`CorGCReferenceType.CorReferenceStack`).</span></span> <span data-ttu-id="ba3f9-120">これには、マネージコードのライブ参照や、共通言語ランタイムによって作成されたオブジェクトが含まれます。</span><span class="sxs-lookup"><span data-stu-id="ba3f9-120">This includes live references in managed code, as well as objects created by the common language runtime.</span></span>  
  
- <span data-ttu-id="ba3f9-121">ハンドルテーブルのオブジェクト (`CorGCReferenceType.CorHandle*`)。</span><span class="sxs-lookup"><span data-stu-id="ba3f9-121">Objects from the handle table (`CorGCReferenceType.CorHandle*`).</span></span> <span data-ttu-id="ba3f9-122">これには、厳密な参照 (`HNDTYPE_STRONG` と `HNDTYPE_REFCOUNT`) と、モジュール内の静的変数が含まれます。</span><span class="sxs-lookup"><span data-stu-id="ba3f9-122">This includes strong references (`HNDTYPE_STRONG` and `HNDTYPE_REFCOUNT`) and static variables in a module.</span></span>  
  
- <span data-ttu-id="ba3f9-123">ファイナライザーキューのオブジェクト (`CorGCReferenceType.CorReferenceFinalizer`)。</span><span class="sxs-lookup"><span data-stu-id="ba3f9-123">Objects from the finalizer queue (`CorGCReferenceType.CorReferenceFinalizer`).</span></span> <span data-ttu-id="ba3f9-124">ファイナライザーが実行されるまで、ファイナライザーはオブジェクトをキューに置いています。</span><span class="sxs-lookup"><span data-stu-id="ba3f9-124">The finalizer queue roots objects until the finalizer has run.</span></span>  
  
 <span data-ttu-id="ba3f9-125">`extraData` フィールドには、参照のソース (または型) に応じて追加のデータが含まれます。</span><span class="sxs-lookup"><span data-stu-id="ba3f9-125">The `extraData` field contains extra data depending on the source (or type) of the reference.</span></span> <span data-ttu-id="ba3f9-126">指定できる値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ba3f9-126">Possible values are:</span></span>  
  
- <span data-ttu-id="ba3f9-127">`DependentSource`.</span><span class="sxs-lookup"><span data-stu-id="ba3f9-127">`DependentSource`.</span></span> <span data-ttu-id="ba3f9-128">`type` が `CorGCREferenceType.CorHandleStrongDependent`の場合、このフィールドは、`COR_GC_REFERENCE.Location`でガベージコレクトされるオブジェクトをルートとして持つオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="ba3f9-128">If the `type` is `CorGCREferenceType.CorHandleStrongDependent`, this field is the object that, if alive, roots the object to be garbage-collected at `COR_GC_REFERENCE.Location`.</span></span>  
  
- <span data-ttu-id="ba3f9-129">`RefCount`.</span><span class="sxs-lookup"><span data-stu-id="ba3f9-129">`RefCount`.</span></span> <span data-ttu-id="ba3f9-130">`type` が `CorGCREferenceType.CorHandleStrongRefCount`の場合、このフィールドはハンドルの参照カウントになります。</span><span class="sxs-lookup"><span data-stu-id="ba3f9-130">If the `type` is `CorGCREferenceType.CorHandleStrongRefCount`, this field is the reference count of the handle.</span></span>  
  
- <span data-ttu-id="ba3f9-131">`Size`.</span><span class="sxs-lookup"><span data-stu-id="ba3f9-131">`Size`.</span></span> <span data-ttu-id="ba3f9-132">`type` が `CorGCREferenceType.CorHandleStrongSizedByref`場合、このフィールドはガベージコレクターによってオブジェクトのルートが計算されたオブジェクトツリーの最後のサイズになります。</span><span class="sxs-lookup"><span data-stu-id="ba3f9-132">If the `type` is `CorGCREferenceType.CorHandleStrongSizedByref`, this field is the last size of the object tree for which the garbage collector calculated the object roots.</span></span> <span data-ttu-id="ba3f9-133">この計算は必ずしも最新の状態ではないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="ba3f9-133">Note that this calculation is not necessarily up to date.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ba3f9-134">［要件］</span><span class="sxs-lookup"><span data-stu-id="ba3f9-134">Requirements</span></span>  
 <span data-ttu-id="ba3f9-135">**:** 「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ba3f9-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba3f9-136">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ba3f9-136">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ba3f9-137">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ba3f9-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ba3f9-138">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba3f9-138">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba3f9-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="ba3f9-139">See also</span></span>

- [<span data-ttu-id="ba3f9-140">デバッグ構造体</span><span class="sxs-lookup"><span data-stu-id="ba3f9-140">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="ba3f9-141">デバッグ</span><span class="sxs-lookup"><span data-stu-id="ba3f9-141">Debugging</span></span>](index.md)
