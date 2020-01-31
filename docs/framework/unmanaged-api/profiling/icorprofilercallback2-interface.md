---
title: ICorProfilerCallback2 インターフェイス
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2
helpviewer_keywords:
- ICorProfilerCallback2 interface [.NET Framework profiling]
ms.assetid: 4a261dba-450d-4f1f-8d98-865b58bfc992
topic_type:
- apiref
ms.openlocfilehash: c565d0fe37a091095b18a6d59308f159fe7b4554
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865743"
---
# <a name="icorprofilercallback2-interface"></a><span data-ttu-id="a066b-102">ICorProfilerCallback2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a066b-102">ICorProfilerCallback2 Interface</span></span>
<span data-ttu-id="a066b-103">プロファイラーがサブスクライブしたイベントが発生したときにコードプロファイラーに通知するために、共通言語ランタイム (CLR) によって使用されるメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="a066b-103">Provides methods that are used by the common language runtime (CLR) to notify a code profiler when the events to which the profiler has subscribed occur.</span></span> <span data-ttu-id="a066b-104">インターフェイスは、[ICorProfilerCallback](icorprofilercallback-interface.md) インターフェイスの拡張機能です。`ICorProfilerCallback2`</span><span class="sxs-lookup"><span data-stu-id="a066b-104">The `ICorProfilerCallback2` interface is an extension of the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span> <span data-ttu-id="a066b-105">つまり、.NET Framework バージョン2.0 で導入された新しいコールバックを提供します。</span><span class="sxs-lookup"><span data-stu-id="a066b-105">That is, it provides new callbacks introduced in the .NET Framework version 2.0.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a066b-106">各メソッドの実装は、成功した場合は S_OK の値を持つ HRESULT を返し、失敗した場合は E_FAIL を返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="a066b-106">Each method implementation must return an HRESULT having a value of S_OK on success or E_FAIL on failure.</span></span> <span data-ttu-id="a066b-107">現在、CLR では、 [ICorProfilerCallback:: ObjectReferences](icorprofilercallback-objectreferences-method.md)を除く各コールバックによって返される HRESULT は無視されます。</span><span class="sxs-lookup"><span data-stu-id="a066b-107">Currently, the CLR ignores the HRESULT that is returned by each callback except [ICorProfilerCallback::ObjectReferences](icorprofilercallback-objectreferences-method.md).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a066b-108">メソッド</span><span class="sxs-lookup"><span data-stu-id="a066b-108">Methods</span></span>  
  
