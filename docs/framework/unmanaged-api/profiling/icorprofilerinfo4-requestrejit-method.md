---
title: ICorProfilerInfo4::RequestReJIT メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.RequestReJIT
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::RequestReJIT
helpviewer_keywords:
- RequestReJIT method, ICorProfilerInfo4 interface [.NET Framework profiling]
- ICorProfilerInfo4::RequestReJIT method [.NET Framework profiling]
ms.assetid: 781ed736-f30c-4816-920e-3552e36542c6
topic_type:
- apiref
ms.openlocfilehash: eb4d5e1c4efd67914df95868b67ec5cc3fe6139a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74444820"
---
# <a name="icorprofilerinfo4requestrejit-method"></a><span data-ttu-id="81452-102">ICorProfilerInfo4::RequestReJIT メソッド</span><span class="sxs-lookup"><span data-stu-id="81452-102">ICorProfilerInfo4::RequestReJIT Method</span></span>
<span data-ttu-id="81452-103">指定された関数のすべてのインスタンスの JIT 再コンパイルを要求します。</span><span class="sxs-lookup"><span data-stu-id="81452-103">Requests a JIT recompilation of all instances of the specified functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81452-104">構文</span><span class="sxs-lookup"><span data-stu-id="81452-104">Syntax</span></span>  
  
