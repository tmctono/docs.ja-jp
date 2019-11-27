---
title: ICorProfilerInfo4::GetReJITIDs メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.GetReJITIDs
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::GetReJITIDs
helpviewer_keywords:
- GetReJITIDs method, ICorProfilerInfo4 interface [.NET Framework profiling]
- ICorProfilerInfo4::GetReJITIDs method [.NET Framework profiling]
ms.assetid: 634ac28c-a5b7-4fc3-af84-256c24ca8177
topic_type:
- apiref
ms.openlocfilehash: f6d26abba649b608858fde8beaac750600493869
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74442856"
---
# <a name="icorprofilerinfo4getrejitids-method"></a><span data-ttu-id="c2194-102">ICorProfilerInfo4::GetReJITIDs メソッド</span><span class="sxs-lookup"><span data-stu-id="c2194-102">ICorProfilerInfo4::GetReJITIDs Method</span></span>
<span data-ttu-id="c2194-103">割り当てられている指定された関数のすべての JIT 再コンパイルバージョンを識別する Id の配列を返します。</span><span class="sxs-lookup"><span data-stu-id="c2194-103">Returns an array of IDs that identify all JIT-recompiled versions of the specified function that are still allocated.</span></span> <span data-ttu-id="c2194-104">これには、後で元に戻されたがまだ解放されていない関数の JIT 再コンパイルバージョンが含まれます (たとえば、元に戻された関数を含むアプリケーションドメインがまだ使用されている場合など)。</span><span class="sxs-lookup"><span data-stu-id="c2194-104">This includes JIT-recompiled versions of functions that have been subsequently reverted but not yet freed (for example, when the application domain that contains the reverted function is still in use).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2194-105">構文</span><span class="sxs-lookup"><span data-stu-id="c2194-105">Syntax</span></span>  
  
```cpp
HRESULT GetReJITIDs (  
     [in]  FunctionID          functionId,  
     [in]  ULONG               cReJitIds,  
     [out] ULONG *             pcReJitIds,  
     [out, size_is(cReJitIds), length_is(*pcReJitIds)]   ReJITID        reJitIds[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c2194-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c2194-106">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="c2194-107">からバージョンを列挙する関数インスタンスの `FunctionID`。</span><span class="sxs-lookup"><span data-stu-id="c2194-107">[in] The `FunctionID` of the function instance for which to enumerate versions.</span></span>  
  
 `cReJitIds`  
 <span data-ttu-id="c2194-108">から`reJitIds` 配列に割り当てられた JIT 再コンパイルされた Id の数。</span><span class="sxs-lookup"><span data-stu-id="c2194-108">[in] The number of JIT-recompiled IDs allocated in the `reJitIds` array.</span></span>  
  
 `pcReJitIds`  
 <span data-ttu-id="c2194-109">入出力JIT 再コンパイルされた Id の実際の数。</span><span class="sxs-lookup"><span data-stu-id="c2194-109">[out] The actual number of JIT-recompiled IDs.</span></span>  
  
 `reJitIds`  
 <span data-ttu-id="c2194-110">入出力指定した関数の JIT 再コンパイルされた Id を格納する、呼び出し元が割り当てた配列。</span><span class="sxs-lookup"><span data-stu-id="c2194-110">[out] A caller-allocated array that will contain the JIT-recompiled IDs for the specified function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c2194-111">コメント</span><span class="sxs-lookup"><span data-stu-id="c2194-111">Remarks</span></span>  
 <span data-ttu-id="c2194-112">`GetReJITIDs` は、指定された関数インスタンスのアクティブな JIT 再コンパイル済み Id を列挙します。</span><span class="sxs-lookup"><span data-stu-id="c2194-112">`GetReJITIDs` enumerates the active JIT-recompiled IDs for a given function instance.</span></span> <span data-ttu-id="c2194-113">これは、呼び出し元が割り当てたバッファーを受け入れる他の `ICorProfilerInfo` 関数と同じ使用パターンに従います。</span><span class="sxs-lookup"><span data-stu-id="c2194-113">It follows the same usage pattern as other `ICorProfilerInfo` functions that accept caller-allocated buffers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2194-114">要件</span><span class="sxs-lookup"><span data-stu-id="c2194-114">Requirements</span></span>  
 <span data-ttu-id="c2194-115">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2194-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2194-116">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c2194-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c2194-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c2194-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c2194-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2194-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2194-119">参照</span><span class="sxs-lookup"><span data-stu-id="c2194-119">See also</span></span>

- [<span data-ttu-id="c2194-120">ICorProfilerInfo4 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c2194-120">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
- [<span data-ttu-id="c2194-121">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="c2194-121">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="c2194-122">プロファイル</span><span class="sxs-lookup"><span data-stu-id="c2194-122">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
