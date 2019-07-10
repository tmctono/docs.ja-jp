---
title: FunctionIDMapper2 関数
ms.date: 03/30/2017
api_name:
- FunctionIDMapper2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionIDMapper2
helpviewer_keywords:
- FunctionIDMapper2 function [.NET Framework profiling]
ms.assetid: 466ad51b-8f0c-41d9-81f7-371aac3374cb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a070d2e863aecf7b13eb59a118848b96d2cccc17
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781305"
---
# <a name="functionidmapper2-function"></a><span data-ttu-id="e82f1-102">FunctionIDMapper2 関数</span><span class="sxs-lookup"><span data-stu-id="e82f1-102">FunctionIDMapper2 Function</span></span>
<span data-ttu-id="e82f1-103">使用される代替 ID に、関数の指定した id 再割り当てされることをプロファイラーに通知、 [FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)、 [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)、および[FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)、または[FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)、 [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)、および[FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)その関数のコールバック。</span><span class="sxs-lookup"><span data-stu-id="e82f1-103">Notifies the profiler that the given identifier of a function may be remapped to an alternative ID to be used in the [FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md), [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md), and [FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md), or[FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md), [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md), and [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) callbacks for that function.</span></span> <span data-ttu-id="e82f1-104">また `FunctionIDMapper2` により、プロファイラーはその関数のコールバックを受信するかどうかを示すことができます。</span><span class="sxs-lookup"><span data-stu-id="e82f1-104">`FunctionIDMapper2` also enables the profiler to indicate whether it wants to receive callbacks for that function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e82f1-105">構文</span><span class="sxs-lookup"><span data-stu-id="e82f1-105">Syntax</span></span>  
  
```cpp  
UINT_PTR __stdcall FunctionIDMapper2 (  
    [in]  FunctionID  funcId,  
    [in]  void * clientData,  
    [out] BOOL       *pbHookFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e82f1-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e82f1-106">Parameters</span></span>  
 `funcId`  
 <span data-ttu-id="e82f1-107">[入力] 再割り当てされる関数識別子。</span><span class="sxs-lookup"><span data-stu-id="e82f1-107">[in] The function identifier to be remapped.</span></span>  
  
 `clientData`  
 <span data-ttu-id="e82f1-108">[入力] ランタイム間のあいまいさを解消するために使用されるデータへのポインター。</span><span class="sxs-lookup"><span data-stu-id="e82f1-108">[in] A pointer to data that is used to disambiguate among runtimes.</span></span>  
  
 `pbHookFunction`  
 <span data-ttu-id="e82f1-109">[出力] 出力プロファイラーが `FunctionEnter3`、`FunctionLeave3`、`FunctionTailcall3`、または  `FunctionEnter3WithInfo`、`FunctionLeave3WithInfo`、`FunctionTailcall3WithInfo` の各コールバックを受信する場合は `true` に設定される値へのポインター。それ以外の場合、この値は  `false` に設定されます。</span><span class="sxs-lookup"><span data-stu-id="e82f1-109">[out] A pointer to a value that the profiler sets to `true` if it wants to receive `FunctionEnter3`, `FunctionLeave3`, and `FunctionTailcall3`, or `FunctionEnter3WithInfo`, `FunctionLeave3WithInfo`, and `FunctionTailcall3WithInfo` callbacks; otherwise, it sets this value to `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e82f1-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="e82f1-110">Return Value</span></span>  
 <span data-ttu-id="e82f1-111">プロファイラーは、実行エンジンが代替関数識別子として使用する値を返します。</span><span class="sxs-lookup"><span data-stu-id="e82f1-111">The profiler returns a value that the execution engine uses as an alternative function identifier.</span></span> <span data-ttu-id="e82f1-112">`false` で `pbHookFunction` を返さない限り、戻り値を null にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="e82f1-112">The return value cannot be null unless `false` is returned in `pbHookFunction`.</span></span> <span data-ttu-id="e82f1-113">これ以外の状況で戻り値を null にすると、プロセスの中止など、予測できない結果が発生します。</span><span class="sxs-lookup"><span data-stu-id="e82f1-113">Otherwise, a null return value produces unpredictable results, including possibly halting the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e82f1-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="e82f1-114">Remarks</span></span>  
 <span data-ttu-id="e82f1-115">このメソッドによって拡張、 [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md)関数クライアント データを渡すために使用される追加パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="e82f1-115">This method extends the [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) function with an additional parameter that is used to pass client data.</span></span> <span data-ttu-id="e82f1-116">クライアント データを使用すると、ランタイム間のあいまいさが解消されます。</span><span class="sxs-lookup"><span data-stu-id="e82f1-116">The client data is used to disambiguate among runtimes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e82f1-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="e82f1-117">Requirements</span></span>  
 <span data-ttu-id="e82f1-118">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e82f1-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e82f1-119">**ヘッダー:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="e82f1-119">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="e82f1-120">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e82f1-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e82f1-121">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e82f1-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e82f1-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="e82f1-122">See also</span></span>

- [<span data-ttu-id="e82f1-123">ICorProfilerInfo::SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="e82f1-123">ICorProfilerInfo::SetFunctionIDMapper</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="e82f1-124">ICorProfilerInfo3::SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="e82f1-124">ICorProfilerInfo3::SetFunctionIDMapper2</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setfunctionidmapper2-method.md)
- [<span data-ttu-id="e82f1-125">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="e82f1-125">FunctionEnter3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)
- [<span data-ttu-id="e82f1-126">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="e82f1-126">FunctionLeave3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)
- [<span data-ttu-id="e82f1-127">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="e82f1-127">FunctionTailcall3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)
- [<span data-ttu-id="e82f1-128">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="e82f1-128">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)
- [<span data-ttu-id="e82f1-129">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="e82f1-129">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)
- [<span data-ttu-id="e82f1-130">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="e82f1-130">FunctionTailcall3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)
- [<span data-ttu-id="e82f1-131">グローバル静的関数のプロファイル</span><span class="sxs-lookup"><span data-stu-id="e82f1-131">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
