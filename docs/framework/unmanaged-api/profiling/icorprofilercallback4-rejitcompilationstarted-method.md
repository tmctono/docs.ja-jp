---
title: ICorProfilerCallback4::ReJITCompilationStarted メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback4.ReJITCompilationStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4::ReJITCompilationStarted
helpviewer_keywords:
- ReJITCompilationStarted method, ICorProfilerCallback4 interface [.NET Framework profiling]
- ICorProfilerCallback4::ReJITCompilationStarted method [.NET Framework profiling]
ms.assetid: 512fdd00-262a-4456-a075-365ef4133c4d
topic_type:
- apiref
ms.openlocfilehash: 6e340fa08800f31d36e6cfb280cac847a4fca548
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499351"
---
# <a name="icorprofilercallback4rejitcompilationstarted-method"></a><span data-ttu-id="b31dd-102">ICorProfilerCallback4::ReJITCompilationStarted メソッド</span><span class="sxs-lookup"><span data-stu-id="b31dd-102">ICorProfilerCallback4::ReJITCompilationStarted Method</span></span>
<span data-ttu-id="b31dd-103">Just-in-time (JIT) コンパイラが関数の再コンパイルを開始したことをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="b31dd-103">Notifies the profiler that the just-in-time (JIT) compiler has started to recompile a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b31dd-104">構文</span><span class="sxs-lookup"><span data-stu-id="b31dd-104">Syntax</span></span>  
  
