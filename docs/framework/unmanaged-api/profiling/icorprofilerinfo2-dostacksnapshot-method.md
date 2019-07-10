---
title: ICorProfilerInfo2::DoStackSnapshot メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.DoStackSnapshot
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::DoStackSnapshot
helpviewer_keywords:
- ICorProfilerInfo2::DoStackSnapshot method [.NET Framework profiling]
- DoStackSnapshot method [.NET Framework profiling]
ms.assetid: 287b11e9-7c52-4a13-ba97-751203fa97f4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 102349461456f971a2fdeaf2783630c1b88dbd6b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778629"
---
# <a name="icorprofilerinfo2dostacksnapshot-method"></a><span data-ttu-id="aca32-102">ICorProfilerInfo2::DoStackSnapshot メソッド</span><span class="sxs-lookup"><span data-stu-id="aca32-102">ICorProfilerInfo2::DoStackSnapshot Method</span></span>
<span data-ttu-id="aca32-103">指定されたスレッドのスタックでマネージド フレームをについて説明し、コールバックを通じてプロファイラーに情報を送信します。</span><span class="sxs-lookup"><span data-stu-id="aca32-103">Walks the managed frames on the stack for the specified thread, and sends information to the profiler through a callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aca32-104">構文</span><span class="sxs-lookup"><span data-stu-id="aca32-104">Syntax</span></span>  
  
