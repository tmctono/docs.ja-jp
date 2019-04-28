---
title: ICorProfilerCallback::JITCachedFunctionSearchStarted メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITCachedFunctionSearchStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITCachedFunctionSearchStarted
helpviewer_keywords:
- JITCachedFunctionSearchStarted method [.NET Framework profiling]
- ICorProfilerCallback::JITCachedFunctionSearchStarted method [.NET Framework profiling]
ms.assetid: 5cba642c-0d80-48ee-889d-198c5044d821
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3550f4da497574ea5076766ad201e9431af52e4c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61598034"
---
# <a name="icorprofilercallbackjitcachedfunctionsearchstarted-method"></a><span data-ttu-id="e848d-102">ICorProfilerCallback::JITCachedFunctionSearchStarted メソッド</span><span class="sxs-lookup"><span data-stu-id="e848d-102">ICorProfilerCallback::JITCachedFunctionSearchStarted Method</span></span>
<span data-ttu-id="e848d-103">ネイティブ イメージ ジェネレーター (NGen.exe) を使用して以前にコンパイルされた関数の検索が開始されたことをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="e848d-103">Notifies the profiler that a search has started for a function that was compiled previously using the Native Image Generator (NGen.exe).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e848d-104">構文</span><span class="sxs-lookup"><span data-stu-id="e848d-104">Syntax</span></span>  
  
