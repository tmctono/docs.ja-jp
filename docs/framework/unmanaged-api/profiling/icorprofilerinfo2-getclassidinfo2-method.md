---
title: ICorProfilerInfo2::GetClassIDInfo2 メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetClassIDInfo2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetClassIDInfo2
helpviewer_keywords:
- GetClassIDInfo2 method [.NET Framework profiling]
- ICorProfilerInfo2::GetClassIDInfo2 method [.NET Framework profiling]
ms.assetid: 0141d582-d066-4d49-8d1f-ae82129a1960
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7b98746be189e211572e5517aac1f06825973b39
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61779783"
---
# <a name="icorprofilerinfo2getclassidinfo2-method"></a><span data-ttu-id="ad528-102">ICorProfilerInfo2::GetClassIDInfo2 メソッド</span><span class="sxs-lookup"><span data-stu-id="ad528-102">ICorProfilerInfo2::GetClassIDInfo2 Method</span></span>
<span data-ttu-id="ad528-103">親モジュールとメタデータを指定したクラスの一般的な定義を開くをトークン取得、`ClassID`その親クラスの`ClassID`クラスの存在する場合、各型引数。</span><span class="sxs-lookup"><span data-stu-id="ad528-103">Gets the parent module and metadata token for the open generic definition of the specified class, the `ClassID` of its parent class, and the `ClassID` for each type argument, if present, of the class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad528-104">構文</span><span class="sxs-lookup"><span data-stu-id="ad528-104">Syntax</span></span>  
  
