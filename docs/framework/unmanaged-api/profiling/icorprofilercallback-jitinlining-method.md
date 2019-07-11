---
title: ICorProfilerCallback::JITInlining メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITInlining
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITInlining
helpviewer_keywords:
- JITInlining method [.NET Framework profiling]
- ICorProfilerCallback::JITInlining method [.NET Framework profiling]
ms.assetid: c2f45801-dd38-4b78-b6b7-64397dc73f83
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 82af06837ead9a00923c23d4ce145015308fbbf7
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782801"
---
# <a name="icorprofilercallbackjitinlining-method"></a><span data-ttu-id="8778d-102">ICorProfilerCallback::JITInlining メソッド</span><span class="sxs-lookup"><span data-stu-id="8778d-102">ICorProfilerCallback::JITInlining Method</span></span>
<span data-ttu-id="8778d-103">別の関数に合わせて関数を挿入しようとしています-イン タイム (JIT) コンパイラがプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="8778d-103">Notifies the profiler that the just-in-time (JIT) compiler is about to insert a function in line with another function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8778d-104">構文</span><span class="sxs-lookup"><span data-stu-id="8778d-104">Syntax</span></span>  
  
```cpp  
HRESULT JITInlining(  
    [in]  FunctionID callerId,  
    [in]  FunctionID calleeId,  
    [out] BOOL      *pfShouldInline);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8778d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8778d-105">Parameters</span></span>  
 `callerId`  
 <span data-ttu-id="8778d-106">[in]先の関数の ID、`calleeId`関数が挿入されます。</span><span class="sxs-lookup"><span data-stu-id="8778d-106">[in] The ID of the function into which the `calleeId` function will be inserted.</span></span>  
  
 `calleeId`  
 <span data-ttu-id="8778d-107">[in]挿入する関数の ID。</span><span class="sxs-lookup"><span data-stu-id="8778d-107">[in] The ID of the function to be inserted.</span></span>  
  
 `pfShouldInline`  
 <span data-ttu-id="8778d-108">[out]`true`発生挿入を許可する場合は、`false`します。</span><span class="sxs-lookup"><span data-stu-id="8778d-108">[out] `true` to allow the insertion to occur; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8778d-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="8778d-109">Remarks</span></span>  
 <span data-ttu-id="8778d-110">プロファイラーを設定できます`pfShouldInline`に`false`を防ぐために、`calleeId`関数に挿入されてから、`callerId`関数。</span><span class="sxs-lookup"><span data-stu-id="8778d-110">The profiler can set `pfShouldInline` to `false` to prevent the `calleeId` function from being inserted into the `callerId` function.</span></span> <span data-ttu-id="8778d-111">また、プロファイラー グローバルに無効にできますインライン挿入の COR_PRF_DISABLE_INLINING 値を使用して、 [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md)列挙体。</span><span class="sxs-lookup"><span data-stu-id="8778d-111">Also, the profiler can globally disable inline insertion by using the COR_PRF_DISABLE_INLINING value of the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
 <span data-ttu-id="8778d-112">挿入関数をインラインでは、出入りに関するイベントは発生しません。</span><span class="sxs-lookup"><span data-stu-id="8778d-112">Functions inserted inline do not raise events for entering or leaving.</span></span> <span data-ttu-id="8778d-113">そのため、プロファイラーを設定する必要があります`pfShouldInline`に`false`正確なコールグラフを生成するためにします。</span><span class="sxs-lookup"><span data-stu-id="8778d-113">Therefore, the profiler must set `pfShouldInline` to `false` in order to produce an accurate callgraph.</span></span> <span data-ttu-id="8778d-114">設定`pfShouldInline`に`false`インライン挿入は通常速度が向上し、挿入されたメソッドの別の JIT コンパイル イベントの数が減るため、パフォーマンスに影響します。</span><span class="sxs-lookup"><span data-stu-id="8778d-114">Setting `pfShouldInline` to `false` will affect performance, because inline insertion typically increases speed and reduces the number of separate JIT compilation events for the inserted method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8778d-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="8778d-115">Requirements</span></span>  
 <span data-ttu-id="8778d-116">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8778d-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8778d-117">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8778d-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8778d-118">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8778d-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8778d-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8778d-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8778d-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="8778d-120">See also</span></span>

- [<span data-ttu-id="8778d-121">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8778d-121">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
