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
ms.openlocfilehash: b6e26d1538cab30db66e887aee89b8fbae501bdb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177008"
---
# <a name="icorprofilerobjectenumnext-method"></a><span data-ttu-id="518fa-102">ICorProfilerObjectEnum::Next メソッド</span><span class="sxs-lookup"><span data-stu-id="518fa-102">ICorProfilerObjectEnum::Next Method</span></span>
<span data-ttu-id="518fa-103">シーケンス内の列挙子の現在位置から始まる、連続するオブジェクトのコレクションから、指定された数の連続したオブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="518fa-103">Gets the specified number of contiguous objects from a sequential collection of objects, starting at the enumerator's current position in the sequence.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="518fa-104">構文</span><span class="sxs-lookup"><span data-stu-id="518fa-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG                    celt,  
    [out, size_is(celt), length_is(*pceltFetched)]
        ObjectID                  objects[],  
    [out] ULONG                   *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="518fa-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="518fa-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="518fa-106">[in] 取得するオブジェクトの数。</span><span class="sxs-lookup"><span data-stu-id="518fa-106">[in] The number of objects to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="518fa-107">[アウト]取得したオブジェクト`ObjectID`を表す値の配列。</span><span class="sxs-lookup"><span data-stu-id="518fa-107">[out] An array of `ObjectID` values, each of which represents a retrieved object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="518fa-108">[out] `objects` 配列で実際に返されるモジュールの数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="518fa-108">[out] A pointer to the number of elements actually returned in the `objects` array.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="518fa-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="518fa-109">Requirements</span></span>  
 <span data-ttu-id="518fa-110">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="518fa-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="518fa-111">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="518fa-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="518fa-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="518fa-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="518fa-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="518fa-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="518fa-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="518fa-114">See also</span></span>

- [<span data-ttu-id="518fa-115">ICorProfilerObjectEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="518fa-115">ICorProfilerObjectEnum Interface</span></span>](icorprofilerobjectenum-interface.md)