```cpp  
HRESULT DoStackSnapshot(  
    [in] ThreadID thread,  
    [in] StackSnapshotCallback *callback,  
    [in] ULONG32 infoFlags,  
    [in] void *clientData,  
    [in, size_is(contextSize), length_is(contextSize)] BYTE context[],  
    [in] ULONG32 contextSize);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aca32-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="aca32-105">Parameters</span></span>  
 `thread`  
 <span data-ttu-id="aca32-106">[in]対象のスレッドの ID。</span><span class="sxs-lookup"><span data-stu-id="aca32-106">[in] The ID of the target thread.</span></span>  
  
 <span data-ttu-id="aca32-107">Null を渡す`thread`現在のスレッドのスナップショットが生成されます。</span><span class="sxs-lookup"><span data-stu-id="aca32-107">Passing null in `thread` yields a snapshot of the current thread.</span></span> <span data-ttu-id="aca32-108">場合、`ThreadID`の別のスレッドが渡される、共通言語ランタイム (CLR) スレッドを中断します、スナップショットの実行が再開されます。</span><span class="sxs-lookup"><span data-stu-id="aca32-108">If a `ThreadID` of a different thread is passed, the common language runtime (CLR) suspends that thread, performs the snapshot, and resumes.</span></span>  
  
 `callback`  
 <span data-ttu-id="aca32-109">[in]実装へのポインター、 [StackSnapshotCallback](../../../../docs/framework/unmanaged-api/profiling/stacksnapshotcallback-function.md)メソッドで、各マネージ フレームとフレームの非管理対象の各実行に関する情報をプロファイラーを提供する、CLR によって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="aca32-109">[in] A pointer to the implementation of the [StackSnapshotCallback](../../../../docs/framework/unmanaged-api/profiling/stacksnapshotcallback-function.md) method, which is called by the CLR to provide the profiler with information on each managed frame and each run of unmanaged frames.</span></span>  
  
 <span data-ttu-id="aca32-110">`StackSnapshotCallback`メソッド プロファイラー ライターによって実装されます。</span><span class="sxs-lookup"><span data-stu-id="aca32-110">The `StackSnapshotCallback` method is implemented by the profiler writer.</span></span>  
  
 `infoFlags`  
 <span data-ttu-id="aca32-111">[in]値、 [COR_PRF_SNAPSHOT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-snapshot-info-enumeration.md)によって各フレームを渡されるデータの量を指定する列挙体`StackSnapshotCallback`します。</span><span class="sxs-lookup"><span data-stu-id="aca32-111">[in] A value of the [COR_PRF_SNAPSHOT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-snapshot-info-enumeration.md) enumeration, which specifies the amount of data to be passed back for each frame by `StackSnapshotCallback`.</span></span>  
  
 `clientData`  
 <span data-ttu-id="aca32-112">[in]直接渡されるクライアントのデータへのポインター、`StackSnapshotCallback`コールバック関数。</span><span class="sxs-lookup"><span data-stu-id="aca32-112">[in] A pointer to the client data, which is passed straight through to the `StackSnapshotCallback` callback function.</span></span>  
  
 `context`  
 <span data-ttu-id="aca32-113">[in]Win32 へのポインター`CONTEXT`構造体は、スタック ウォークをシードするために使用します。</span><span class="sxs-lookup"><span data-stu-id="aca32-113">[in] A pointer to a Win32 `CONTEXT` structure, which is used to seed the stack walk.</span></span> <span data-ttu-id="aca32-114">Win32`CONTEXT`構造は、CPU レジスタの値が含まれています、特定の時点で、CPU の状態を表します。</span><span class="sxs-lookup"><span data-stu-id="aca32-114">The Win32 `CONTEXT` structure contains values of the CPU registers and represents the state of the CPU at a particular moment in time.</span></span>  
  
 <span data-ttu-id="aca32-115">シードにより、CLR がスタックの先頭がアンマネージ ヘルパー コードの場合、スタック ウォークを開始する場所を決定します。それ以外の場合、シードは無視されます。</span><span class="sxs-lookup"><span data-stu-id="aca32-115">The seed helps the CLR determine where to begin the stack walk, if the top of the stack is unmanaged helper code; otherwise, the seed is ignored.</span></span> <span data-ttu-id="aca32-116">非同期のウォークのシードを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aca32-116">A seed must be supplied for an asynchronous walk.</span></span> <span data-ttu-id="aca32-117">同期のウォークを実行している場合、シードの必要はありません。</span><span class="sxs-lookup"><span data-stu-id="aca32-117">If you are doing a synchronous walk, no seed is necessary.</span></span>  
  
 <span data-ttu-id="aca32-118">`context`パラメーターは COR_PRF_SNAPSHOT_CONTEXT フラグが渡された場合にのみ有効ですが、`infoFlags`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="aca32-118">The `context` parameter is valid only if the COR_PRF_SNAPSHOT_CONTEXT flag was passed in the `infoFlags` parameter.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="aca32-119">[in]サイズ、`CONTEXT`によって参照されている構造体、`context`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="aca32-119">[in] The size of the `CONTEXT` structure, which is referenced by the `context` parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aca32-120">Remarks</span><span class="sxs-lookup"><span data-stu-id="aca32-120">Remarks</span></span>  
 <span data-ttu-id="aca32-121">Null を渡す`thread`現在のスレッドのスナップショットが生成されます。</span><span class="sxs-lookup"><span data-stu-id="aca32-121">Passing null for `thread` yields a snapshot of the current thread.</span></span> <span data-ttu-id="aca32-122">時に対象のスレッドが中断されている場合にのみ、他のスレッドのスナップショットを作成できます。</span><span class="sxs-lookup"><span data-stu-id="aca32-122">Snapshots can be taken of other threads only if the target thread is suspended at the time.</span></span>  
  
 <span data-ttu-id="aca32-123">プロファイラーは、スタック ウォークが、ときに呼び出す`DoStackSnapshot`します。</span><span class="sxs-lookup"><span data-stu-id="aca32-123">When the profiler wants to walk the stack, it calls `DoStackSnapshot`.</span></span> <span data-ttu-id="aca32-124">CLR がその呼び出しから戻る前に呼び出し、`StackSnapshotCallback`を複数回 1 回ごとに管理されているフレーム (または非管理対象のフレームの実行)、スタックにします。</span><span class="sxs-lookup"><span data-stu-id="aca32-124">Before the CLR returns from that call, it calls your `StackSnapshotCallback` several times, once for each managed frame (or run of unmanaged frames) on the stack.</span></span> <span data-ttu-id="aca32-125">非管理対象のフレームが発生したときを自分でに説明する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aca32-125">When unmanaged frames are encountered, you must walk them yourself.</span></span>  
  
 <span data-ttu-id="aca32-126">スタックが走査され、順序が逆の方法、フレームがスタックにプッシュされた: 最後 (最後にプッシュされた) 最初に、メイン (最初にプッシュされた) フレームをリーフします。</span><span class="sxs-lookup"><span data-stu-id="aca32-126">The order in which the stack is walked is the reverse of how the frames were pushed onto the stack: leaf (last-pushed) frame first, main (first-pushed) frame last.</span></span>  
  
 <span data-ttu-id="aca32-127">プロファイラーでマネージ スタックをプログラムする方法の詳細については、次を参照してください。 [、.NET Framework 2.0 における Profiler スタック ウォーク。基本、そしてその向こう](https://go.microsoft.com/fwlink/?LinkId=73638)します。</span><span class="sxs-lookup"><span data-stu-id="aca32-127">For more information about how to program the profiler to walk managed stacks, see [Profiler Stack Walking in the .NET Framework 2.0: Basics and Beyond](https://go.microsoft.com/fwlink/?LinkId=73638).</span></span>  
  
 <span data-ttu-id="aca32-128">スタック ウォークには、次のセクションで説明するよう同期または非同期でを指定できます。</span><span class="sxs-lookup"><span data-stu-id="aca32-128">A stack walk can be synchronous or asynchronous, as explained in the following sections.</span></span>  
  
## <a name="synchronous-stack-walk"></a><span data-ttu-id="aca32-129">同期スタック ウォーク</span><span class="sxs-lookup"><span data-stu-id="aca32-129">Synchronous Stack Walk</span></span>  
 <span data-ttu-id="aca32-130">同期スタック ウォークは、コールバックへの応答で、現在のスレッドのスタックをウォークします。</span><span class="sxs-lookup"><span data-stu-id="aca32-130">A synchronous stack walk involves walking the stack of the current thread in response to a callback.</span></span> <span data-ttu-id="aca32-131">シード処理または中断は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="aca32-131">It does not require seeding or suspending.</span></span>  
  
 <span data-ttu-id="aca32-132">同期を行うときに、プロファイラーのいずれかを呼び出して、CLR への応答を呼び出す[ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) (または[ICorProfilerCallback2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)) メソッドを呼び出す`DoStackSnapshot`のスタック ウォーク、現在のスレッド。</span><span class="sxs-lookup"><span data-stu-id="aca32-132">You make a synchronous call when, in response to the CLR calling one of your profiler's [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) (or [ICorProfilerCallback2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)) methods, you call `DoStackSnapshot` to walk the stack of the current thread.</span></span> <span data-ttu-id="aca32-133">これは、スタックがどのように通知でなどを表示する場合に便利です[icorprofilercallback::objectallocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="aca32-133">This is useful when you want to see what the stack looks like at a notification such as [ICorProfilerCallback::ObjectAllocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md).</span></span> <span data-ttu-id="aca32-134">呼び出すだけで`DoStackSnapshot`内から、`ICorProfilerCallback`で null を渡す場合、メソッド、`context`と`thread`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="aca32-134">You just call `DoStackSnapshot` from within your `ICorProfilerCallback` method, passing null in the `context` and `thread` parameters.</span></span>  
  
## <a name="asynchronous-stack-walk"></a><span data-ttu-id="aca32-135">非同期のスタック ウォーク</span><span class="sxs-lookup"><span data-stu-id="aca32-135">Asynchronous Stack Walk</span></span>  
 <span data-ttu-id="aca32-136">別のスレッドのスタックや、応答が現在のスレッドの命令ポインターをハイジャックして、コールバックではなく、現在のスレッドのスタックをウォーク、非同期のスタック ウォークする必要があります。</span><span class="sxs-lookup"><span data-stu-id="aca32-136">An asynchronous stack walk entails walking the stack of a different thread, or walking the stack of the current thread, not in response to a callback, but by hijacking the current thread's instruction pointer.</span></span> <span data-ttu-id="aca32-137">非同期のチュートリアルでは、アンマネージ コード、プラットフォームの一部でない場合は、スタックの一番上のシードの呼び出し (PInvoke) が必要です、COM の呼び出しでも CLR 自体でヘルパー コード。</span><span class="sxs-lookup"><span data-stu-id="aca32-137">An asynchronous walk requires a seed if the top of the stack is unmanaged code that is not part of a platform invoke (PInvoke) or COM call, but helper code in the CLR itself.</span></span> <span data-ttu-id="aca32-138">たとえば、ジャストイン タイム (JIT) コンパイルやガベージ コレクションを実行するコードは、ヘルパー コードです。</span><span class="sxs-lookup"><span data-stu-id="aca32-138">For example, code that does just-in-time (JIT) compiling or garbage collection is helper code.</span></span>  
  
 <span data-ttu-id="aca32-139">直接対象のスレッドを中断することによって、シードを取得し、自分で、最上位に表示されるまでにマネージ フレーム スタックを走査します。</span><span class="sxs-lookup"><span data-stu-id="aca32-139">You obtain a seed by directly suspending the target thread and walking its stack yourself, until you find the topmost managed frame.</span></span> <span data-ttu-id="aca32-140">対象のスレッドが中断された後は、対象のスレッドの現在のレジスタのコンテキストを取得します。</span><span class="sxs-lookup"><span data-stu-id="aca32-140">After the target thread is suspended, get the target thread's current register context.</span></span> <span data-ttu-id="aca32-141">次に、呼び出すことでレジスタのコンテキストがアンマネージ コードを指すかどうかを決定[icorprofilerinfo::getfunctionfromip](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getfunctionfromip-method.md) -返された場合、 `FunctionID` 0 に等しい、フレームがアンマネージ コード。</span><span class="sxs-lookup"><span data-stu-id="aca32-141">Next, determine whether the register context points to unmanaged code by calling [ICorProfilerInfo::GetFunctionFromIP](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getfunctionfromip-method.md) — if it returns a `FunctionID` equal to zero, the frame is unmanaged code.</span></span> <span data-ttu-id="aca32-142">最初のマネージ フレームに到達し、そのフレームのレジスタのコンテキストに基づき、シードのコンテキストを計算するまで、スタックについて説明します。</span><span class="sxs-lookup"><span data-stu-id="aca32-142">Now, walk the stack until you reach the first managed frame, and then calculate the seed context based on the register context for that frame.</span></span>  
  
 <span data-ttu-id="aca32-143">呼び出す`DoStackSnapshot`非同期スタック ウォークを開始する、シードのコンテキストを使用します。</span><span class="sxs-lookup"><span data-stu-id="aca32-143">Call `DoStackSnapshot` with your seed context to begin the asynchronous stack walk.</span></span> <span data-ttu-id="aca32-144">シードを指定しない場合`DoStackSnapshot`スタックの上部にあるマネージ フレームをスキップする場合があり、その結果は、スタック ウォークが不完全です。</span><span class="sxs-lookup"><span data-stu-id="aca32-144">If you do not supply a seed, `DoStackSnapshot` might skip managed frames at the top of the stack and, consequently, will give you an incomplete stack walk.</span></span> <span data-ttu-id="aca32-145">シードを指定した場合は、JIT コンパイルまたはネイティブ イメージ ジェネレーター (Ngen.exe) を指している必要があります-生成されたコードです。それ以外の場合、 `DoStackSnapshot` CORPROF_E_STACKSNAPSHOT_UNMANAGED_CTX エラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="aca32-145">If you do supply a seed, it must point to JIT-compiled or Native Image Generator (Ngen.exe)-generated code; otherwise, `DoStackSnapshot` returns the failure code, CORPROF_E_STACKSNAPSHOT_UNMANAGED_CTX.</span></span>  
  
 <span data-ttu-id="aca32-146">非同期のスタック ウォークを簡単にデッドロックが発生するか、アクセス違反が次のガイドラインに従わない場合、します。</span><span class="sxs-lookup"><span data-stu-id="aca32-146">Asynchronous stack walks can easily cause deadlocks or access violations, unless you follow these guidelines:</span></span>  
  
- <span data-ttu-id="aca32-147">直接のスレッドを中断する場合は、マネージ コードを実行しないが、スレッドが別のスレッドを中断できますを注意してください。</span><span class="sxs-lookup"><span data-stu-id="aca32-147">When you directly suspend threads, remember that only a thread that has never run managed code can suspend another thread.</span></span>  
  
- <span data-ttu-id="aca32-148">常にブロック、 [icorprofilercallback::threaddestroyed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threaddestroyed-method.md)スレッドのスタック ウォークが完了するまでのコールバック。</span><span class="sxs-lookup"><span data-stu-id="aca32-148">Always block in your [ICorProfilerCallback::ThreadDestroyed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threaddestroyed-method.md) callback until that thread's stack walk is complete.</span></span>  
  
- <span data-ttu-id="aca32-149">プロファイラーがガベージ コレクションをトリガーできる CLR 関数を呼び出すときに、ロックを保持しないでください。</span><span class="sxs-lookup"><span data-stu-id="aca32-149">Do not hold a lock while your profiler calls into a CLR function that can trigger a garbage collection.</span></span> <span data-ttu-id="aca32-150">つまり、所有元のスレッドがガベージ コレクションをトリガーする呼び出しを行う場合、ロックを保持しないでください。</span><span class="sxs-lookup"><span data-stu-id="aca32-150">That is, do not hold a lock if the owning thread might make a call that triggers a garbage collection.</span></span>  
  
 <span data-ttu-id="aca32-151">またがデッドロックの危険性を呼び出す場合`DoStackSnapshot`プロファイラーが別のターゲット スレッドのスタックを学ぶことができるように作成したスレッドから。</span><span class="sxs-lookup"><span data-stu-id="aca32-151">There is also a risk of deadlock if you call `DoStackSnapshot` from a thread that your profiler has created so that you can walk the stack of a separate target thread.</span></span> <span data-ttu-id="aca32-152">最初に作成したスレッドが特定`ICorProfilerInfo*`メソッド (含む`DoStackSnapshot`)、CLR はスレッドごと、そのスレッドで CLR 固有の初期化を実行します。</span><span class="sxs-lookup"><span data-stu-id="aca32-152">The first time the thread you created enters certain `ICorProfilerInfo*` methods (including `DoStackSnapshot`), the CLR will perform per-thread, CLR-specific initialization on that thread.</span></span> <span data-ttu-id="aca32-153">プロファイラーには、スタック ウォーク、しようとして対象のスレッドが中断されている場合、およびその対象スレッドは、このスレッドごとの初期化を実行するために必要なロックを所有するが発生した場合は、デッドロックが発生します。</span><span class="sxs-lookup"><span data-stu-id="aca32-153">If your profiler has suspended the target thread whose stack you are trying to walk, and if that target thread happened to own a lock necessary for performing this per-thread initialization, a deadlock will occur.</span></span> <span data-ttu-id="aca32-154">このデッドロックを回避することを最初の呼び出しに`DoStackSnapshot`からプロファイラーが作成したスレッドについて説明しますが、別が対象に、スレッドは、まず対象のスレッドを中断しないようにします。</span><span class="sxs-lookup"><span data-stu-id="aca32-154">To avoid this deadlock, make an initial call into `DoStackSnapshot` from your profiler-created thread to walk a separate target thread, but do not suspend the target thread first.</span></span> <span data-ttu-id="aca32-155">この最初の呼び出しにより、スレッドごとの初期化がデッドロックなしで完了できます。</span><span class="sxs-lookup"><span data-stu-id="aca32-155">This initial call ensures that the per-thread initialization can complete without deadlock.</span></span> <span data-ttu-id="aca32-156">場合`DoStackSnapshot`が成功し、少なくとも 1 つのフレームを報告その後、対象のスレッドと呼び出しを中断するプロファイラーが作成したスレッドの安全ななります`DoStackSnapshot`ターゲット スレッドのスタック ウォークします。</span><span class="sxs-lookup"><span data-stu-id="aca32-156">If `DoStackSnapshot` succeeds and reports at least one frame, after that point, it will be safe for that profiler-created thread to suspend any target thread and call `DoStackSnapshot` to walk the stack of that target thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aca32-157">必要条件</span><span class="sxs-lookup"><span data-stu-id="aca32-157">Requirements</span></span>  
 <span data-ttu-id="aca32-158">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="aca32-158">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aca32-159">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="aca32-159">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="aca32-160">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="aca32-160">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="aca32-161">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aca32-161">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aca32-162">関連項目</span><span class="sxs-lookup"><span data-stu-id="aca32-162">See also</span></span>

- [<span data-ttu-id="aca32-163">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="aca32-163">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="aca32-164">ICorProfilerInfo2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="aca32-164">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
