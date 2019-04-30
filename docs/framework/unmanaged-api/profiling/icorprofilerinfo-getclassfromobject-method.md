---
title: ICorProfilerInfo::GetClassFromObject メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetClassFromObject
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetClassFromObject
helpviewer_keywords:
- GetClassFromObject method [.NET Framework profiling]
- ICorProfilerInfo::GetClassFromObject method [.NET Framework profiling]
ms.assetid: b97493fb-713e-49d5-a73e-5688b2ad0700
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 81afb9b40269b04a59c54636c7e88c1f67189593
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62041718"
---
# <a name="icorprofilerinfogetclassfromobject-method"></a><span data-ttu-id="bf762-102">ICorProfilerInfo::GetClassFromObject メソッド</span><span class="sxs-lookup"><span data-stu-id="bf762-102">ICorProfilerInfo::GetClassFromObject Method</span></span>
<span data-ttu-id="bf762-103">取得、 `ClassID` 、指定したオブジェクトの`ObjectID`します。</span><span class="sxs-lookup"><span data-stu-id="bf762-103">Gets the `ClassID` of an object, given its `ObjectID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf762-104">構文</span><span class="sxs-lookup"><span data-stu-id="bf762-104">Syntax</span></span>  
  
```  
HRESULT GetClassFromObject(  
    [in]  ObjectID objectId,  
    [out] ClassID *pClassId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bf762-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="bf762-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="bf762-106">[in]取得する対象のオブジェクトの ID、`ClassID`します。</span><span class="sxs-lookup"><span data-stu-id="bf762-106">[in] The ID of the object for which to get the `ClassID`.</span></span>  
  
 `pClassId`  
 <span data-ttu-id="bf762-107">[out]返されたポインター`ClassID`します。</span><span class="sxs-lookup"><span data-stu-id="bf762-107">[out] A pointer to the returned `ClassID`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bf762-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="bf762-108">Remarks</span></span>  
 <span data-ttu-id="bf762-109">Null`pClassId`ことを示します`objectId`型をアンロードしていますがあります。</span><span class="sxs-lookup"><span data-stu-id="bf762-109">A null `pClassId` indicates that `objectId` has a type that is unloading.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf762-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="bf762-110">Requirements</span></span>  
 <span data-ttu-id="bf762-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bf762-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf762-112">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bf762-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bf762-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bf762-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bf762-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bf762-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf762-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="bf762-115">See also</span></span>

- [<span data-ttu-id="bf762-116">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bf762-116">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
