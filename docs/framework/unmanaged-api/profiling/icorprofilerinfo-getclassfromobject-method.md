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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59189548"
---
# <a name="icorprofilerinfogetclassfromobject-method"></a><span data-ttu-id="789fe-102">ICorProfilerInfo::GetClassFromObject メソッド</span><span class="sxs-lookup"><span data-stu-id="789fe-102">ICorProfilerInfo::GetClassFromObject Method</span></span>
<span data-ttu-id="789fe-103">取得、 `ClassID` 、指定したオブジェクトの`ObjectID`します。</span><span class="sxs-lookup"><span data-stu-id="789fe-103">Gets the `ClassID` of an object, given its `ObjectID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="789fe-104">構文</span><span class="sxs-lookup"><span data-stu-id="789fe-104">Syntax</span></span>  
  
```  
HRESULT GetClassFromObject(  
    [in]  ObjectID objectId,  
    [out] ClassID *pClassId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="789fe-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="789fe-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="789fe-106">[in]取得する対象のオブジェクトの ID、`ClassID`します。</span><span class="sxs-lookup"><span data-stu-id="789fe-106">[in] The ID of the object for which to get the `ClassID`.</span></span>  
  
 `pClassId`  
 <span data-ttu-id="789fe-107">[out]返されたポインター`ClassID`します。</span><span class="sxs-lookup"><span data-stu-id="789fe-107">[out] A pointer to the returned `ClassID`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="789fe-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="789fe-108">Remarks</span></span>  
 <span data-ttu-id="789fe-109">Null`pClassId`ことを示します`objectId`型をアンロードしていますがあります。</span><span class="sxs-lookup"><span data-stu-id="789fe-109">A null `pClassId` indicates that `objectId` has a type that is unloading.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="789fe-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="789fe-110">Requirements</span></span>  
 <span data-ttu-id="789fe-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="789fe-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="789fe-112">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="789fe-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="789fe-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="789fe-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="789fe-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="789fe-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="789fe-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="789fe-115">See also</span></span>

- [<span data-ttu-id="789fe-116">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="789fe-116">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
