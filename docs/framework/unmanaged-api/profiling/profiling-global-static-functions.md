---
title: グローバル静的関数のプロファイル
ms.date: 03/30/2017
helpviewer_keywords:
- global static functions [.NET Framework profiling]
- profiling global static functions [.NET Framework]
- unmanaged global static functions [.NET Framework], profiling
ms.assetid: 08a13a57-dc49-488d-b937-31e3051fda97
ms.openlocfilehash: 20ee2a9e045d839aa8ac043e035c438986b987ef
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76860867"
---
# <a name="profiling-global-static-functions"></a><span data-ttu-id="a75b2-102">グローバル静的関数のプロファイル</span><span class="sxs-lookup"><span data-stu-id="a75b2-102">Profiling Global Static Functions</span></span>
<span data-ttu-id="a75b2-103">このセクションでは、プロファイリング API が使用するアンマネージ API 関数について説明します。</span><span class="sxs-lookup"><span data-stu-id="a75b2-103">This section describes the unmanaged API functions that the profiling API uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a75b2-104">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="a75b2-104">In This Section</span></span>  
  
## <a name="net-framework-version-1-profiling-functions"></a><span data-ttu-id="a75b2-105">.NET Framework version 1 プロファイリング関数</span><span class="sxs-lookup"><span data-stu-id="a75b2-105">.NET Framework version 1 Profiling Functions</span></span>  
 [<span data-ttu-id="a75b2-106">FunctionEnter 関数</span><span class="sxs-lookup"><span data-stu-id="a75b2-106">FunctionEnter Function</span></span>](functionenter-function.md)  
 <span data-ttu-id="a75b2-107">コントロールが関数に渡されていることをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="a75b2-107">Notifies the profiler that control is being passed to a function.</span></span> <span data-ttu-id="a75b2-108">.NET Framework 2.0 では非推奨となりました。</span><span class="sxs-lookup"><span data-stu-id="a75b2-108">Deprecated in the .NET Framework 2.0.</span></span>  
  
 [<span data-ttu-id="a75b2-109">FunctionLeave 関数</span><span class="sxs-lookup"><span data-stu-id="a75b2-109">FunctionLeave Function</span></span>](functionleave-function.md)  
 <span data-ttu-id="a75b2-110">関数が呼び出し元に戻りようとしていることをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="a75b2-110">Notifies the profiler that a function is about to return to the caller.</span></span> <span data-ttu-id="a75b2-111">.NET Framework 2.0 では非推奨となりました。</span><span class="sxs-lookup"><span data-stu-id="a75b2-111">Deprecated in the .NET Framework 2.0.</span></span>  
  
 [<span data-ttu-id="a75b2-112">FunctionTailcall 関数</span><span class="sxs-lookup"><span data-stu-id="a75b2-112">FunctionTailcall Function</span></span>](functiontailcall-function.md)  
 <span data-ttu-id="a75b2-113">現在実行中の関数が別の関数の末尾呼び出しを実行しようとしていることをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="a75b2-113">Notifies the profiler that the currently executing function is about to perform a tail call to another function.</span></span> <span data-ttu-id="a75b2-114">.NET Framework 2.0 では非推奨となりました。</span><span class="sxs-lookup"><span data-stu-id="a75b2-114">Deprecated in the .NET Framework 2.0.</span></span>  
  
