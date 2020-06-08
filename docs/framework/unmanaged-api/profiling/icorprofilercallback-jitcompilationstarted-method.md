---
title: ICorProfilerCallback::JITCompilationStarted メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITCompilationStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITCompilationStarted
helpviewer_keywords:
- JITCompilationStarted method [.NET Framework profiling]
- ICorProfilerCallback::JITCompilationStarted method [.NET Framework profiling]
ms.assetid: 31782b36-d311-4518-8f45-25f65385af5b
topic_type:
- apiref
ms.openlocfilehash: 57981ef134dc3f30337d47f5cee426a25d0414cf
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500040"
---
# <a name="icorprofilercallbackjitcompilationstarted-method"></a><span data-ttu-id="3bfdb-102">ICorProfilerCallback::JITCompilationStarted メソッド</span><span class="sxs-lookup"><span data-stu-id="3bfdb-102">ICorProfilerCallback::JITCompilationStarted Method</span></span>
<span data-ttu-id="3bfdb-103">Just-in-time (JIT) コンパイラが関数のコンパイルを開始したことをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="3bfdb-103">Notifies the profiler that the just-in-time (JIT) compiler has started to compile a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3bfdb-104">構文</span><span class="sxs-lookup"><span data-stu-id="3bfdb-104">Syntax</span></span>  
  
