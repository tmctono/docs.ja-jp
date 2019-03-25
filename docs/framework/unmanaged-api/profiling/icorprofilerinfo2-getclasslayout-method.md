---
title: ICorProfilerInfo2::GetClassLayout メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetClassLayout
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetClassLayout
helpviewer_keywords:
- ICorProfilerInfo2::GetClassLayout method [.NET Framework profiling]
- GetClassLayout method, ICorProfilerInfo2 interface [.NET Framework profiling]
ms.assetid: a3a36987-5666-4e2f-95b5-d0cb246502ec
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f5995eac780241b5d0a01b99b23ec91c2f325e2a
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57478805"
---
# <a name="icorprofilerinfo2getclasslayout-method"></a><span data-ttu-id="c31c2-102">ICorProfilerInfo2::GetClassLayout メソッド</span><span class="sxs-lookup"><span data-stu-id="c31c2-102">ICorProfilerInfo2::GetClassLayout Method</span></span>
<span data-ttu-id="c31c2-103">指定したクラスで定義されるフィールドのメモリ内レイアウトに関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="c31c2-103">Gets information about the layout, in memory, of the fields defined by the specified class.</span></span> <span data-ttu-id="c31c2-104">つまり、このメソッドはクラスのフィールドのオフセットを取得します。</span><span class="sxs-lookup"><span data-stu-id="c31c2-104">That is, this method gets the offsets of the class's fields.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c31c2-105">構文</span><span class="sxs-lookup"><span data-stu-id="c31c2-105">Syntax</span></span>  
  
