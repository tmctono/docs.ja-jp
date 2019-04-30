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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9d2d48e5fb070ec0334de579d2e28146177a87b1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62049480"
---
# <a name="icorprofilerinfo4getrejitids-method"></a><span data-ttu-id="04b7a-102">ICorProfilerInfo4::GetReJITIDs メソッド</span><span class="sxs-lookup"><span data-stu-id="04b7a-102">ICorProfilerInfo4::GetReJITIDs Method</span></span>
<span data-ttu-id="04b7a-103">JIT 再コンパイルのすべてのバージョン指定の関数も割り当てられているを識別する Id の配列を返します。</span><span class="sxs-lookup"><span data-stu-id="04b7a-103">Returns an array of IDs that identify all JIT-recompiled versions of the specified function that are still allocated.</span></span> <span data-ttu-id="04b7a-104">これには、後で元に戻されますが (たとえば、元に戻された関数を含むアプリケーション ドメインでは、使用中で) ときに解放されていない関数の JIT 再コンパイルのバージョンが含まれます。</span><span class="sxs-lookup"><span data-stu-id="04b7a-104">This includes JIT-recompiled versions of functions that have been subsequently reverted but not yet freed (for example, when the application domain that contains the reverted function is still in use).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04b7a-105">構文</span><span class="sxs-lookup"><span data-stu-id="04b7a-105">Syntax</span></span>  
  
```  
HRESULT GetReJITIDs (  
     [in]  FunctionID          functionId,  
     [in]  ULONG               cReJitIds,  
     [out] ULONG *             pcReJitIds,  
     [out, size_is(cReJitIds), length_is(*pcReJitIds)]   ReJITID        reJitIds[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="04b7a-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="04b7a-106">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="04b7a-107">[in]`FunctionID`関数インスタンスのバージョンを列挙するのです。</span><span class="sxs-lookup"><span data-stu-id="04b7a-107">[in] The `FunctionID` of the function instance for which to enumerate versions.</span></span>  
  
 `cReJitIds`  
 <span data-ttu-id="04b7a-108">[in]JIT 再コンパイルの Id の割り当ての数、`reJitIds`配列。</span><span class="sxs-lookup"><span data-stu-id="04b7a-108">[in] The number of JIT-recompiled IDs allocated in the `reJitIds` array.</span></span>  
  
 `pcReJitIds`  
 <span data-ttu-id="04b7a-109">[out]実際に JIT 再コンパイルの Id の数。</span><span class="sxs-lookup"><span data-stu-id="04b7a-109">[out] The actual number of JIT-recompiled IDs.</span></span>  
  
 `reJitIds`  
 <span data-ttu-id="04b7a-110">[out]指定した関数の JIT 再コンパイルの Id を含む、呼び出し元が割り当てた配列。</span><span class="sxs-lookup"><span data-stu-id="04b7a-110">[out] A caller-allocated array that will contain the JIT-recompiled IDs for the specified function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="04b7a-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="04b7a-111">Remarks</span></span>  
 <span data-ttu-id="04b7a-112">`GetReJITIDs` 指定された関数のインスタンスのアクティブな JIT 再コンパイルの Id を列挙します。</span><span class="sxs-lookup"><span data-stu-id="04b7a-112">`GetReJITIDs` enumerates the active JIT-recompiled IDs for a given function instance.</span></span> <span data-ttu-id="04b7a-113">他の同時使用状況パターンに従って`ICorProfilerInfo`呼び出し元が割り当てたバッファーを受け取る関数をします。</span><span class="sxs-lookup"><span data-stu-id="04b7a-113">It follows the same usage pattern as other `ICorProfilerInfo` functions that accept caller-allocated buffers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="04b7a-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="04b7a-114">Requirements</span></span>  
 <span data-ttu-id="04b7a-115">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="04b7a-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04b7a-116">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="04b7a-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="04b7a-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="04b7a-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="04b7a-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="04b7a-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04b7a-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="04b7a-119">See also</span></span>

- [<span data-ttu-id="04b7a-120">ICorProfilerInfo4 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="04b7a-120">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
- [<span data-ttu-id="04b7a-121">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="04b7a-121">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="04b7a-122">プロファイル</span><span class="sxs-lookup"><span data-stu-id="04b7a-122">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
