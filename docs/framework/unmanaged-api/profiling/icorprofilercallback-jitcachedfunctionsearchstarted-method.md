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
ms.openlocfilehash: 01989812b85cf98aedfd8855bee7b2dfbfd375f4
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790055"
---
# <a name="icorprofilercallbackjitcachedfunctionsearchstarted-method"></a><span data-ttu-id="ff8d9-102">ICorProfilerCallback::JITCachedFunctionSearchStarted メソッド</span><span class="sxs-lookup"><span data-stu-id="ff8d9-102">ICorProfilerCallback::JITCachedFunctionSearchStarted Method</span></span>
<span data-ttu-id="ff8d9-103">以前にネイティブイメージジェネレーター (Ngen.exe) を使用してコンパイルされた関数に対して検索が開始されたことをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="ff8d9-103">Notifies the profiler that a search has started for a function that was compiled previously using the Native Image Generator (NGen.exe).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff8d9-104">構文</span><span class="sxs-lookup"><span data-stu-id="ff8d9-104">Syntax</span></span>  
  
```cpp  
HRESULT JITCachedFunctionSearchStarted(  
    [in]  FunctionID functionId,  
    [out] BOOL *pbUseCachedFunction);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ff8d9-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ff8d9-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="ff8d9-106">\[] 検索を実行する関数の ID です。</span><span class="sxs-lookup"><span data-stu-id="ff8d9-106">\[in] The ID of the function for which the search is being performed.</span></span>

- `pbUseCachedFunction`

  <span data-ttu-id="ff8d9-107">\[out] `true` キャッシュされたバージョンの関数を実行エンジンが使用する必要がある場合 (使用可能な場合)、それ以外の場合は `false`。</span><span class="sxs-lookup"><span data-stu-id="ff8d9-107">\[out] `true` if the execution engine should use the cached version of a function (if available); otherwise `false`.</span></span> <span data-ttu-id="ff8d9-108">値が `false`場合、実行エンジンは、JIT コンパイルされていないバージョンを使用するのではなく、関数を JIT コンパイルします。</span><span class="sxs-lookup"><span data-stu-id="ff8d9-108">If the value is `false`, the execution engine JIT-compiles the function instead of using a version that is not JIT-compiled.</span></span>

## <a name="remarks"></a><span data-ttu-id="ff8d9-109">コメント</span><span class="sxs-lookup"><span data-stu-id="ff8d9-109">Remarks</span></span>  
 <span data-ttu-id="ff8d9-110">.NET Framework バージョン2.0 では、通常の NGen イメージのすべての関数に対して `JITCachedFunctionSearchStarted` および[ICorProfilerCallback:: JITCachedFunctionSearchFinished メソッド](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcachedfunctionsearchfinished-method.md)のコールバックは行われません。</span><span class="sxs-lookup"><span data-stu-id="ff8d9-110">In the .NET Framework version 2.0, the `JITCachedFunctionSearchStarted` and [ICorProfilerCallback::JITCachedFunctionSearchFinished Method](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcachedfunctionsearchfinished-method.md) callbacks will not be made for all functions in regular NGen images.</span></span> <span data-ttu-id="ff8d9-111">プロファイル用に最適化された NGen イメージのみが、イメージ内のすべての関数のコールバックを生成します。</span><span class="sxs-lookup"><span data-stu-id="ff8d9-111">Only NGen images optimized for a profile will generate callbacks for all functions in the image.</span></span> <span data-ttu-id="ff8d9-112">ただし、オーバーヘッドが増加するため、プロファイラーは、これらのコールバックを使用して just-in-time (JIT) コンパイルを強制的に実行する場合にのみ、プロファイラーで最適化された NGen イメージを要求する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff8d9-112">However, due to the additional overhead, a profiler should request profiler-optimized NGen images only if it intends to use these callbacks to force a function to be compiled just-in-time (JIT).</span></span> <span data-ttu-id="ff8d9-113">それ以外の場合、プロファイラーは関数情報を収集するためにレイジー戦略を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff8d9-113">Otherwise, the profiler should use a lazy strategy for gathering function information.</span></span>  
  
 <span data-ttu-id="ff8d9-114">プロファイラーは、プロファイルされたアプリケーションの複数のスレッドが同時に同じメソッドを呼び出す場合をサポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff8d9-114">Profilers must support cases where multiple threads of a profiled application are calling the same method simultaneously.</span></span> <span data-ttu-id="ff8d9-115">たとえば、スレッド A は `JITCachedFunctionSearchStarted` を呼び出し、プロファイラーは JIT コンパイルを強制するために*pbUseCachedFunction*を FALSE に設定することによって応答します。</span><span class="sxs-lookup"><span data-stu-id="ff8d9-115">For example, thread A calls `JITCachedFunctionSearchStarted` and the profiler responds by setting *pbUseCachedFunction*to FALSE to force JIT compilation.</span></span> <span data-ttu-id="ff8d9-116">次に、スレッド A は[ICorProfilerCallback:: JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md)と[ICorProfilerCallback:: JITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md)を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="ff8d9-116">Thread A then calls [ICorProfilerCallback::JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md) and [ICorProfilerCallback::JITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md).</span></span>  
  
 <span data-ttu-id="ff8d9-117">ここで、スレッド B は同じ関数の `JITCachedFunctionSearchStarted` を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="ff8d9-117">Now thread B calls `JITCachedFunctionSearchStarted` for the same function.</span></span> <span data-ttu-id="ff8d9-118">プロファイラーは、関数を JIT コンパイルすることを意図していましたが、プロファイラーは2番目のコールバックを受け取ります。これは、プロファイラーが `JITCachedFunctionSearchStarted`へのスレッド A の呼び出しに応答する前に、スレッド B がコールバックを送信するためです。</span><span class="sxs-lookup"><span data-stu-id="ff8d9-118">Even though the profiler has stated its intention to JIT-compile the function, the profiler receives the second callback because thread B sends the callback before the profiler has responded to thread A's call to `JITCachedFunctionSearchStarted`.</span></span> <span data-ttu-id="ff8d9-119">スレッドが呼び出しを行う順序は、スレッドがどのようにスケジュールされているかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="ff8d9-119">The order in which the threads make calls depends on how the threads are scheduled.</span></span>  
  
 <span data-ttu-id="ff8d9-120">プロファイラーは、重複コールバックを受信するときに、`pbUseCachedFunction` によって参照される値を、重複するすべてのコールバックについて同じ値に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff8d9-120">When the profiler receives duplicate callbacks, it must set the value referenced by `pbUseCachedFunction` to the same value for all the duplicate callbacks.</span></span> <span data-ttu-id="ff8d9-121">つまり、同じ `functionId` 値を使用して `JITCachedFunctionSearchStarted` が複数回呼び出された場合、プロファイラーは毎回同じ応答を返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff8d9-121">That is, when `JITCachedFunctionSearchStarted` is called multiple times with the same `functionId` value, the profiler must respond the same each time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff8d9-122">要件</span><span class="sxs-lookup"><span data-stu-id="ff8d9-122">Requirements</span></span>  
 <span data-ttu-id="ff8d9-123">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ff8d9-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff8d9-124">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ff8d9-124">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ff8d9-125">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ff8d9-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ff8d9-126">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff8d9-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff8d9-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="ff8d9-127">See also</span></span>

- [<span data-ttu-id="ff8d9-128">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ff8d9-128">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