```cpp  
HRESULT JITCompilationStarted(  
    [in] FunctionID functionId,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3bfdb-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3bfdb-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="3bfdb-106">からコンパイルを開始する関数の ID。</span><span class="sxs-lookup"><span data-stu-id="3bfdb-106">[in] The ID of the function for which the compilation is starting.</span></span>  
  
 `fIsSafeToBlock`  
 <span data-ttu-id="3bfdb-107">からプロファイラーに対して、ブロックがランタイムの操作に影響を与えるかどうかを示す値。</span><span class="sxs-lookup"><span data-stu-id="3bfdb-107">[in] A value indicating to the profiler whether blocking will affect the operation of the runtime.</span></span> <span data-ttu-id="3bfdb-108">この値は、ブロックによって、 `true` ランタイムが呼び出し元のスレッドがこのコールバックから戻るのを待機する場合は、それ以外の場合はです `false` 。</span><span class="sxs-lookup"><span data-stu-id="3bfdb-108">The value is `true` if blocking may cause the runtime to wait for the calling thread to return from this callback; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="3bfdb-109">の値は `true` ランタイムに害を及ぼすことはありませんが、プロファイルの結果をスキューできます。</span><span class="sxs-lookup"><span data-stu-id="3bfdb-109">Although a value of `true` will not harm the runtime, it can skew the profiling results.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3bfdb-110">解説</span><span class="sxs-lookup"><span data-stu-id="3bfdb-110">Remarks</span></span>  
 <span data-ttu-id="3bfdb-111">ランタイムがクラスコンストラクターを処理する方法によって、各関数に対して複数のペアの `JITCompilationStarted` と[ICorProfilerCallback:: JITCompilationFinished](icorprofilercallback-jitcompilationfinished-method.md)呼び出しを受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="3bfdb-111">It is possible to receive more than one pair of `JITCompilationStarted` and [ICorProfilerCallback::JITCompilationFinished](icorprofilercallback-jitcompilationfinished-method.md) calls for each function because of the way the runtime handles class constructors.</span></span> <span data-ttu-id="3bfdb-112">たとえば、ランタイムは JIT コンパイルメソッド A を開始しますが、クラス B のクラスコンストラクターを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3bfdb-112">For example, the runtime starts to JIT-compile method A, but the class constructor for class B needs to be run.</span></span> <span data-ttu-id="3bfdb-113">このため、ランタイムは、クラス B のコンストラクターを JIT でコンパイルして実行します。</span><span class="sxs-lookup"><span data-stu-id="3bfdb-113">Therefore, the runtime JIT-compiles the constructor for class B and runs it.</span></span> <span data-ttu-id="3bfdb-114">コンストラクターが実行されている間、メソッド a が呼び出されます。これにより、メソッド A が再度 JIT コンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="3bfdb-114">While the constructor is running, it makes a call to method A, which causes method A to be JIT-compiled again.</span></span> <span data-ttu-id="3bfdb-115">このシナリオでは、メソッド A の最初の JIT コンパイルが停止します。</span><span class="sxs-lookup"><span data-stu-id="3bfdb-115">In this scenario, the first JIT compilation of method A is halted.</span></span> <span data-ttu-id="3bfdb-116">ただし、JIT コンパイルメソッド A の両方の試行は、JIT コンパイルイベントを使用して報告されます。</span><span class="sxs-lookup"><span data-stu-id="3bfdb-116">However, both attempts to JIT-compile method A are reported with JIT-compilation events.</span></span> <span data-ttu-id="3bfdb-117">プロファイラーは、 [ICorProfilerInfo:: SetILFunctionBody](icorprofilerinfo-setilfunctionbody-method.md)メソッドを呼び出すことによってメソッド A の Microsoft 中間言語 (MSIL) コードを置き換える必要がある場合、両方のイベントに対してこれを行う必要があり `JITCompilationStarted` ますが、両方に同じ msil ブロックを使用する場合があります。</span><span class="sxs-lookup"><span data-stu-id="3bfdb-117">If the profiler is going to replace Microsoft intermediate language (MSIL) code for method A by calling the [ICorProfilerInfo::SetILFunctionBody](icorprofilerinfo-setilfunctionbody-method.md) method, it must do so for both `JITCompilationStarted` events, but it may use the same MSIL block for both.</span></span>  
  
 <span data-ttu-id="3bfdb-118">2つのスレッドが同時にコールバックを作成する場合、プロファイラーは JIT コールバックのシーケンスをサポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3bfdb-118">Profilers must support the sequence of JIT callbacks in cases where two threads are simultaneously making callbacks.</span></span> <span data-ttu-id="3bfdb-119">たとえば、スレッド A はを呼び出し `JITCompilationStarted` ます。</span><span class="sxs-lookup"><span data-stu-id="3bfdb-119">For example, thread A calls `JITCompilationStarted`.</span></span> <span data-ttu-id="3bfdb-120">ただし、スレッド A が呼び出される前に、スレッド B は、 `JITCompilationFinished` スレッド a のコールバックからの関数 ID を使用して[ICorProfilerCallback:: ExceptionSearchFunctionEnter](icorprofilercallback-exceptionsearchfunctionenter-method.md)を呼び出し `JITCompilationStarted` ます。</span><span class="sxs-lookup"><span data-stu-id="3bfdb-120">However, before thread A calls `JITCompilationFinished`, thread B calls [ICorProfilerCallback::ExceptionSearchFunctionEnter](icorprofilercallback-exceptionsearchfunctionenter-method.md) with the function ID from thread A's `JITCompilationStarted` callback.</span></span> <span data-ttu-id="3bfdb-121">の呼び出しが `JITCompilationFinished` まだプロファイラーによって受信されていないため、関数 ID がまだ有効ではないように見えることがあります。</span><span class="sxs-lookup"><span data-stu-id="3bfdb-121">It might appear that the function ID should not yet be valid because a call to `JITCompilationFinished` had not yet been received by the profiler.</span></span> <span data-ttu-id="3bfdb-122">ただし、このような場合は、関数 ID が有効です。</span><span class="sxs-lookup"><span data-stu-id="3bfdb-122">However, in a case like this one, the function ID is valid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3bfdb-123">要件</span><span class="sxs-lookup"><span data-stu-id="3bfdb-123">Requirements</span></span>  
 <span data-ttu-id="3bfdb-124">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3bfdb-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3bfdb-125">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3bfdb-125">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3bfdb-126">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3bfdb-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3bfdb-127">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3bfdb-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bfdb-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="3bfdb-128">See also</span></span>

- [<span data-ttu-id="3bfdb-129">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3bfdb-129">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="3bfdb-130">JITCompilationFinished メソッド</span><span class="sxs-lookup"><span data-stu-id="3bfdb-130">JITCompilationFinished Method</span></span>](icorprofilercallback-jitcompilationfinished-method.md)
