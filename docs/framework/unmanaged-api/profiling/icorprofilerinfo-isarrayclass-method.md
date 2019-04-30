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
ms.openlocfilehash: 350221ae205636cef82581f3fe11367006dd8b2b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61968078"
---
# <a name="icorprofilerinfoisarrayclass-method"></a><span data-ttu-id="f0467-102">ICorProfilerInfo::IsArrayClass メソッド</span><span class="sxs-lookup"><span data-stu-id="f0467-102">ICorProfilerInfo::IsArrayClass Method</span></span>
<span data-ttu-id="f0467-103">指定したクラスが、配列クラスであるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="f0467-103">Determines whether the specified class is an array class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0467-104">構文</span><span class="sxs-lookup"><span data-stu-id="f0467-104">Syntax</span></span>  
  
```  
HRESULT IsArrayClass(  
    [in]  ClassID        classId,  
    [out] CorElementType *pBaseElemType,  
    [out] ClassID        *pBaseClassId,  
    [out] ULONG          *pcRank);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f0467-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f0467-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="f0467-106">[in]調査するクラスの ID。</span><span class="sxs-lookup"><span data-stu-id="f0467-106">[in] The ID of the class to be examined.</span></span>  
  
 `pBaseElemType`  
 <span data-ttu-id="f0467-107">[out]配列要素の種類を示す CorElementType 列挙型の値へのポインター。</span><span class="sxs-lookup"><span data-stu-id="f0467-107">[out] A pointer to a value of the CorElementType enumeration that indicates the type of the array elements.</span></span>  
  
 `pBaseClassId`  
 <span data-ttu-id="f0467-108">[out]使用可能な場合は、配列の要素のクラス ID へのポインター。</span><span class="sxs-lookup"><span data-stu-id="f0467-108">[out] A pointer to the class ID of the array elements, when available.</span></span>  
  
 `pcRank`  
 <span data-ttu-id="f0467-109">[out]配列のランク (次元の数では、) を示す整数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="f0467-109">[out] A pointer to an integer that indicates the rank (that is, number of dimensions) of the array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f0467-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="f0467-110">Remarks</span></span>  
 <span data-ttu-id="f0467-111">指定したクラスが、配列クラスの場合、`IsArrayClass`メソッドは、S_OK HRESULT と null 以外の出力パラメーターに値を返します。</span><span class="sxs-lookup"><span data-stu-id="f0467-111">If the specified class is an array class, the `IsArrayClass` method returns an S_OK HRESULT and values for any non-null output parameters.</span></span> <span data-ttu-id="f0467-112">それ以外の場合、S_FALSE を返します。</span><span class="sxs-lookup"><span data-stu-id="f0467-112">Otherwise, it returns S_FALSE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0467-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="f0467-113">Requirements</span></span>  
 <span data-ttu-id="f0467-114">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0467-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0467-115">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f0467-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f0467-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f0467-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f0467-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0467-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0467-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="f0467-118">See also</span></span>

- [<span data-ttu-id="f0467-119">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f0467-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