|<span data-ttu-id="a066b-109">メソッド</span><span class="sxs-lookup"><span data-stu-id="a066b-109">Method</span></span>|<span data-ttu-id="a066b-110">説明</span><span class="sxs-lookup"><span data-stu-id="a066b-110">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a066b-111">FinalizeableObjectQueued メソッド</span><span class="sxs-lookup"><span data-stu-id="a066b-111">FinalizeableObjectQueued Method</span></span>](icorprofilercallback2-finalizeableobjectqueued-method.md)|<span data-ttu-id="a066b-112">ファイナライザーを持つオブジェクトが `Finalize` メソッドを実行するためにファイナライザースレッドに対してキューに登録されていることをコードプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="a066b-112">Notifies the code profiler that an object with a finalizer has been queued to the finalizer thread for execution of its `Finalize` method.</span></span>|  
|[<span data-ttu-id="a066b-113">GarbageCollectionFinished メソッド</span><span class="sxs-lookup"><span data-stu-id="a066b-113">GarbageCollectionFinished Method</span></span>](icorprofilercallback2-garbagecollectionfinished-method.md)|<span data-ttu-id="a066b-114">ガベージコレクションが完了し、すべてのガベージコレクションコールバックが発行されたことをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="a066b-114">Notifies the profiler that a garbage collection has completed and all garbage collection callbacks have been issued for it.</span></span>|  
|[<span data-ttu-id="a066b-115">GarbageCollectionStarted メソッド</span><span class="sxs-lookup"><span data-stu-id="a066b-115">GarbageCollectionStarted Method</span></span>](icorprofilercallback2-garbagecollectionstarted-method.md)|<span data-ttu-id="a066b-116">ガベージコレクションが開始されたことをコードプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="a066b-116">Notifies the code profiler that a garbage collection has started.</span></span>|  
|[<span data-ttu-id="a066b-117">HandleCreated メソッド</span><span class="sxs-lookup"><span data-stu-id="a066b-117">HandleCreated Method</span></span>](icorprofilercallback2-handlecreated-method.md)|<span data-ttu-id="a066b-118">ガベージコレクションハンドルが作成されたことをコードプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="a066b-118">Notifies the code profiler that a garbage collection handle has been created.</span></span>|  
|[<span data-ttu-id="a066b-119">HandleDestroyed メソッド</span><span class="sxs-lookup"><span data-stu-id="a066b-119">HandleDestroyed Method</span></span>](icorprofilercallback2-handledestroyed-method.md)|<span data-ttu-id="a066b-120">ガベージコレクションハンドルが破棄されたことをコードプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="a066b-120">Notifies the code profiler that a garbage collection handle has been destroyed.</span></span>|  
|[<span data-ttu-id="a066b-121">RootReferences2 メソッド</span><span class="sxs-lookup"><span data-stu-id="a066b-121">RootReferences2 Method</span></span>](icorprofilercallback2-rootreferences2-method.md)|<span data-ttu-id="a066b-122">ガベージコレクションが発生した後のルート参照をプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="a066b-122">Notifies the profiler about root references after a garbage collection has occurred.</span></span> <span data-ttu-id="a066b-123">このメソッドは、 [ICorProfilerCallback:: RootReferences](icorprofilercallback-rootreferences-method.md)メソッドの拡張です。</span><span class="sxs-lookup"><span data-stu-id="a066b-123">This method is an extension of the [ICorProfilerCallback::RootReferences](icorprofilercallback-rootreferences-method.md) method.</span></span>|  
|[<span data-ttu-id="a066b-124">SurvivingReferences メソッド</span><span class="sxs-lookup"><span data-stu-id="a066b-124">SurvivingReferences Method</span></span>](icorprofilercallback2-survivingreferences-method.md)|<span data-ttu-id="a066b-125">ガベージコレクションで残ったオブジェクト参照をプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="a066b-125">Notifies the profiler about object references that have survived a garbage collection.</span></span>|  
|[<span data-ttu-id="a066b-126">ThreadNameChanged メソッド</span><span class="sxs-lookup"><span data-stu-id="a066b-126">ThreadNameChanged Method</span></span>](icorprofilercallback2-threadnamechanged-method.md)|<span data-ttu-id="a066b-127">スレッドの名前が変更されたことをコードプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="a066b-127">Notifies the code profiler that the name of a thread has changed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a066b-128">コメント</span><span class="sxs-lookup"><span data-stu-id="a066b-128">Remarks</span></span>  
 <span data-ttu-id="a066b-129">CLR は、`ICorProfilerCallback` (または `ICorProfilerCallback2`) インターフェイスのメソッドを呼び出して、プロファイラーがサブスクライブしているイベントが発生したときにプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="a066b-129">The CLR calls a method in the `ICorProfilerCallback` (or `ICorProfilerCallback2`) interface to notify the profiler when an event, to which the profiler had subscribed, occurs.</span></span> <span data-ttu-id="a066b-130">これは、CLR がコードプロファイラーと通信するときに使用する主要なコールバックインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="a066b-130">This is the primary callback interface through which the CLR communicates with the code profiler.</span></span>  
  
 <span data-ttu-id="a066b-131">コードプロファイラーは、`ICorProfilerCallback` インターフェイスのメソッドを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a066b-131">A code profiler must implement the methods of the `ICorProfilerCallback` interface.</span></span> <span data-ttu-id="a066b-132">.NET Framework 2.0 以降のバージョンでは、プロファイラーで `ICorProfilerCallback2` メソッドも実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a066b-132">For the .NET Framework 2.0 and later versions, the profiler must also implement the `ICorProfilerCallback2` methods.</span></span> <span data-ttu-id="a066b-133">各メソッドの実装は、成功した場合は S_OK の値を持つ HRESULT を返し、失敗した場合は E_FAIL を返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="a066b-133">Each method implementation must return an HRESULT having a value of S_OK on success or E_FAIL on failure.</span></span> <span data-ttu-id="a066b-134">現在、CLR では、 [ICorProfilerCallback:: ObjectReferences](icorprofilercallback-objectreferences-method.md)を除く各コールバックによって返される HRESULT は無視されます。</span><span class="sxs-lookup"><span data-stu-id="a066b-134">Currently, the CLR ignores the HRESULT that is returned by each callback except [ICorProfilerCallback::ObjectReferences](icorprofilercallback-objectreferences-method.md).</span></span>  
  
 <span data-ttu-id="a066b-135">コードプロファイラーは、Microsoft Windows レジストリ、`ICorProfilerCallback` および `ICorProfilerCallback2` インターフェイスを実装する COM オブジェクトに登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a066b-135">A code profiler must register in the Microsoft Windows registry, its COM object that implements the `ICorProfilerCallback` and `ICorProfilerCallback2` interfaces.</span></span> <span data-ttu-id="a066b-136">コードプロファイラーは、 [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md)を呼び出して、通知を受信するイベントをサブスクライブします。</span><span class="sxs-lookup"><span data-stu-id="a066b-136">A code profiler subscribes to the events for which it wants to receive notification by calling [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md).</span></span> <span data-ttu-id="a066b-137">これは通常、プロファイラーによる[ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md)の実装で行われます。</span><span class="sxs-lookup"><span data-stu-id="a066b-137">This is usually done in the profiler's implementation of [ICorProfilerCallback::Initialize](icorprofilercallback-initialize-method.md).</span></span> <span data-ttu-id="a066b-138">その後、プロファイラーは、実行中のランタイムプロセスでイベントが発生するか、発生したばかりの場合に、ランタイムから通知を受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="a066b-138">The profiler is then able to receive notification from the runtime when an event is about to occur or has just occurred in an executing runtime process.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a066b-139">プロファイラーは、1つの COM オブジェクトを登録します。</span><span class="sxs-lookup"><span data-stu-id="a066b-139">The profiler registers a single COM object.</span></span> <span data-ttu-id="a066b-140">プロファイラーが .NET Framework バージョン1.0 または1.1 を対象としている場合、その COM オブジェクトは `ICorProfilerCallback`のメソッドのみを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a066b-140">If the profiler is targeting .NET Framework version 1.0 or 1.1, that COM object need only implement the methods of `ICorProfilerCallback`.</span></span> <span data-ttu-id="a066b-141">.NET Framework バージョン2.0 以降を対象としている場合、COM オブジェクトは `ICorProfilerCallback2`のメソッドも実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a066b-141">If it is targeting .NET Framework version 2.0 and later, the COM object must also implement the methods of `ICorProfilerCallback2`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a066b-142">要件</span><span class="sxs-lookup"><span data-stu-id="a066b-142">Requirements</span></span>  
 <span data-ttu-id="a066b-143">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a066b-143">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a066b-144">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a066b-144">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a066b-145">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a066b-145">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a066b-146">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a066b-146">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a066b-147">関連項目</span><span class="sxs-lookup"><span data-stu-id="a066b-147">See also</span></span>

- [<span data-ttu-id="a066b-148">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="a066b-148">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="a066b-149">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a066b-149">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="a066b-150">ICorProfilerCallback3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a066b-150">ICorProfilerCallback3 Interface</span></span>](icorprofilercallback3-interface.md)
- [<span data-ttu-id="a066b-151">ICorProfilerCallback4 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a066b-151">ICorProfilerCallback4 Interface</span></span>](icorprofilercallback4-interface.md)
