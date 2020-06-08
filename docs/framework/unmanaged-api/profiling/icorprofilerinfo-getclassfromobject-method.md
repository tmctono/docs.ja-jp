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
ms.openlocfilehash: 613267549329d2f48dcd18ae341e47538e414ac0
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84498532"
---
# <a name="icorprofilerinfogetclassfromobject-method"></a><span data-ttu-id="6bd26-102">ICorProfilerInfo::GetClassFromObject メソッド</span><span class="sxs-lookup"><span data-stu-id="6bd26-102">ICorProfilerInfo::GetClassFromObject Method</span></span>
<span data-ttu-id="6bd26-103">を指定して、オブジェクトのを取得し `ClassID` `ObjectID` ます。</span><span class="sxs-lookup"><span data-stu-id="6bd26-103">Gets the `ClassID` of an object, given its `ObjectID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6bd26-104">構文</span><span class="sxs-lookup"><span data-stu-id="6bd26-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClassFromObject(  
    [in]  ObjectID objectId,  
    [out] ClassID *pClassId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6bd26-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6bd26-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="6bd26-106">からを取得する対象のオブジェクトの ID `ClassID` 。</span><span class="sxs-lookup"><span data-stu-id="6bd26-106">[in] The ID of the object for which to get the `ClassID`.</span></span>  
  
 `pClassId`  
 <span data-ttu-id="6bd26-107">入出力返されたへのポインター `ClassID` 。</span><span class="sxs-lookup"><span data-stu-id="6bd26-107">[out] A pointer to the returned `ClassID`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6bd26-108">解説</span><span class="sxs-lookup"><span data-stu-id="6bd26-108">Remarks</span></span>  
 <span data-ttu-id="6bd26-109">Null は、が `pClassId` `objectId` アンロード中の型を持つことを示します。</span><span class="sxs-lookup"><span data-stu-id="6bd26-109">A null `pClassId` indicates that `objectId` has a type that is unloading.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6bd26-110">要件</span><span class="sxs-lookup"><span data-stu-id="6bd26-110">Requirements</span></span>  
 <span data-ttu-id="6bd26-111">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6bd26-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6bd26-112">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6bd26-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6bd26-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6bd26-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6bd26-114">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6bd26-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bd26-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="6bd26-115">See also</span></span>

- [<span data-ttu-id="6bd26-116">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6bd26-116">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
