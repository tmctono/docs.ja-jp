---
title: ICorProfilerObjectEnum::Next メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerObjectEnum.Next
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerObjectEnum::Next
helpviewer_keywords:
- Next method, ICorProfilerObjectEnum interface [.NET Framework profiling]
- ICorProfilerObjectEnum::Next method [.NET Framework profiling]
ms.assetid: b420433c-5ebe-4986-bba1-97902e6db819
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 221752b537cd3a890ad646290a64a7022692f625
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61597259"
---
# <a name="icorprofilerobjectenumnext-method"></a><span data-ttu-id="7e19d-102">ICorProfilerObjectEnum::Next メソッド</span><span class="sxs-lookup"><span data-stu-id="7e19d-102">ICorProfilerObjectEnum::Next Method</span></span>
<span data-ttu-id="7e19d-103">列挙子の現在の位置から、オブジェクトのシーケンシャル コレクションから指定した数の隣接するオブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="7e19d-103">Gets the specified number of contiguous objects from a sequential collection of objects, starting at the enumerator's current position in the sequence.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e19d-104">構文</span><span class="sxs-lookup"><span data-stu-id="7e19d-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG                    celt,  
    [out, size_is(celt), length_is(*pceltFetched)]    
        ObjectID                  objects[],  
    [out] ULONG                   *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7e19d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7e19d-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="7e19d-106">[in] 取得するオブジェクトの数。</span><span class="sxs-lookup"><span data-stu-id="7e19d-106">[in] The number of objects to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="7e19d-107">[out]配列の`ObjectID`取得したオブジェクトを表す値。</span><span class="sxs-lookup"><span data-stu-id="7e19d-107">[out] An array of `ObjectID` values, each of which represents a retrieved object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="7e19d-108">[out] `objects` 配列で実際に返されるモジュールの数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="7e19d-108">[out] A pointer to the number of elements actually returned in the `objects` array.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e19d-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="7e19d-109">Requirements</span></span>  
 <span data-ttu-id="7e19d-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7e19d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e19d-111">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7e19d-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7e19d-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7e19d-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7e19d-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e19d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e19d-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="7e19d-114">See also</span></span>

- [<span data-ttu-id="7e19d-115">ICorProfilerObjectEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7e19d-115">ICorProfilerObjectEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md)
