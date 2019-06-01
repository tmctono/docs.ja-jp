---
title: プロファイリングのインターフェイス
ms.date: 04/10/2018
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], profiling
- profiling interfaces [.NET Framework]
- interfaces [.NET Framework profiling]
ms.assetid: d9303db8-e881-4217-91b7-8c7573c8ef9e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d97960a43e1d7ce625d96755a7c597a0425d0911
ms.sourcegitcommit: 518e7634b86d3980ec7da5f8c308cc1054daedb7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/01/2019
ms.locfileid: "66457464"
---
# <a name="profiling-interfaces"></a><span data-ttu-id="bfb72-102">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="bfb72-102">Profiling Interfaces</span></span>
<span data-ttu-id="bfb72-103">ここでは、共通言語ランタイム (CLR) で実行中のプログラムに対してプロファイルを可能にするアンマネージ インターフェイスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="bfb72-103">This section describes the unmanaged interfaces that enable you to profile a program that is being executed by the common language runtime (CLR).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bfb72-104">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="bfb72-104">In This Section</span></span>  
 [<span data-ttu-id="bfb72-105">ICLRProfiling インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bfb72-105">ICLRProfiling Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-interface.md)  
 <span data-ttu-id="bfb72-106">提供、 [AttachProfiler](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-attachprofiler-method.md)メソッドで、実行中のプロセスにアタッチするプロファイラーを使用します。</span><span class="sxs-lookup"><span data-stu-id="bfb72-106">Provides the [AttachProfiler](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-attachprofiler-method.md) method, which enables a profiler to attach to a running process.</span></span>  
  
 [<span data-ttu-id="bfb72-107">ICorProfilerAssemblyReferenceProvider インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bfb72-107">ICorProfilerAssemblyReferenceProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md)  
 <span data-ttu-id="bfb72-108">プロファイラーを追加するアセンブリ参照の CLR に通知できるように、 [icorprofilercallback::moduleloadfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)コールバック。</span><span class="sxs-lookup"><span data-stu-id="bfb72-108">Enables the profiler to inform the CLR of assembly references that the profiler will add in the [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>  
  
 [<span data-ttu-id="bfb72-109">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bfb72-109">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 <span data-ttu-id="bfb72-110">プロファイラーがサブスクライブしたイベントが発生したときにコード プロファイラーに通知するために、CLR が使用するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="bfb72-110">Provides methods that are used by the CLR to notify a code profiler when the events to which the profiler has subscribed occur.</span></span>  
  
 [<span data-ttu-id="bfb72-111">ICorProfilerCallback2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bfb72-111">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)  
 <span data-ttu-id="bfb72-112">.NET Framework 2.0 以降でサポートされるコールバックによって、`ICorProfilerCallback` インターフェイスを拡張します。</span><span class="sxs-lookup"><span data-stu-id="bfb72-112">Extends the `ICorProfilerCallback` interface with callbacks supported in the .NET Framework 2.0 and later versions.</span></span>  
  
 [<span data-ttu-id="bfb72-113">ICorProfilerCallback3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bfb72-113">ICorProfilerCallback3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-interface.md)  
 <span data-ttu-id="bfb72-114">CLR がプロファイラーにアタッチとデタッチの状態情報を伝えるために使用するコールバック メソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="bfb72-114">Provides callback methods that the CLR uses to communicate attach and detach state information to the profiler.</span></span>  
  
 [<span data-ttu-id="bfb72-115">ICorProfilerCallback4 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bfb72-115">ICorProfilerCallback4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)  
 <span data-ttu-id="bfb72-116">プロファイラーと情報をやりとりするために CLR が使用するコールバック メソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="bfb72-116">Provides callback methods that the CLR uses to communicate information to the profiler.</span></span>  
  
 [<span data-ttu-id="bfb72-117">ICorProfilerCallback5 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bfb72-117">ICorProfilerCallback5 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-interface.md)  
 <span data-ttu-id="bfb72-118">ガベージ コレクションのルートによって参照されるオブジェクトの遷移的なクロージャを識別するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="bfb72-118">Provides a method that identifies the transitive closure of objects referenced by garbage collection roots.</span></span>  
  
 [<span data-ttu-id="bfb72-119">ICorProfilerCallback6 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bfb72-119">ICorProfilerCallback6 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-interface.md)  
 <span data-ttu-id="bfb72-120">CLR が プロファイラーに対して、アセンブリがロード中であることを通知するために使用するコールバック メソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="bfb72-120">Provides a callback method that the CLR uses to notify a profiler that an assembly is loading.</span></span>  
  
 [<span data-ttu-id="bfb72-121">ICorProfilerCallback7 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bfb72-121">ICorProfilerCallback7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-interface.md)  
 <span data-ttu-id="bfb72-122">共通言語ランタイムを使用してメモリ内のモジュールに関連付けられているシンボルのストリームが更新されたことをプロファイラーに通知するコールバック メソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="bfb72-122">Provides a callback method that the common language runtime uses to notify the profiler that the symbol stream associated with an in-memory module is updated.</span></span>  

[<span data-ttu-id="bfb72-123">ICorProfilerCallback8 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bfb72-123">ICorProfilerCallback8 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback8-interface.md)  
<span data-ttu-id="bfb72-124">共通言語ランタイムを使用して動的メソッドの JIT コンパイルが開始して完了したことをプロファイラーに通知するコールバック メソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="bfb72-124">Provides callback methods that the common language runtime uses to notify the profiler that JIT compilation of a dynamic method has started and finished.</span></span>

[<span data-ttu-id="bfb72-125">ICorProfilerCallback9 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bfb72-125">ICorProfilerCallback9 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback9-interface.md)  
<span data-ttu-id="bfb72-126">共通言語ランタイムを使用して動的メソッドは、ガベージ コレクションされ、その後にアンロードされたことをプロファイラーに通知するコールバック メソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="bfb72-126">Provides a callback method that the common language runtime uses to notify the profiler that a dynamic method is garbage collected and subsequently unloaded.</span></span>

 [<span data-ttu-id="bfb72-127">ICorProfilerFunctionControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bfb72-127">ICorProfilerFunctionControl Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md)  
 <span data-ttu-id="bfb72-128">コード プロファイラーが CLR と通信できるようにするためのメソッドを提供します。これは特定のメソッドを再コンパイルするときに、JIT コンパイラーがどのようにしてコードを生成するかを制御するためのものです。</span><span class="sxs-lookup"><span data-stu-id="bfb72-128">Provides methods that allow a code profiler to communicate with the CLR to control how the JIT compiler should generate code when recompiling a specific method.</span></span>  
  
 [<span data-ttu-id="bfb72-129">ICorProfilerFunctionEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bfb72-129">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)  
 <span data-ttu-id="bfb72-130">CLR で関数のコレクションを順番に反復処理するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="bfb72-130">Provides methods to sequentially iterate through a collection of functions in the CLR.</span></span>  
  
 [<span data-ttu-id="bfb72-131">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bfb72-131">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 <span data-ttu-id="bfb72-132">コード プロファイラーが、イベントの監視および情報の要求を制御するために CLR との通信で使用するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="bfb72-132">Provides methods for use by code profilers to communicate with the CLR to control event monitoring and request information.</span></span>  
  
 [<span data-ttu-id="bfb72-133">ICorProfilerInfo2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bfb72-133">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)  
 <span data-ttu-id="bfb72-134">.NET Framework 2.0 以降でサポートされるメソッドによって、`ICorProfilerInfo` インターフェイスを拡張します。</span><span class="sxs-lookup"><span data-stu-id="bfb72-134">Extends the `ICorProfilerInfo` interface with methods supported in the .NET Framework 2.0 and later versions.</span></span>  
  
 [<span data-ttu-id="bfb72-135">ICorProfilerInfo3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bfb72-135">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 <span data-ttu-id="bfb72-136">拡張、 `ICorProfilerInfo2` .NET Framework 4 およびそれ以降のバージョンでサポートされるメソッドと連携します。</span><span class="sxs-lookup"><span data-stu-id="bfb72-136">Extends the `ICorProfilerInfo2` interface with methods supported in the .NET Framework 4 and later versions.</span></span>  
  
 [<span data-ttu-id="bfb72-137">ICorProfilerInfo4 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bfb72-137">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)  
 <span data-ttu-id="bfb72-138">コード プロファイラーが、イベントの監視および情報の要求を制御するために CLR との通信で使用するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="bfb72-138">Provides methods that code profilers use to communicate with the CLR to control event monitoring and to request information.</span></span>  
  
 [<span data-ttu-id="bfb72-139">ICorProfilerInfo5 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bfb72-139">ICorProfilerInfo5 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md)  
 <span data-ttu-id="bfb72-140">コード プロファイラーが、イベントの監視を制御するために CLR との通信で使用するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="bfb72-140">Provides methods for use by code profilers to communicate with the CLR to control event monitoring.</span></span>  
  
 [<span data-ttu-id="bfb72-141">ICorProfilerInfo6 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bfb72-141">ICorProfilerInfo6 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md)  
 <span data-ttu-id="bfb72-142">指定された NGen モジュールに属していて、特定のメソッドの本体にインライン化ではないすべてのメソッドに列挙子を提供します。</span><span class="sxs-lookup"><span data-stu-id="bfb72-142">Provides an enumerator to all the methods that belong to a given NGen module and that are inlined in the body of a given method.</span></span>  
  
 [<span data-ttu-id="bfb72-143">ICorProfilerInfo7 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bfb72-143">ICorProfilerInfo7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)  
 <span data-ttu-id="bfb72-144">新しくを適用するメソッドをモジュールにメタデータを定義して、メモリ内のシンボルのストリームへのアクセスを提供する提供します。</span><span class="sxs-lookup"><span data-stu-id="bfb72-144">Provides a method to apply newly defined metadata to a module and that provides access to an in-memory symbol stream.</span></span>  
  
 [<span data-ttu-id="bfb72-145">ICorProfilerModuleEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bfb72-145">ICorProfilerModuleEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md)  
 <span data-ttu-id="bfb72-146">アプリケーションまたはプロファイラーによってロードされたモジュールのコレクションを順番に反復処理するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="bfb72-146">Provides methods to sequentially iterate through a collection of modules loaded by the application or the profiler.</span></span>  
  
 [<span data-ttu-id="bfb72-147">ICorProfilerObjectEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bfb72-147">ICorProfilerObjectEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md)  
 <span data-ttu-id="bfb72-148">によって生成される固定されたオブジェクトのコレクションを順番に反復処理するメソッドを提供します[Ngen.exe (ネイティブ イメージ ジェネレーター)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md)します。</span><span class="sxs-lookup"><span data-stu-id="bfb72-148">Provides methods to sequentially iterate through a collection of frozen objects that are generated by [Ngen.exe (Native Image Generator)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md).</span></span>  
  
 [<span data-ttu-id="bfb72-149">ICorProfilerThreadEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bfb72-149">ICorProfilerThreadEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)  
 <span data-ttu-id="bfb72-150">CLR でスレッドのコレクションを順番に反復処理するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="bfb72-150">Provides methods to sequentially iterate through a collection of threads in the CLR.</span></span>  
  
 [<span data-ttu-id="bfb72-151">IMethodMalloc インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bfb72-151">IMethodMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-interface.md)  
 <span data-ttu-id="bfb72-152">提供、[アロケーション](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-alloc-method.md)メソッドを新しい Microsoft intermediate language (MSIL) 関数本体にメモリを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="bfb72-152">Provides the [Alloc](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-alloc-method.md) method to allocate memory for a new Microsoft intermediate language (MSIL) function body.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="bfb72-153">関連項目</span><span class="sxs-lookup"><span data-stu-id="bfb72-153">Related Sections</span></span>  
 [<span data-ttu-id="bfb72-154">プロファイルの概要</span><span class="sxs-lookup"><span data-stu-id="bfb72-154">Profiling Overview</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-overview.md)  
  
 [<span data-ttu-id="bfb72-155">グローバル静的関数のプロファイル</span><span class="sxs-lookup"><span data-stu-id="bfb72-155">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)  
  
 [<span data-ttu-id="bfb72-156">列挙型のプロファイリング</span><span class="sxs-lookup"><span data-stu-id="bfb72-156">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)  
  
 [<span data-ttu-id="bfb72-157">構造体のプロファイリング</span><span class="sxs-lookup"><span data-stu-id="bfb72-157">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