```cpp  
HRESULT RequestReJIT (  
   [in] ULONG    cFunctions,  
   [in, size_is(cFunctions)]  ModuleID    moduleIds[],  
   [in, size_is(cFunctions)]  mdMethodDef methodIds[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="81452-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="81452-105">Parameters</span></span>  
 `cFunctions`  
 <span data-ttu-id="81452-106">[in] 再コンパイルする関数の数。</span><span class="sxs-lookup"><span data-stu-id="81452-106">[in] The number of functions to recompile.</span></span>  
  
 `moduleIds`  
 <span data-ttu-id="81452-107">[in] 再コンパイルする関数を識別する (`moduleId`、`module`) ペアの `methodDef` の部分を指定します。</span><span class="sxs-lookup"><span data-stu-id="81452-107">[in] Specifies the `moduleId` portion of the (`module`, `methodDef`) pairs that identify the functions to be recompiled.</span></span>  
  
 `methodIds`  
 <span data-ttu-id="81452-108">[in] 再コンパイルする関数を識別する (`methodId`、`module`) ペアの `methodDef` の部分を指定します。</span><span class="sxs-lookup"><span data-stu-id="81452-108">[in] Specifies the `methodId` portion of the (`module`, `methodDef`) pairs that identify the functions to be recompiled.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="81452-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="81452-109">Return Value</span></span>  
 <span data-ttu-id="81452-110">このメソッドは、次の特定の HRESULT と、メソッドの失敗を示す HRESULT エラーも返します。</span><span class="sxs-lookup"><span data-stu-id="81452-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="81452-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="81452-111">HRESULT</span></span>|<span data-ttu-id="81452-112">説明</span><span class="sxs-lookup"><span data-stu-id="81452-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="81452-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="81452-113">S_OK</span></span>|<span data-ttu-id="81452-114">すべてのメソッドを JIT 再コンパイル対象としてマークする操作が試行されました。</span><span class="sxs-lookup"><span data-stu-id="81452-114">An attempt was made to mark all the methods for JIT recompilation.</span></span> <span data-ttu-id="81452-115">プロファイラーは、 [ICorProfilerCallback4:: ReJITError](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejiterror-method.md)メソッドを実装して、JIT 再コンパイルのために正常にマークされたメソッドを特定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="81452-115">The profiler must implement the [ICorProfilerCallback4::ReJITError](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejiterror-method.md) method to determine which methods were successfully marked for JIT recompilation.</span></span>|  
|<span data-ttu-id="81452-116">CORPROF_E_CALLBACK4_REQUIRED</span><span class="sxs-lookup"><span data-stu-id="81452-116">CORPROF_E_CALLBACK4_REQUIRED</span></span>|<span data-ttu-id="81452-117">プロファイラーは、この呼び出しがサポートされるように、 [ICorProfilerCallback4](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)インターフェイスを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="81452-117">The profiler must implement the [ICorProfilerCallback4](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md) interface for this call to be supported.</span></span>|  
|<span data-ttu-id="81452-118">CORPROF_E_REJIT_NOT_ENABLED</span><span class="sxs-lookup"><span data-stu-id="81452-118">CORPROF_E_REJIT_NOT_ENABLED</span></span>|<span data-ttu-id="81452-119">JIT 再コンパイルが有効になっていませんでした。</span><span class="sxs-lookup"><span data-stu-id="81452-119">JIT recompilation has not been enabled.</span></span> <span data-ttu-id="81452-120">[ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md)メソッドを使用して `COR_PRF_ENABLE_REJIT` フラグを設定することにより、初期化中に JIT 再コンパイルを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="81452-120">You must enable JIT recompilation during initialization by using the [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) method to set the `COR_PRF_ENABLE_REJIT` flag.</span></span>|  
|<span data-ttu-id="81452-121">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="81452-121">E_INVALIDARG</span></span>|<span data-ttu-id="81452-122">`cFunctions` が0であるか、`moduleIds` または `methodIds` が `NULL`。</span><span class="sxs-lookup"><span data-stu-id="81452-122">`cFunctions` is 0, or `moduleIds` or `methodIds` is `NULL`.</span></span>|  
|||  
|<span data-ttu-id="81452-123">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="81452-123">E_OUTOFMEMORY</span></span>|<span data-ttu-id="81452-124">メモリが不足しているために、CLR は要求を完了できませんでした。</span><span class="sxs-lookup"><span data-stu-id="81452-124">The CLR was unable to complete the request because it ran out of memory.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="81452-125">コメント</span><span class="sxs-lookup"><span data-stu-id="81452-125">Remarks</span></span>  
 <span data-ttu-id="81452-126">指定された一連の関数をこのラインタイムで再コンパイルするため、`RequestReJIT` を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="81452-126">Call `RequestReJIT` to have the runtime recompile a specified set of functions.</span></span> <span data-ttu-id="81452-127">コードプロファイラーは、 [ICorProfilerFunctionControl](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md)インターフェイスを使用して、関数の再コンパイル時に生成されるコードを調整できます。</span><span class="sxs-lookup"><span data-stu-id="81452-127">A code profiler can then use the [ICorProfilerFunctionControl](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md) interface to adjust the code that is generated when the functions are recompiled.</span></span> <span data-ttu-id="81452-128">これは、今後の関数呼び出しにのみ影響し、現在実行中の関数には影響しません。</span><span class="sxs-lookup"><span data-stu-id="81452-128">This does not affect currently executing functions, only future function invocations.</span></span> <span data-ttu-id="81452-129">指定されている関数のいずれかが以前に JIT 再コンパイルされている場合、再コンパイルを要求する操作は、関数を元に戻して再コンパイルする操作と同等です。</span><span class="sxs-lookup"><span data-stu-id="81452-129">If any of the specified functions has previously been JIT-recompiled, requesting a recompilation is equivalent to reverting and recompiling the function.</span></span> <span data-ttu-id="81452-130">可逆性を維持するため、JIT コンパイラは関数の元のバージョンのコンパイル時に、インライン処理の決定のために呼び出し先の元のバージョンだけを考慮します。</span><span class="sxs-lookup"><span data-stu-id="81452-130">To preserve reversibility, when the JIT compiler compiles the original version of a function, it considers only the original versions of its callees for inlining decisions.</span></span> <span data-ttu-id="81452-131">JIT コンパイラは関数の再コンパイル時に、インライン処理のためにその呼び出し先の現行バージョン (再コンパイル バージョンまたは元のバージョン) を考慮します。</span><span class="sxs-lookup"><span data-stu-id="81452-131">When the JIT compiler recompiles a function, it considers the current versions (recompiled or original) of its callees for inlining.</span></span>  
  
 <span data-ttu-id="81452-132">プロファイラーは一般に、プロファイラーが 1 つ以上のメソッドをインストルメント化することを求めるユーザー入力に対応して `RequestReJIT` を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="81452-132">A profiler typically calls `RequestReJIT` in response to user input requesting that the profiler instrument one or more methods.</span></span> <span data-ttu-id="81452-133">`RequestReJIT` は通常、作業の一部を実行するためにランタイムを中断し、ガベージコレクションをトリガーする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="81452-133">`RequestReJIT` typically suspends the runtime in order to do some of its work, and can potentially trigger a garbage collection.</span></span> <span data-ttu-id="81452-134">このためプロファイラーは、現在プロファイラー コールバックを実行している CLR 作成スレッドではなく、以前に作成したスレッドから `RequestReJIT` を呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="81452-134">As such, the profiler should call `RequestReJIT` from a thread it previously created, and not from a CLR-created thread that is currently executing a profiler callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="81452-135">要件</span><span class="sxs-lookup"><span data-stu-id="81452-135">Requirements</span></span>  
 <span data-ttu-id="81452-136">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="81452-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81452-137">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="81452-137">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="81452-138">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="81452-138">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="81452-139">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81452-139">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81452-140">参照</span><span class="sxs-lookup"><span data-stu-id="81452-140">See also</span></span>

- [<span data-ttu-id="81452-141">ICorProfilerInfo4 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="81452-141">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
- [<span data-ttu-id="81452-142">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="81452-142">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="81452-143">プロファイル</span><span class="sxs-lookup"><span data-stu-id="81452-143">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
