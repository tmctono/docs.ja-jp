---
title: ICorProfilerInfo::IsArrayClass メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.IsArrayClass
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::IsArrayClass
helpviewer_keywords:
- IsArrayClass method [.NET Framework profiling]
- ICorProfilerInfo::IsArrayClass method [.NET Framework profiling]
ms.assetid: 7f230961-23a6-4d56-ad2d-7a876d65705f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5e00e7f39bc2f8c14db0676102a52089c7710bd6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67772252"
---
# <a name="icorprofilerinfoisarrayclass-method"></a><span data-ttu-id="f4202-102">ICorProfilerInfo::IsArrayClass メソッド</span><span class="sxs-lookup"><span data-stu-id="f4202-102">ICorProfilerInfo::IsArrayClass Method</span></span>
<span data-ttu-id="f4202-103">指定したクラスが、配列クラスであるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="f4202-103">Determines whether the specified class is an array class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4202-104">構文</span><span class="sxs-lookup"><span data-stu-id="f4202-104">Syntax</span></span>  
  
```cpp  
HRESULT IsArrayClass(  
    [in]  ClassID        classId,  
    [out] CorElementType *pBaseElemType,  
    [out] ClassID        *pBaseClassId,  
    [out] ULONG          *pcRank);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f4202-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f4202-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="f4202-106">[in]調査するクラスの ID。</span><span class="sxs-lookup"><span data-stu-id="f4202-106">[in] The ID of the class to be examined.</span></span>  
  
 `pBaseElemType`  
 <span data-ttu-id="f4202-107">[out]配列要素の種類を示す CorElementType 列挙型の値へのポインター。</span><span class="sxs-lookup"><span data-stu-id="f4202-107">[out] A pointer to a value of the CorElementType enumeration that indicates the type of the array elements.</span></span>  
  
 `pBaseClassId`  
 <span data-ttu-id="f4202-108">[out]使用可能な場合は、配列の要素のクラス ID へのポインター。</span><span class="sxs-lookup"><span data-stu-id="f4202-108">[out] A pointer to the class ID of the array elements, when available.</span></span>  
  
 `pcRank`  
 <span data-ttu-id="f4202-109">[out]配列のランク (次元の数では、) を示す整数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="f4202-109">[out] A pointer to an integer that indicates the rank (that is, number of dimensions) of the array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f4202-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="f4202-110">Remarks</span></span>  
 <span data-ttu-id="f4202-111">指定したクラスが、配列クラスの場合、`IsArrayClass`メソッドは、S_OK HRESULT と null 以外の出力パラメーターに値を返します。</span><span class="sxs-lookup"><span data-stu-id="f4202-111">If the specified class is an array class, the `IsArrayClass` method returns an S_OK HRESULT and values for any non-null output parameters.</span></span> <span data-ttu-id="f4202-112">それ以外の場合、S_FALSE を返します。</span><span class="sxs-lookup"><span data-stu-id="f4202-112">Otherwise, it returns S_FALSE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f4202-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="f4202-113">Requirements</span></span>  
 <span data-ttu-id="f4202-114">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f4202-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4202-115">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f4202-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f4202-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f4202-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f4202-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f4202-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4202-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="f4202-118">See also</span></span>

- [<span data-ttu-id="f4202-119">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f4202-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
