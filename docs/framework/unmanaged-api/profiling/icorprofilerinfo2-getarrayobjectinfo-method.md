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
ms.openlocfilehash: 839cd574e5352b74b47cd6242d5706bc6405d439
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76862920"
---
# <a name="icorprofilerinfo2getarrayobjectinfo-method"></a><span data-ttu-id="ea00d-102">ICorProfilerInfo2::GetArrayObjectInfo メソッド</span><span class="sxs-lookup"><span data-stu-id="ea00d-102">ICorProfilerInfo2::GetArrayObjectInfo Method</span></span>
<span data-ttu-id="ea00d-103">配列オブジェクトに関する詳細情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="ea00d-103">Gets detailed information about an array object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea00d-104">構文</span><span class="sxs-lookup"><span data-stu-id="ea00d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetArrayObjectInfo(  
    [in] ObjectID objectId,  
    [in] ULONG32 cDimensions,  
    [out, size_is(cDimensions), length_is(cDimensions)] ULONG32 pDimensionSizes[],  
    [out, size_is(cDimensions), length_is(cDimensions)] int pDimensionLowerBounds[],  
    [out] BYTE **ppData);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ea00d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ea00d-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="ea00d-106">から有効な配列オブジェクトの ID。</span><span class="sxs-lookup"><span data-stu-id="ea00d-106">[in] The ID of a valid array object.</span></span>  
  
 `cDimensions`  
 <span data-ttu-id="ea00d-107">から配列のランク (次元数)。</span><span class="sxs-lookup"><span data-stu-id="ea00d-107">[in] The rank (number of dimensions) of the array.</span></span>  
  
 `pDimensionSizes`  
 <span data-ttu-id="ea00d-108">入出力それぞれが配列の次元のサイズを表す整数を格納している配列。</span><span class="sxs-lookup"><span data-stu-id="ea00d-108">[out] An array that contains integers, each representing the size of a dimension of the array.</span></span>  
  
 `pDimensionLowerBounds`  
 <span data-ttu-id="ea00d-109">入出力それぞれが配列の次元の下限を表す整数を格納している配列。</span><span class="sxs-lookup"><span data-stu-id="ea00d-109">[out] An array that contains integers, each representing the lower bound of a dimension of the array.</span></span>  
  
 `ppData`  
 <span data-ttu-id="ea00d-110">入出力C++規則に従ってレイアウトされる、配列の生バッファーのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="ea00d-110">[out] A pointer to the address of the raw buffer for the array, which is laid out according to the C++ convention.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ea00d-111">コメント</span><span class="sxs-lookup"><span data-stu-id="ea00d-111">Remarks</span></span>  
 <span data-ttu-id="ea00d-112">`pDimensionSizes` と `pDimensionLowerBounds` は並列配列であるため、各配列内の同じインデックスにある要素は同じエンティティの特性です。</span><span class="sxs-lookup"><span data-stu-id="ea00d-112">The `pDimensionSizes` and `pDimensionLowerBounds` are parallel arrays, so the elements located at the same index in each array are characteristics of the same entity.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea00d-113">要件</span><span class="sxs-lookup"><span data-stu-id="ea00d-113">Requirements</span></span>  
 <span data-ttu-id="ea00d-114">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ea00d-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea00d-115">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ea00d-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ea00d-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ea00d-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ea00d-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea00d-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea00d-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="ea00d-118">See also</span></span>

- [<span data-ttu-id="ea00d-119">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ea00d-119">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="ea00d-120">ICorProfilerInfo2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ea00d-120">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
