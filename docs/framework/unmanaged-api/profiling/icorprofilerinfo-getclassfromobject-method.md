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
ms.openlocfilehash: a5573765486112a83f5ea7cc9258447692f72166
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76864069"
---
# <a name="icorprofilerinfogetclassfromobject-method"></a><span data-ttu-id="22abd-102">ICorProfilerInfo::GetClassFromObject メソッド</span><span class="sxs-lookup"><span data-stu-id="22abd-102">ICorProfilerInfo::GetClassFromObject Method</span></span>
<span data-ttu-id="22abd-103">`ObjectID`指定されたオブジェクトの `ClassID` を取得します。</span><span class="sxs-lookup"><span data-stu-id="22abd-103">Gets the `ClassID` of an object, given its `ObjectID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22abd-104">構文</span><span class="sxs-lookup"><span data-stu-id="22abd-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClassFromObject(  
    [in]  ObjectID objectId,  
    [out] ClassID *pClassId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="22abd-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="22abd-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="22abd-106">から`ClassID`を取得する対象のオブジェクトの ID。</span><span class="sxs-lookup"><span data-stu-id="22abd-106">[in] The ID of the object for which to get the `ClassID`.</span></span>  
  
 `pClassId`  
 <span data-ttu-id="22abd-107">入出力返された `ClassID`へのポインター。</span><span class="sxs-lookup"><span data-stu-id="22abd-107">[out] A pointer to the returned `ClassID`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="22abd-108">コメント</span><span class="sxs-lookup"><span data-stu-id="22abd-108">Remarks</span></span>  
 <span data-ttu-id="22abd-109">Null `pClassId` は、`objectId` にアンロード中の型があることを示します。</span><span class="sxs-lookup"><span data-stu-id="22abd-109">A null `pClassId` indicates that `objectId` has a type that is unloading.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22abd-110">要件</span><span class="sxs-lookup"><span data-stu-id="22abd-110">Requirements</span></span>  
 <span data-ttu-id="22abd-111">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="22abd-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22abd-112">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="22abd-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="22abd-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="22abd-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="22abd-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22abd-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22abd-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="22abd-115">See also</span></span>

- [<span data-ttu-id="22abd-116">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="22abd-116">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