```  
HRESULT GetClassIDInfo2(  
    [in]  ClassID classId,  
    [out] ModuleID *pModuleId,  
    [out] mdTypeDef *pTypeDefToken,  
    [out] ClassID *pParentClassId,  
    [in]  ULONG32 cNumTypeArgs,  
    [out] ULONG32 *pcNumTypeArgs,  
    [out] ClassID typeArgs[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ad528-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ad528-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="ad528-106">[in] 情報が取得されるクラスの ID。</span><span class="sxs-lookup"><span data-stu-id="ad528-106">[in] The ID of the class for which information will be retrieved.</span></span>  
  
 `pModuleId`  
 <span data-ttu-id="ad528-107">[out]指定したクラスの一般的な定義を開くの親モジュールの ID へのポインター。</span><span class="sxs-lookup"><span data-stu-id="ad528-107">[out] Pointer to the ID of the parent module for the open generic definition of the specified class.</span></span>  
  
 `pTypeDefToken`  
 <span data-ttu-id="ad528-108">[out]指定したクラスのオープン ジェネリック定義のメタデータ トークンへのポインター。</span><span class="sxs-lookup"><span data-stu-id="ad528-108">[out] Pointer to the metadata token for the open generic definition of the specified class.</span></span>  
  
 `pParentClassId`  
 <span data-ttu-id="ad528-109">[out] 親クラスの ID へのポインター。</span><span class="sxs-lookup"><span data-stu-id="ad528-109">[out] Pointer to the ID of the parent class.</span></span>  
  
 `cNumTypeArgs`  
 <span data-ttu-id="ad528-110">[in] `typeArgs` 配列のサイズ。</span><span class="sxs-lookup"><span data-stu-id="ad528-110">[in] The size of the `typeArgs` array.</span></span>  
  
 `pcNumTypeArgs`  
 <span data-ttu-id="ad528-111">[out] 使用できる要素の総数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="ad528-111">[out] Pointer to the total number of available elements.</span></span>  
  
 `typeArgs`  
 <span data-ttu-id="ad528-112">[out] `ClassID` 値の配列。各値は、クラスの型引数の ID を表します。</span><span class="sxs-lookup"><span data-stu-id="ad528-112">[out] An array of `ClassID` values, each of which represents the ID of a type argument of the class.</span></span> <span data-ttu-id="ad528-113">このメソッドが戻るとき、使用できる `ClassID` 値の一部またはすべてが `typeArgs` に格納されます。</span><span class="sxs-lookup"><span data-stu-id="ad528-113">When the method returns, `typeArgs` will contain some or all the available `ClassID` values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ad528-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="ad528-114">Remarks</span></span>  
 <span data-ttu-id="ad528-115">`GetClassIDInfo2`メソッドは、 [icorprofilerinfo::getclassidinfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getclassidinfo-method.md)メソッドが`GetClassIDInfo2`ジェネリック型に関する追加情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="ad528-115">The `GetClassIDInfo2` method is similar to the [ICorProfilerInfo::GetClassIDInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getclassidinfo-method.md) method, but `GetClassIDInfo2` obtains additional information about a generic type.</span></span>  
  
 <span data-ttu-id="ad528-116">プロファイラー コードを呼び出すことができます[icorprofilerinfo::getmodulemetadata](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md)を取得する、[メタデータ](../../../../docs/framework/unmanaged-api/metadata/index.md)指定したモジュールのインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="ad528-116">The profiler code can call [ICorProfilerInfo::GetModuleMetaData](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md) to obtain a [metadata](../../../../docs/framework/unmanaged-api/metadata/index.md) interface for a given module.</span></span> <span data-ttu-id="ad528-117">`pTypeDefToken` によって参照される場所に返されるメタデータ トークンを使用すると、クラスのメタデータにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="ad528-117">The metadata token that is returned to the location referenced by `pTypeDefToken` can then be used to access the metadata for the class.</span></span>  
  
 <span data-ttu-id="ad528-118">`GetClassIDInfo2` から制御が戻ったら、`typeArgs` バッファーのサイズが十分で、すべての `ClassID` 値を格納できたかどうかを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad528-118">After `GetClassIDInfo2` returns, you must verify that the `typeArgs` buffer was large enough to contain all the `ClassID` values.</span></span> <span data-ttu-id="ad528-119">これを行うには、`pcNumTypeArgs` が指している値を `cNumTypeArgs` パラメーターの値と比較します。</span><span class="sxs-lookup"><span data-stu-id="ad528-119">To do this, compare the value that `pcNumTypeArgs` points to with the value of the `cNumTypeArgs` parameter.</span></span> <span data-ttu-id="ad528-120">`pcNumTypeArgs` が指している値が `cNumTypeArgs` の値より大きい場合は、`typeArgs` バッファーの割り当てを増やし、`cNumTypeArgs` を新しい大きいサイズに更新して、`GetClassIDInfo2` を再度呼び出します。</span><span class="sxs-lookup"><span data-stu-id="ad528-120">If `pcNumTypeArgs` points to a value that is larger than `cNumTypeArgs`, allocate a larger `typeArgs` buffer, update `cNumTypeArgs` with the new, larger size, and call `GetClassIDInfo2` again.</span></span>  
  
 <span data-ttu-id="ad528-121">別の方法として、最初に `GetClassIDInfo2` を長さゼロの `typeArgs` バッファーで呼び出して、適切なバッファーのサイズを取得します。</span><span class="sxs-lookup"><span data-stu-id="ad528-121">Alternatively, you can first call `GetClassIDInfo2` with a zero-length `typeArgs` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="ad528-122">その後、`typeArgs` バッファーのサイズを `pcNumTypeArgs` に返された値に設定し、`GetClassIDInfo2` を再度呼び出します。</span><span class="sxs-lookup"><span data-stu-id="ad528-122">You can then set the `typeArgs` buffer size to the value returned in `pcNumTypeArgs` and call `GetClassIDInfo2` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad528-123">必要条件</span><span class="sxs-lookup"><span data-stu-id="ad528-123">Requirements</span></span>  
 <span data-ttu-id="ad528-124">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ad528-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad528-125">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ad528-125">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ad528-126">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ad528-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ad528-127">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad528-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad528-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="ad528-128">See also</span></span>

- [<span data-ttu-id="ad528-129">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ad528-129">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="ad528-130">ICorProfilerInfo2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ad528-130">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
- [<span data-ttu-id="ad528-131">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="ad528-131">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="ad528-132">プロファイル</span><span class="sxs-lookup"><span data-stu-id="ad528-132">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
