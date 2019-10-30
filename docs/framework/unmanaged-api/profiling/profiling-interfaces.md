---
title: プロファイリングのインターフェイス
ms.date: 04/10/2018
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], profiling
- profiling interfaces [.NET Framework]
- interfaces [.NET Framework profiling]
ms.assetid: d9303db8-e881-4217-91b7-8c7573c8ef9e
ms.openlocfilehash: adc47417265d32d79508af949c118c4d31a83365
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124193"
---
# <a name="profiling-interfaces"></a><span data-ttu-id="198a2-102">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="198a2-102">Profiling Interfaces</span></span>
<span data-ttu-id="198a2-103">ここでは、共通言語ランタイム (CLR) で実行中のプログラムに対してプロファイルを可能にするアンマネージ インターフェイスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="198a2-103">This section describes the unmanaged interfaces that enable you to profile a program that is being executed by the common language runtime (CLR).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="198a2-104">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="198a2-104">In This Section</span></span>  
 [<span data-ttu-id="198a2-105">ICLRProfiling インターフェイス</span><span class="sxs-lookup"><span data-stu-id="198a2-105">ICLRProfiling Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-interface.md)  
 <span data-ttu-id="198a2-106">[Attachprofiler](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-attachprofiler-method.md)メソッドを提供します。これにより、実行中のプロセスにプロファイラーをアタッチできます。</span><span class="sxs-lookup"><span data-stu-id="198a2-106">Provides the [AttachProfiler](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-attachprofiler-method.md) method, which enables a profiler to attach to a running process.</span></span>  
  
 [<span data-ttu-id="198a2-107">ICorProfilerAssemblyReferenceProvider インターフェイス</span><span class="sxs-lookup"><span data-stu-id="198a2-107">ICorProfilerAssemblyReferenceProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md)  
 <span data-ttu-id="198a2-108">プロファイラーが[ICorProfilerCallback:: ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)コールバックに追加するアセンブリ参照を CLR に通知できるようにします。</span><span class="sxs-lookup"><span data-stu-id="198a2-108">Enables the profiler to inform the CLR of assembly references that the profiler will add in the [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>  
  
 [<span data-ttu-id="198a2-109">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="198a2-109">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 <span data-ttu-id="198a2-110">プロファイラーがサブスクライブしたイベントが発生したときにコード プロファイラーに通知するために、CLR が使用するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="198a2-110">Provides methods that are used by the CLR to notify a code profiler when the events to which the profiler has subscribed occur.</span></span>  
  
 [<span data-ttu-id="198a2-111">ICorProfilerCallback2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="198a2-111">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)  
 <span data-ttu-id="198a2-112">.NET Framework 2.0 以降でサポートされるコールバックによって、`ICorProfilerCallback` インターフェイスを拡張します。</span><span class="sxs-lookup"><span data-stu-id="198a2-112">Extends the `ICorProfilerCallback` interface with callbacks supported in the .NET Framework 2.0 and later versions.</span></span>  
  
 [<span data-ttu-id="198a2-113">ICorProfilerCallback3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="198a2-113">ICorProfilerCallback3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-interface.md)  
 <span data-ttu-id="198a2-114">CLR がプロファイラーにアタッチとデタッチの状態情報を伝えるために使用するコールバック メソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="198a2-114">Provides callback methods that the CLR uses to communicate attach and detach state information to the profiler.</span></span>  
  
 [<span data-ttu-id="198a2-115">ICorProfilerCallback4 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="198a2-115">ICorProfilerCallback4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)  
 <span data-ttu-id="198a2-116">プロファイラーと情報をやりとりするために CLR が使用するコールバック メソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="198a2-116">Provides callback methods that the CLR uses to communicate information to the profiler.</span></span>  
  
 [<span data-ttu-id="198a2-117">ICorProfilerCallback5 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="198a2-117">ICorProfilerCallback5 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-interface.md)  
 <span data-ttu-id="198a2-118">ガベージ コレクションのルートによって参照されるオブジェクトの遷移的なクロージャを識別するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="198a2-118">Provides a method that identifies the transitive closure of objects referenced by garbage collection roots.</span></span>  
  
 [<span data-ttu-id="198a2-119">ICorProfilerCallback6 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="198a2-119">ICorProfilerCallback6 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-interface.md)  
 <span data-ttu-id="198a2-120">CLR が プロファイラーに対して、アセンブリがロード中であることを通知するために使用するコールバック メソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="198a2-120">Provides a callback method that the CLR uses to notify a profiler that an assembly is loading.</span></span>  
  
 [<span data-ttu-id="198a2-121">ICorProfilerCallback7 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="198a2-121">ICorProfilerCallback7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-interface.md)  
 <span data-ttu-id="198a2-122">メモリ内モジュールに関連付けられているシンボルストリームが更新されたことをプロファイラーに通知するために共通言語ランタイムが使用するコールバックメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="198a2-122">Provides a callback method that the common language runtime uses to notify the profiler that the symbol stream associated with an in-memory module is updated.</span></span>  

[<span data-ttu-id="198a2-123">ICorProfilerCallback8 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="198a2-123">ICorProfilerCallback8 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback8-interface.md)  
<span data-ttu-id="198a2-124">動的メソッドの JIT コンパイルが開始および終了したことをプロファイラーに通知するために共通言語ランタイムが使用するコールバックメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="198a2-124">Provides callback methods that the common language runtime uses to notify the profiler that JIT compilation of a dynamic method has started and finished.</span></span>

[<span data-ttu-id="198a2-125">ICorProfilerCallback9 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="198a2-125">ICorProfilerCallback9 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback9-interface.md)  
<span data-ttu-id="198a2-126">動的メソッドがガベージコレクションされ、その後アンロードされることをプロファイラーに通知するために共通言語ランタイムが使用するコールバックメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="198a2-126">Provides a callback method that the common language runtime uses to notify the profiler that a dynamic method is garbage collected and subsequently unloaded.</span></span>

 [<span data-ttu-id="198a2-127">ICorProfilerFunctionControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="198a2-127">ICorProfilerFunctionControl Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md)  
 <span data-ttu-id="198a2-128">コード プロファイラーが CLR と通信できるようにするためのメソッドを提供します。これは特定のメソッドを再コンパイルするときに、JIT コンパイラーがどのようにしてコードを生成するかを制御するためのものです。</span><span class="sxs-lookup"><span data-stu-id="198a2-128">Provides methods that allow a code profiler to communicate with the CLR to control how the JIT compiler should generate code when recompiling a specific method.</span></span>  
  
 [<span data-ttu-id="198a2-129">ICorProfilerFunctionEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="198a2-129">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)  
 <span data-ttu-id="198a2-130">CLR で関数のコレクションを順番に反復処理するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="198a2-130">Provides methods to sequentially iterate through a collection of functions in the CLR.</span></span>  
  
 [<span data-ttu-id="198a2-131">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="198a2-131">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 <span data-ttu-id="198a2-132">コード プロファイラーが、イベントの監視および情報の要求を制御するために CLR との通信で使用するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="198a2-132">Provides methods for use by code profilers to communicate with the CLR to control event monitoring and request information.</span></span>  
  
 [<span data-ttu-id="198a2-133">ICorProfilerInfo2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="198a2-133">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)  
 <span data-ttu-id="198a2-134">.NET Framework 2.0 以降でサポートされるメソッドによって、`ICorProfilerInfo` インターフェイスを拡張します。</span><span class="sxs-lookup"><span data-stu-id="198a2-134">Extends the `ICorProfilerInfo` interface with methods supported in the .NET Framework 2.0 and later versions.</span></span>  
  
 [<span data-ttu-id="198a2-135">ICorProfilerInfo3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="198a2-135">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 <span data-ttu-id="198a2-136">.NET Framework 4 以降のバージョンでサポートされているメソッドを使用して、`ICorProfilerInfo2` インターフェイスを拡張します。</span><span class="sxs-lookup"><span data-stu-id="198a2-136">Extends the `ICorProfilerInfo2` interface with methods supported in the .NET Framework 4 and later versions.</span></span>  
  
 [<span data-ttu-id="198a2-137">ICorProfilerInfo4 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="198a2-137">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)  
 <span data-ttu-id="198a2-138">コード プロファイラーが、イベントの監視および情報の要求を制御するために CLR との通信で使用するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="198a2-138">Provides methods that code profilers use to communicate with the CLR to control event monitoring and to request information.</span></span>  
  
 [<span data-ttu-id="198a2-139">ICorProfilerInfo5 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="198a2-139">ICorProfilerInfo5 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md)  
 <span data-ttu-id="198a2-140">コード プロファイラーが、イベントの監視を制御するために CLR との通信で使用するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="198a2-140">Provides methods for use by code profilers to communicate with the CLR to control event monitoring.</span></span>  
  
 [<span data-ttu-id="198a2-141">ICorProfilerInfo6 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="198a2-141">ICorProfilerInfo6 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md)  
 <span data-ttu-id="198a2-142">特定の NGen モジュールに属し、特定のメソッドの本体にインライン化されているすべてのメソッドに列挙子を提供します。</span><span class="sxs-lookup"><span data-stu-id="198a2-142">Provides an enumerator to all the methods that belong to a given NGen module and that are inlined in the body of a given method.</span></span>  
  
 [<span data-ttu-id="198a2-143">ICorProfilerInfo7 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="198a2-143">ICorProfilerInfo7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)  
 <span data-ttu-id="198a2-144">新しく定義されたメタデータをモジュールに適用し、メモリ内シンボルストリームへのアクセスを提供するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="198a2-144">Provides a method to apply newly defined metadata to a module and that provides access to an in-memory symbol stream.</span></span>  
  
 [<span data-ttu-id="198a2-145">ICorProfilerModuleEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="198a2-145">ICorProfilerModuleEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md)  
 <span data-ttu-id="198a2-146">アプリケーションまたはプロファイラーによってロードされたモジュールのコレクションを順番に反復処理するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="198a2-146">Provides methods to sequentially iterate through a collection of modules loaded by the application or the profiler.</span></span>  
  
 [<span data-ttu-id="198a2-147">ICorProfilerObjectEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="198a2-147">ICorProfilerObjectEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md)  
 <span data-ttu-id="198a2-148">[Ngen.exe (ネイティブイメージジェネレーター)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md)によって生成される固定されたオブジェクトのコレクションを順番に反復処理するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="198a2-148">Provides methods to sequentially iterate through a collection of frozen objects that are generated by [Ngen.exe (Native Image Generator)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md).</span></span>  
  
 [<span data-ttu-id="198a2-149">ICorProfilerThreadEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="198a2-149">ICorProfilerThreadEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)  
 <span data-ttu-id="198a2-150">CLR でスレッドのコレクションを順番に反復処理するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="198a2-150">Provides methods to sequentially iterate through a collection of threads in the CLR.</span></span>  
  
 [<span data-ttu-id="198a2-151">IMethodMalloc インターフェイス</span><span class="sxs-lookup"><span data-stu-id="198a2-151">IMethodMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-interface.md)  
 <span data-ttu-id="198a2-152">新しい Microsoft 中間言語 (MSIL) 関数の本体にメモリを割り当てるための[Alloc](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-alloc-method.md)メソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="198a2-152">Provides the [Alloc](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-alloc-method.md) method to allocate memory for a new Microsoft intermediate language (MSIL) function body.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="198a2-153">関連項目</span><span class="sxs-lookup"><span data-stu-id="198a2-153">Related Sections</span></span>  
 [<span data-ttu-id="198a2-154">プロファイルの概要</span><span class="sxs-lookup"><span data-stu-id="198a2-154">Profiling Overview</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-overview.md)  
  
 [<span data-ttu-id="198a2-155">グローバル静的関数のプロファイル</span><span class="sxs-lookup"><span data-stu-id="198a2-155">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)  
  
 [<span data-ttu-id="198a2-156">列挙型のプロファイリング</span><span class="sxs-lookup"><span data-stu-id="198a2-156">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)  
  
 [<span data-ttu-id="198a2-157">構造体のプロファイリング</span><span class="sxs-lookup"><span data-stu-id="198a2-157">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