```  
HRESULT JITCachedFunctionSearchStarted(  
    [in]  FunctionID functionId,  
    [out] BOOL *pbUseCachedFunction);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e848d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e848d-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="e848d-106">[in]検索が実行されている関数の ID。</span><span class="sxs-lookup"><span data-stu-id="e848d-106">[in] The ID of the function for which the search is being performed.</span></span>  
  
 `pbUseCachedFunction`  
 <span data-ttu-id="e848d-107">[out]`true`場合 (該当する場合)、実行エンジンはキャッシュされたバージョンの関数を使用する必要があります。 そうしないと`false`します。</span><span class="sxs-lookup"><span data-stu-id="e848d-107">[out] `true` if the execution engine should use the cached version of a function (if available); otherwise `false`.</span></span> <span data-ttu-id="e848d-108">値が場合`false`、実行エンジンは JIT コンパイル、JIT コンパイルではないバージョンを使用する代わりに関数。</span><span class="sxs-lookup"><span data-stu-id="e848d-108">If the value is `false`, the execution engine JIT-compiles the function instead of using a version that is not JIT-compiled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e848d-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="e848d-109">Remarks</span></span>  
 <span data-ttu-id="e848d-110">.NET Framework version 2.0 で、`JITCachedFunctionSearchStarted`と[icorprofilercallback::jitcachedfunctionsearchfinished メソッド](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcachedfunctionsearchfinished-method.md)正規の NGen イメージのすべての関数のコールバックは行われません。</span><span class="sxs-lookup"><span data-stu-id="e848d-110">In the .NET Framework version 2.0, the `JITCachedFunctionSearchStarted` and [ICorProfilerCallback::JITCachedFunctionSearchFinished Method](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcachedfunctionsearchfinished-method.md) callbacks will not be made for all functions in regular NGen images.</span></span> <span data-ttu-id="e848d-111">プロファイル用に最適化された NGen イメージだけでは、イメージのすべての関数のコールバックが生成されます。</span><span class="sxs-lookup"><span data-stu-id="e848d-111">Only NGen images optimized for a profile will generate callbacks for all functions in the image.</span></span> <span data-ttu-id="e848d-112">ただし、追加のオーバーヘッドが原因で、プロファイラー NGen イメージのプロファイラーを最適化する必要があります要求した場合、関数のコンパイル済みの just-in-time (JIT) を強制的にこれらのコールバックを使用する場合にのみにします。</span><span class="sxs-lookup"><span data-stu-id="e848d-112">However, due to the additional overhead, a profiler should request profiler-optimized NGen images only if it intends to use these callbacks to force a function to be compiled just-in-time (JIT).</span></span> <span data-ttu-id="e848d-113">それ以外の場合、プロファイラーは、関数の情報を収集するため、遅延の戦略を使用してください。</span><span class="sxs-lookup"><span data-stu-id="e848d-113">Otherwise, the profiler should use a lazy strategy for gathering function information.</span></span>  
  
 <span data-ttu-id="e848d-114">プロファイラーは、プロファイリング対象のアプリケーションの複数のスレッドが、同じメソッドを同時に呼び出す場合をサポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e848d-114">Profilers must support cases where multiple threads of a profiled application are calling the same method simultaneously.</span></span> <span data-ttu-id="e848d-115">たとえば、スレッド A が呼び出す`JITCachedFunctionSearchStarted`し応答する状態を設定して、プロファイラー *pbUseCachedFunction*に JIT コンパイルを強制する場合は FALSE。</span><span class="sxs-lookup"><span data-stu-id="e848d-115">For example, thread A calls `JITCachedFunctionSearchStarted` and the profiler responds by setting *pbUseCachedFunction*to FALSE to force JIT compilation.</span></span> <span data-ttu-id="e848d-116">スレッド A はその呼び出し[icorprofilercallback::jitcompilationstarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md)と[icorprofilercallback::jitcompilationfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="e848d-116">Thread A then calls [ICorProfilerCallback::JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md) and [ICorProfilerCallback::JITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md).</span></span>  
  
 <span data-ttu-id="e848d-117">スレッド B の呼び出しのようになりました`JITCachedFunctionSearchStarted`同じ関数。</span><span class="sxs-lookup"><span data-stu-id="e848d-117">Now thread B calls `JITCachedFunctionSearchStarted` for the same function.</span></span> <span data-ttu-id="e848d-118">プロファイラーがスレッド B が、プロファイラーがスレッドの呼び出し前に、コールバックを送信するために、2 番目のコールバックを受け取る場合でも、プロファイラーが、関数の JIT コンパイルする意向を説明すると、`JITCachedFunctionSearchStarted`します。</span><span class="sxs-lookup"><span data-stu-id="e848d-118">Even though the profiler has stated its intention to JIT-compile the function, the profiler receives the second callback because thread B sends the callback before the profiler has responded to thread A's call to `JITCachedFunctionSearchStarted`.</span></span> <span data-ttu-id="e848d-119">これで、スレッドは呼び出しを行う順序は、スレッドをスケジュールする方法に依存します。</span><span class="sxs-lookup"><span data-stu-id="e848d-119">The order in which the threads make calls depends on how the threads are scheduled.</span></span>  
  
 <span data-ttu-id="e848d-120">によって参照される値を設定する必要があります、プロファイラーは、重複するコールバックを受信すると`pbUseCachedFunction`重複するすべてのコールバックの同じ値にします。</span><span class="sxs-lookup"><span data-stu-id="e848d-120">When the profiler receives duplicate callbacks, it must set the value referenced by `pbUseCachedFunction` to the same value for all the duplicate callbacks.</span></span> <span data-ttu-id="e848d-121">つまり、`JITCachedFunctionSearchStarted`同じで複数回呼び出された`functionId`値、プロファイラー対応する必要が同じたび。</span><span class="sxs-lookup"><span data-stu-id="e848d-121">That is, when `JITCachedFunctionSearchStarted` is called multiple times with the same `functionId` value, the profiler must respond the same each time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e848d-122">必要条件</span><span class="sxs-lookup"><span data-stu-id="e848d-122">Requirements</span></span>  
 <span data-ttu-id="e848d-123">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e848d-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e848d-124">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e848d-124">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e848d-125">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e848d-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e848d-126">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e848d-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e848d-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="e848d-127">See also</span></span>

- [<span data-ttu-id="e848d-128">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e848d-128">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