```cpp  
HRESULT ReJITCompilationStarted(
    [in] FunctionID functionId,  
    [in] ReJITID    rejitId,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b31dd-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b31dd-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="b31dd-106">からJIT コンパイラが再コンパイルを開始した関数の ID。</span><span class="sxs-lookup"><span data-stu-id="b31dd-106">[in] The ID of the function that the JIT compiler has started to recompile.</span></span>  
  
 `rejitId`  
 <span data-ttu-id="b31dd-107">から関数の新しいバージョンの再コンパイル ID。</span><span class="sxs-lookup"><span data-stu-id="b31dd-107">[in] The recompilation ID of the new version of the function.</span></span>  
  
 `fIsSafeToBlock`  
 <span data-ttu-id="b31dd-108">[入力] `true`ブロックが原因で、ランタイムが呼び出し元のスレッドがこのコールバックから戻るのを待機する場合があることを示します。`false`ブロックがランタイムの動作に影響を与えないことを示す場合。</span><span class="sxs-lookup"><span data-stu-id="b31dd-108">[in] `true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span> <span data-ttu-id="b31dd-109">の値は、 `true` ランタイムには影響しませんが、プロファイルの結果に影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b31dd-109">A value of `true` does not harm the runtime, but can affect the profiling results.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b31dd-110">解説</span><span class="sxs-lookup"><span data-stu-id="b31dd-110">Remarks</span></span>  
 <span data-ttu-id="b31dd-111">`ReJITCompilationStarted`ランタイムがクラスコンストラクターを処理する方法によって、各関数に対して複数の And [ReJITCompilationFinished](icorprofilercallback4-rejitcompilationfinished-method.md)メソッド呼び出しを受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="b31dd-111">It is possible to receive more than one pair of `ReJITCompilationStarted` and [ReJITCompilationFinished](icorprofilercallback4-rejitcompilationfinished-method.md) method calls for each function because of the way the runtime handles class constructors.</span></span> <span data-ttu-id="b31dd-112">たとえば、ランタイムはメソッド A の再コンパイルを開始しますが、クラス B のクラスコンストラクターを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b31dd-112">For example, the runtime starts to recompile method A, but the class constructor for class B needs to be run.</span></span> <span data-ttu-id="b31dd-113">このため、ランタイムはクラス B のコンストラクターを再コンパイルして実行します。</span><span class="sxs-lookup"><span data-stu-id="b31dd-113">Therefore, the runtime recompiles the constructor for class B and runs it.</span></span> <span data-ttu-id="b31dd-114">コンストラクターが実行されている間、メソッド a が呼び出されます。これにより、メソッド A が再コンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="b31dd-114">While the constructor is running, it makes a call to method A, which causes method A to be recompiled again.</span></span> <span data-ttu-id="b31dd-115">このシナリオでは、メソッド A の最初の再コンパイルが停止します。</span><span class="sxs-lookup"><span data-stu-id="b31dd-115">In this scenario, the first recompilation of method A is halted.</span></span> <span data-ttu-id="b31dd-116">ただし、メソッド A を再コンパイルしようとすると、JIT 再コンパイルイベントで報告されます。</span><span class="sxs-lookup"><span data-stu-id="b31dd-116">However, both attempts to recompile method A are reported with JIT recompilation events.</span></span>  
  
 <span data-ttu-id="b31dd-117">2つのスレッドが同時にコールバックを作成する場合、プロファイラーは JIT 再コンパイルコールバックのシーケンスをサポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b31dd-117">Profilers must support the sequence of JIT recompilation callbacks in cases where two threads are simultaneously making callbacks.</span></span> <span data-ttu-id="b31dd-118">たとえば、スレッド A はを呼び出します。ただし、スレッド a が `ReJITCompilationStarted` [ReJITCompilationFinished](icorprofilercallback4-rejitcompilationfinished-method.md)を呼び出す前に、スレッド B はスレッド a のコールバックからの関数 ID を使用して[ICorProfilerCallback:: exceptionsearchfunctionenter](icorprofilercallback-exceptionsearchfunctionenter-method.md)を呼び出し `ReJITCompilationStarted` ます。[ReJITCompilationFinished](icorprofilercallback4-rejitcompilationfinished-method.md)の呼び出しがまだプロファイラーによって受信されていないため、関数 ID がまだ有効ではないように見えることがあります。</span><span class="sxs-lookup"><span data-stu-id="b31dd-118">For example, thread A calls `ReJITCompilationStarted`; however, before thread A calls [ReJITCompilationFinished](icorprofilercallback4-rejitcompilationfinished-method.md), thread B calls [ICorProfilerCallback::ExceptionSearchFunctionEnter](icorprofilercallback-exceptionsearchfunctionenter-method.md) with the function ID from the `ReJITCompilationStarted` callback for thread A. It might appear that the function ID should not yet be valid because a call to [ReJITCompilationFinished](icorprofilercallback4-rejitcompilationfinished-method.md) had not yet been received by the profiler.</span></span> <span data-ttu-id="b31dd-119">ただし、この場合、関数 ID は有効です。</span><span class="sxs-lookup"><span data-stu-id="b31dd-119">However, in this case, the function ID is valid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b31dd-120">要件</span><span class="sxs-lookup"><span data-stu-id="b31dd-120">Requirements</span></span>  
 <span data-ttu-id="b31dd-121">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b31dd-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b31dd-122">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b31dd-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b31dd-123">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b31dd-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b31dd-124">**.NET Framework のバージョン:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b31dd-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b31dd-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="b31dd-125">See also</span></span>

- [<span data-ttu-id="b31dd-126">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b31dd-126">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="b31dd-127">ICorProfilerCallback4 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b31dd-127">ICorProfilerCallback4 Interface</span></span>](icorprofilercallback4-interface.md)
- [<span data-ttu-id="b31dd-128">JITCompilationFinished メソッド</span><span class="sxs-lookup"><span data-stu-id="b31dd-128">JITCompilationFinished Method</span></span>](icorprofilercallback-jitcompilationfinished-method.md)
- [<span data-ttu-id="b31dd-129">ReJITCompilationFinished メソッド</span><span class="sxs-lookup"><span data-stu-id="b31dd-129">ReJITCompilationFinished Method</span></span>](icorprofilercallback4-rejitcompilationfinished-method.md)