## <a name="net-framework-version-2-profiling-functions"></a><span data-ttu-id="a75b2-115">.NET Framework version 2 プロファイリング関数</span><span class="sxs-lookup"><span data-stu-id="a75b2-115">.NET Framework version 2 Profiling Functions</span></span>  
 [<span data-ttu-id="a75b2-116">FunctionIDMapper 関数</span><span class="sxs-lookup"><span data-stu-id="a75b2-116">FunctionIDMapper Function</span></span>](functionidmapper-function.md)  
 <span data-ttu-id="a75b2-117">関数の特定の識別子が、その関数の[FunctionEnter2](functionenter2-function.md)、 [FunctionLeave2](functionleave2-function.md)、および[FunctionTailcall2](functiontailcall2-function.md)コールバックで使用される代替 ID に再マップされる可能性があることをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="a75b2-117">Notifies the profiler that the given identifier of a function may be remapped to an alternative ID to be used in the [FunctionEnter2](functionenter2-function.md), [FunctionLeave2](functionleave2-function.md), and [FunctionTailcall2](functiontailcall2-function.md) callbacks for that function.</span></span> <span data-ttu-id="a75b2-118">また、プロファイラーが、その関数のコールバックを受信するかどうかを示すこともできます。</span><span class="sxs-lookup"><span data-stu-id="a75b2-118">Also enables the profiler to indicate whether it wants to receive callbacks for that function</span></span>  
  
 [<span data-ttu-id="a75b2-119">FunctionEnter2 関数</span><span class="sxs-lookup"><span data-stu-id="a75b2-119">FunctionEnter2 Function</span></span>](functionenter2-function.md)  
 <span data-ttu-id="a75b2-120">コントロールが関数に渡されていることをプロファイラーに通知し、スタックフレームと関数の引数に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="a75b2-120">Notifies the profiler that control is being passed to a function and provides information about the stack frame and function arguments.</span></span> <span data-ttu-id="a75b2-121">.NET Framework 4 では非推奨となりました。</span><span class="sxs-lookup"><span data-stu-id="a75b2-121">Deprecated in the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="a75b2-122">FunctionLeave2 関数</span><span class="sxs-lookup"><span data-stu-id="a75b2-122">FunctionLeave2 Function</span></span>](functionleave2-function.md)  
 <span data-ttu-id="a75b2-123">関数が呼び出し元に戻り、スタックフレームおよび関数の戻り値に関する情報を提供することをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="a75b2-123">Notifies the profiler that a function is about to return to the caller and provides information about the stack frame and function return value.</span></span> <span data-ttu-id="a75b2-124">.NET Framework 4 では非推奨となりました。</span><span class="sxs-lookup"><span data-stu-id="a75b2-124">Deprecated in the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="a75b2-125">FunctionTailcall2 関数</span><span class="sxs-lookup"><span data-stu-id="a75b2-125">FunctionTailcall2 Function</span></span>](functiontailcall2-function.md)  
 <span data-ttu-id="a75b2-126">現在実行中の関数が別の関数の末尾呼び出しを実行しようとしていることをプロファイラーに通知し、スタックフレームに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="a75b2-126">Notifies the profiler that the currently executing function is about to perform a tail call to another function and provides information about the stack frame.</span></span> <span data-ttu-id="a75b2-127">.NET Framework 4 では非推奨となりました。</span><span class="sxs-lookup"><span data-stu-id="a75b2-127">Deprecated in the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="a75b2-128">StackSnapshotCallback 関数</span><span class="sxs-lookup"><span data-stu-id="a75b2-128">StackSnapshotCallback Function</span></span>](stacksnapshotcallback-function.md)  
 <span data-ttu-id="a75b2-129">[ICorProfilerInfo2::D ostacksnapshot](icorprofilerinfo2-dostacksnapshot-method.md)メソッドによって開始されるスタックウォーク中に、各マネージフレームおよびスタック上のアンマネージフレームの各実行に関する情報をプロファイラーに提供します。</span><span class="sxs-lookup"><span data-stu-id="a75b2-129">Provides the profiler with information about each managed frame and each run of unmanaged frames on the stack during a stack walk, which is initiated by the [ICorProfilerInfo2::DoStackSnapshot](icorprofilerinfo2-dostacksnapshot-method.md) method.</span></span>  
  