```  
HRESULT GetClassLayout(  
    [in]  ClassID classID,  
    [in, out] COR_FIELD_OFFSET rFieldOffset[],  
    [in]  ULONG cFieldOffset,  
    [out] ULONG *pcFieldOffset,  
    [out] ULONG *pulClassSize);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c31c2-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c31c2-106">Parameters</span></span>  
 `classID`  
 <span data-ttu-id="c31c2-107">[in] レイアウトを取得するクラスの ID。</span><span class="sxs-lookup"><span data-stu-id="c31c2-107">[in] The ID of the class for which the layout will be retrieved.</span></span>  
  
 `rFieldOffset`  
 <span data-ttu-id="c31c2-108">[入力、出力]配列の[COR_FIELD_OFFSET](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md)トークンとクラスのフィールドのオフセットを含む各構造体。</span><span class="sxs-lookup"><span data-stu-id="c31c2-108">[in, out] An array of [COR_FIELD_OFFSET](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md) structures, each of which contains the tokens and offsets of the class's fields.</span></span>  
  
 `cFieldOffset`  
 <span data-ttu-id="c31c2-109">[in] `rFieldOffset` 配列のサイズ。</span><span class="sxs-lookup"><span data-stu-id="c31c2-109">[in] The size of the `rFieldOffset` array.</span></span>  
  
 `pcFieldOffset`  
 <span data-ttu-id="c31c2-110">[out] 使用できる要素の総数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="c31c2-110">[out] A pointer to the total number of available elements.</span></span> <span data-ttu-id="c31c2-111">`cFieldOffset` が 0 である場合、この値は必要な要素の数を示します。</span><span class="sxs-lookup"><span data-stu-id="c31c2-111">If `cFieldOffset` is 0, this value indicates the number of elements needed.</span></span>  
  
 `pulClassSize`  
 <span data-ttu-id="c31c2-112">[out] クラスのサイズ (バイト単位) を含む位置へのポインター。</span><span class="sxs-lookup"><span data-stu-id="c31c2-112">[out] A pointer to a location that contains the size, in bytes, of the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c31c2-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="c31c2-113">Remarks</span></span>  
 <span data-ttu-id="c31c2-114">`GetClassLayout` メソッドは、クラス自体によって定義されているフィールドのみを返します。</span><span class="sxs-lookup"><span data-stu-id="c31c2-114">The `GetClassLayout` method returns only the fields defined by the class itself.</span></span> <span data-ttu-id="c31c2-115">クラスの親クラスもフィールドを定義している場合、プロファイラーは親クラスで `GetClassLayout` を呼び出してそのフィールドを取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c31c2-115">If the class's parent class has defined fields as well, the profiler must call `GetClassLayout` on the parent class to obtain those fields.</span></span>  
  
 <span data-ttu-id="c31c2-116">`GetClassLayout` を文字列クラスと一緒に使用する場合、このメソッドは E_INVALIDARG というエラー コードで失敗します。</span><span class="sxs-lookup"><span data-stu-id="c31c2-116">If you use `GetClassLayout` with string classes, the method will fail with error code E_INVALIDARG.</span></span> <span data-ttu-id="c31c2-117">使用[icorprofilerinfo 2::getstringlayout](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getstringlayout-method.md)文字列のレイアウトに関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="c31c2-117">Use [ICorProfilerInfo2::GetStringLayout](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getstringlayout-method.md) to get information about the layout of a string.</span></span> <span data-ttu-id="c31c2-118">`GetClassLayout` は、配列クラスを使用して呼び出される場合も失敗します。</span><span class="sxs-lookup"><span data-stu-id="c31c2-118">`GetClassLayout` will also fail when called with an array class.</span></span>  
  
 <span data-ttu-id="c31c2-119">`GetClassLayout` から制御が戻ったら、`rFieldOffset` バッファーのサイズが十分で、すべての使用可能な `COR_FIELD_OFFSET` 構造体を格納できたかどうかを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c31c2-119">After `GetClassLayout` returns, you must verify that the `rFieldOffset` buffer was large enough to contain all the available `COR_FIELD_OFFSET` structures.</span></span> <span data-ttu-id="c31c2-120">これを行うには、`pcFieldOffset` が指している値と、`rFieldOffset` のサイズを `COR_FIELD_OFFSET` 構造体のサイズで割った値を比較します。</span><span class="sxs-lookup"><span data-stu-id="c31c2-120">To do this, compare the value that `pcFieldOffset` points to with the size of `rFieldOffset` divided by the size of a `COR_FIELD_OFFSET` structure.</span></span> <span data-ttu-id="c31c2-121">`rFieldOffset` の大きさが十分でない場合は、`rFieldOffset` バッファーの割り当てを増やし、`cFieldOffset` を新しい大きいサイズに更新して、`GetClassLayout` を再度呼び出します。</span><span class="sxs-lookup"><span data-stu-id="c31c2-121">If `rFieldOffset` is not large enough, allocate a larger `rFieldOffset` buffer, update `cFieldOffset` with the new, larger size, and call `GetClassLayout` again.</span></span>  
  
 <span data-ttu-id="c31c2-122">別の方法として、最初に長さ 0 の `rFieldOffset` バッファーで `GetClassLayout` を呼び出すことで、適切なバッファーのサイズを取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="c31c2-122">Alternatively, you can first call `GetClassLayout` with a zero-length `rFieldOffset` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="c31c2-123">その後、バッファーのサイズを `pcFieldOffset` で返された値に設定し、`GetClassLayout` を再度呼び出します。</span><span class="sxs-lookup"><span data-stu-id="c31c2-123">You can then set the buffer size to the value returned in `pcFieldOffset` and call `GetClassLayout` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c31c2-124">必要条件</span><span class="sxs-lookup"><span data-stu-id="c31c2-124">Requirements</span></span>  
 <span data-ttu-id="c31c2-125">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c31c2-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c31c2-126">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c31c2-126">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c31c2-127">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c31c2-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c31c2-128">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c31c2-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c31c2-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="c31c2-129">See also</span></span>
- [<span data-ttu-id="c31c2-130">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c31c2-130">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="c31c2-131">ICorProfilerInfo2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c31c2-131">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
- [<span data-ttu-id="c31c2-132">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="c31c2-132">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="c31c2-133">プロファイル</span><span class="sxs-lookup"><span data-stu-id="c31c2-133">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
