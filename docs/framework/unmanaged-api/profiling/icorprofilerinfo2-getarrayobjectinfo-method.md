---
title: ICorProfilerInfo2::GetArrayObjectInfo メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetArrayObjectInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetArrayObjectInfo
helpviewer_keywords:
- ICorProfilerInfo2::GetArrayObjectInfo method [.NET Framework profiling]
- GetArrayObjectInfo method [.NET Framework profiling]
ms.assetid: bda75017-739f-4ce5-9000-f3b526e8473c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7fe86fbe7ee51e5f53eeea74d7d5a56046de5e00
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57484395"
---
# <a name="icorprofilerinfo2getarrayobjectinfo-method"></a><span data-ttu-id="735a7-102">ICorProfilerInfo2::GetArrayObjectInfo メソッド</span><span class="sxs-lookup"><span data-stu-id="735a7-102">ICorProfilerInfo2::GetArrayObjectInfo Method</span></span>
<span data-ttu-id="735a7-103">配列オブジェクトに関する詳細な情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="735a7-103">Gets detailed information about an array object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="735a7-104">構文</span><span class="sxs-lookup"><span data-stu-id="735a7-104">Syntax</span></span>  
  
```  
HRESULT GetArrayObjectInfo(  
    [in] ObjectID objectId,  
    [in] ULONG32 cDimensions,  
    [out, size_is(cDimensions), length_is(cDimensions)] ULONG32 pDimensionSizes[],  
    [out, size_is(cDimensions), length_is(cDimensions)] int pDimensionLowerBounds[],  
    [out] BYTE **ppData);  
```  
  
## <a name="parameters"></a><span data-ttu-id="735a7-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="735a7-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="735a7-106">[in]有効な配列オブジェクトの ID。</span><span class="sxs-lookup"><span data-stu-id="735a7-106">[in] The ID of a valid array object.</span></span>  
  
 `cDimensions`  
 <span data-ttu-id="735a7-107">[in]配列のランク (次元数)。</span><span class="sxs-lookup"><span data-stu-id="735a7-107">[in] The rank (number of dimensions) of the array.</span></span>  
  
 `pDimensionSizes`  
 <span data-ttu-id="735a7-108">[out]各配列の次元のサイズを表す整数を格納する配列。</span><span class="sxs-lookup"><span data-stu-id="735a7-108">[out] An array that contains integers, each representing the size of a dimension of the array.</span></span>  
  
 `pDimensionLowerBounds`  
 <span data-ttu-id="735a7-109">[out]整数を含む配列、配列の次元の下限を表す各バインドされています。</span><span class="sxs-lookup"><span data-stu-id="735a7-109">[out] An array that contains integers, each representing the lower bound of a dimension of the array.</span></span>  
  
 `ppData`  
 <span data-ttu-id="735a7-110">[out]C++ の規約に従ってレイアウトは、配列の生バッファーのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="735a7-110">[out] A pointer to the address of the raw buffer for the array, which is laid out according to the C++ convention.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="735a7-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="735a7-111">Remarks</span></span>  
 <span data-ttu-id="735a7-112">`pDimensionSizes`と`pDimensionLowerBounds`は並列配列は、各配列内の同じインデックス位置にある要素は、同じエンティティの特性。</span><span class="sxs-lookup"><span data-stu-id="735a7-112">The `pDimensionSizes` and `pDimensionLowerBounds` are parallel arrays, so the elements located at the same index in each array are characteristics of the same entity.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="735a7-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="735a7-113">Requirements</span></span>  
 <span data-ttu-id="735a7-114">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="735a7-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="735a7-115">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="735a7-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="735a7-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="735a7-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="735a7-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="735a7-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="735a7-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="735a7-118">See also</span></span>
- [<span data-ttu-id="735a7-119">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="735a7-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="735a7-120">ICorProfilerInfo2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="735a7-120">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