## <a name="net-framework-version-4-profiling-functions"></a><span data-ttu-id="a75b2-130">.NET Framework version 4 プロファイリング関数</span><span class="sxs-lookup"><span data-stu-id="a75b2-130">.NET Framework version 4 Profiling Functions</span></span>  
 [<span data-ttu-id="a75b2-131">FunctionIDMapper2 関数</span><span class="sxs-lookup"><span data-stu-id="a75b2-131">FunctionIDMapper2 Function</span></span>](functionidmapper2-function.md)  
 <span data-ttu-id="a75b2-132">指定された関数の識別子が、その関数の[FunctionEnter3](functionenter3-function.md)、 [FunctionLeave3](functionleave3-function.md)、 [FunctionTailcall3](functiontailcall3-function.md)、または[FunctionEnter3WithInfo](functionenter3withinfo-function.md)、 [FunctionLeave3WithInfo](functionleave3withinfo-function.md)、および[FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md)コールバックで使用される代替 ID に再マップされる可能性があることをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="a75b2-132">Notifies the profiler that the given identifier of a function may be remapped to an alternative ID to be used in the [FunctionEnter3](functionenter3-function.md), [FunctionLeave3](functionleave3-function.md), and [FunctionTailcall3](functiontailcall3-function.md), or[FunctionEnter3WithInfo](functionenter3withinfo-function.md), [FunctionLeave3WithInfo](functionleave3withinfo-function.md), and [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) callbacks for that function.</span></span> <span data-ttu-id="a75b2-133">また、プロファイラーは、その関数のコールバックを受信するかどうかを示すこともできます。</span><span class="sxs-lookup"><span data-stu-id="a75b2-133">Also enables the profiler to indicate whether it wants to receive callbacks for that function.</span></span>  
  
 <span data-ttu-id="a75b2-134">`FunctionIDMapper2` は、`clientData` パラメーターを使用して[Functionidmapper](functionidmapper-function.md)関数を拡張します。これは、プロファイラーがランタイムを明確に区別するために使用する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a75b2-134">`FunctionIDMapper2` extends the [FunctionIDMapper](functionidmapper-function.md) function with a `clientData` parameter, which profilers may use to disambiguate among runtimes.</span></span>  
  
 [<span data-ttu-id="a75b2-135">FunctionEnter3 関数</span><span class="sxs-lookup"><span data-stu-id="a75b2-135">FunctionEnter3 Function</span></span>](functionenter3-function.md)  
 <span data-ttu-id="a75b2-136">コントロールが関数に渡されていることをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="a75b2-136">Notifies the profiler that control is being passed to a function.</span></span>  
  
 [<span data-ttu-id="a75b2-137">FunctionEnter3WithInfo 関数</span><span class="sxs-lookup"><span data-stu-id="a75b2-137">FunctionEnter3WithInfo Function</span></span>](functionenter3withinfo-function.md)  
 <span data-ttu-id="a75b2-138">コントロールが関数に渡されていることをプロファイラーに通知し、スタックフレームと関数の引数を取得するために[ICorProfilerInfo3:: GetFunctionEnter3Info](icorprofilerinfo3-getfunctionenter3info-method.md)に渡すことができるハンドルを提供します。</span><span class="sxs-lookup"><span data-stu-id="a75b2-138">Notifies the profiler that control is being passed to a function, and provides a handle that can be passed to [ICorProfilerInfo3::GetFunctionEnter3Info](icorprofilerinfo3-getfunctionenter3info-method.md) to retrieve the stack frame and function arguments.</span></span>  
  
 [<span data-ttu-id="a75b2-139">FunctionLeave3 関数</span><span class="sxs-lookup"><span data-stu-id="a75b2-139">FunctionLeave3 Function</span></span>](functionleave3-function.md)  
 <span data-ttu-id="a75b2-140">関数から制御が返されていることをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="a75b2-140">Notifies the profiler that control is being returned from a function.</span></span>  
  
 [<span data-ttu-id="a75b2-141">FunctionLeave3WithInfo 関数</span><span class="sxs-lookup"><span data-stu-id="a75b2-141">FunctionLeave3WithInfo Function</span></span>](functionleave3withinfo-function.md)  
 <span data-ttu-id="a75b2-142">関数から制御が返されていることをプロファイラーに通知し、スタックフレームと戻り値を取得するために[ICorProfilerInfo3:: GetFunctionLeave3Info](icorprofilerinfo3-getfunctionleave3info-method.md)に渡すことができるハンドルを提供します。</span><span class="sxs-lookup"><span data-stu-id="a75b2-142">Notifies the profiler that control is being returned from a function, and provides a handle that can be passed to [ICorProfilerInfo3::GetFunctionLeave3Info](icorprofilerinfo3-getfunctionleave3info-method.md) to retrieve the stack frame and the return value.</span></span>  
  
 [<span data-ttu-id="a75b2-143">FunctionTailcall3 関数</span><span class="sxs-lookup"><span data-stu-id="a75b2-143">FunctionTailcall3 Function</span></span>](functiontailcall3-function.md)  
 <span data-ttu-id="a75b2-144">現在実行中の関数が別の関数の末尾呼び出しを実行しようとしていることをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="a75b2-144">Notifies the profiler that the currently executing function is about to perform a tail call to another function.</span></span>  
  
 [<span data-ttu-id="a75b2-145">FunctionTailcall3WithInfo 関数</span><span class="sxs-lookup"><span data-stu-id="a75b2-145">FunctionTailcall3WithInfo Function</span></span>](functiontailcall3withinfo-function.md)  
 <span data-ttu-id="a75b2-146">現在実行中の関数が別の関数の末尾呼び出しを実行しようとしていることをプロファイラーに通知し、スタックフレームを取得するために[ICorProfilerInfo3:: GetFunctionTailcall3Info](icorprofilerinfo3-getfunctiontailcall3info-method.md)に渡すことができるハンドルを提供します。</span><span class="sxs-lookup"><span data-stu-id="a75b2-146">Notifies the profiler that the currently executing function is about to perform a tail call to another function, and provides a handle that can be passed to [ICorProfilerInfo3::GetFunctionTailcall3Info](icorprofilerinfo3-getfunctiontailcall3info-method.md) to retrieve the stack frame.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="a75b2-147">関連セクション</span><span class="sxs-lookup"><span data-stu-id="a75b2-147">Related Sections</span></span>  
 [<span data-ttu-id="a75b2-148">プロファイルの概要</span><span class="sxs-lookup"><span data-stu-id="a75b2-148">Profiling Overview</span></span>](profiling-overview.md)  
  
 [<span data-ttu-id="a75b2-149">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="a75b2-149">Profiling Interfaces</span></span>](profiling-interfaces.md)  
  
 [<span data-ttu-id="a75b2-150">列挙型のプロファイリング</span><span class="sxs-lookup"><span data-stu-id="a75b2-150">Profiling Enumerations</span></span>](profiling-enumerations.md)  
  
 [<span data-ttu-id="a75b2-151">構造体のプロファイリング</span><span class="sxs-lookup"><span data-stu-id="a75b2-151">Profiling Structures</span></span>](profiling-structures.md)
