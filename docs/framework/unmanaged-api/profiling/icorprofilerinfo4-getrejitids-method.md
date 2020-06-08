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
ms.openlocfilehash: ba15440df79dded95a8afa9438657d064e167f36
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84495971"
---
# <a name="icorprofilerinfo4getrejitids-method"></a><span data-ttu-id="532d6-102">ICorProfilerInfo4::GetReJITIDs メソッド</span><span class="sxs-lookup"><span data-stu-id="532d6-102">ICorProfilerInfo4::GetReJITIDs Method</span></span>
<span data-ttu-id="532d6-103">割り当てられている指定された関数のすべての JIT 再コンパイルバージョンを識別する Id の配列を返します。</span><span class="sxs-lookup"><span data-stu-id="532d6-103">Returns an array of IDs that identify all JIT-recompiled versions of the specified function that are still allocated.</span></span> <span data-ttu-id="532d6-104">これには、後で元に戻されたがまだ解放されていない関数の JIT 再コンパイルバージョンが含まれます (たとえば、元に戻された関数を含むアプリケーションドメインがまだ使用されている場合など)。</span><span class="sxs-lookup"><span data-stu-id="532d6-104">This includes JIT-recompiled versions of functions that have been subsequently reverted but not yet freed (for example, when the application domain that contains the reverted function is still in use).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="532d6-105">構文</span><span class="sxs-lookup"><span data-stu-id="532d6-105">Syntax</span></span>  
  
```cpp
HRESULT GetReJITIDs (  
     [in]  FunctionID          functionId,  
     [in]  ULONG               cReJitIds,  
     [out] ULONG *             pcReJitIds,  
     [out, size_is(cReJitIds), length_is(*pcReJitIds)]   ReJITID        reJitIds[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="532d6-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="532d6-106">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="532d6-107">から`FunctionID`バージョンを列挙する対象の関数インスタンスの。</span><span class="sxs-lookup"><span data-stu-id="532d6-107">[in] The `FunctionID` of the function instance for which to enumerate versions.</span></span>  
  
 `cReJitIds`  
 <span data-ttu-id="532d6-108">から配列に割り当てられた JIT 再コンパイル済み Id の数 `reJitIds` 。</span><span class="sxs-lookup"><span data-stu-id="532d6-108">[in] The number of JIT-recompiled IDs allocated in the `reJitIds` array.</span></span>  
  
 `pcReJitIds`  
 <span data-ttu-id="532d6-109">入出力JIT 再コンパイルされた Id の実際の数。</span><span class="sxs-lookup"><span data-stu-id="532d6-109">[out] The actual number of JIT-recompiled IDs.</span></span>  
  
 `reJitIds`  
 <span data-ttu-id="532d6-110">入出力指定した関数の JIT 再コンパイルされた Id を格納する、呼び出し元が割り当てた配列。</span><span class="sxs-lookup"><span data-stu-id="532d6-110">[out] A caller-allocated array that will contain the JIT-recompiled IDs for the specified function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="532d6-111">解説</span><span class="sxs-lookup"><span data-stu-id="532d6-111">Remarks</span></span>  
 <span data-ttu-id="532d6-112">`GetReJITIDs`指定された関数インスタンスのアクティブな JIT 再コンパイル済み Id を列挙します。</span><span class="sxs-lookup"><span data-stu-id="532d6-112">`GetReJITIDs` enumerates the active JIT-recompiled IDs for a given function instance.</span></span> <span data-ttu-id="532d6-113">これは、 `ICorProfilerInfo` 呼び出し元が割り当てたバッファーを受け入れる他の関数と同じ使用パターンに従います。</span><span class="sxs-lookup"><span data-stu-id="532d6-113">It follows the same usage pattern as other `ICorProfilerInfo` functions that accept caller-allocated buffers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="532d6-114">要件</span><span class="sxs-lookup"><span data-stu-id="532d6-114">Requirements</span></span>  
 <span data-ttu-id="532d6-115">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="532d6-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="532d6-116">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="532d6-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="532d6-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="532d6-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="532d6-118">**.NET Framework のバージョン:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="532d6-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="532d6-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="532d6-119">See also</span></span>

- [<span data-ttu-id="532d6-120">ICorProfilerInfo4 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="532d6-120">ICorProfilerInfo4 Interface</span></span>](icorprofilerinfo4-interface.md)
- [<span data-ttu-id="532d6-121">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="532d6-121">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="532d6-122">プロファイル</span><span class="sxs-lookup"><span data-stu-id="532d6-122">Profiling</span></span>](index.md)
