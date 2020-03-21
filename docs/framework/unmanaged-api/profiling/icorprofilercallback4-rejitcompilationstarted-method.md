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
ms.openlocfilehash: be257930ca0fad658afa75d6efa4573d4f888a2b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177088"
---
# <a name="icorprofilercallback4rejitcompilationstarted-method"></a><span data-ttu-id="609c8-102">ICorProfilerCallback4::ReJITCompilationStarted メソッド</span><span class="sxs-lookup"><span data-stu-id="609c8-102">ICorProfilerCallback4::ReJITCompilationStarted Method</span></span>
<span data-ttu-id="609c8-103">ジャスト イン タイム (JIT) コンパイラが関数の再コンパイルを開始したことをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="609c8-103">Notifies the profiler that the just-in-time (JIT) compiler has started to recompile a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="609c8-104">構文</span><span class="sxs-lookup"><span data-stu-id="609c8-104">Syntax</span></span>  
  
```cpp  
HRESULT ReJITCompilationStarted(
    [in] FunctionID functionId,  
    [in] ReJITID    rejitId,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a><span data-ttu-id="609c8-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="609c8-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="609c8-106">[in]JIT コンパイラが再コンパイルを開始した関数の ID。</span><span class="sxs-lookup"><span data-stu-id="609c8-106">[in] The ID of the function that the JIT compiler has started to recompile.</span></span>  
  
 `rejitId`  
 <span data-ttu-id="609c8-107">[in]関数の新しいバージョンの再コンパイル ID。</span><span class="sxs-lookup"><span data-stu-id="609c8-107">[in] The recompilation ID of the new version of the function.</span></span>  
  
 `fIsSafeToBlock`  
 <span data-ttu-id="609c8-108">[in]`true`をクリックすると、呼び出し元のスレッドがこのコールバックから返されるのをランタイムが待機する可能性があることを示します。`false`ブロックがランタイムの操作に影響しないことを示します。</span><span class="sxs-lookup"><span data-stu-id="609c8-108">[in] `true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span> <span data-ttu-id="609c8-109">値を指定`true`すると、ランタイムに影響はありませんが、プロファイル結果に影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="609c8-109">A value of `true` does not harm the runtime, but can affect the profiling results.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="609c8-110">解説</span><span class="sxs-lookup"><span data-stu-id="609c8-110">Remarks</span></span>  
 <span data-ttu-id="609c8-111">ランタイムがクラス コンストラクターを処理する方法により`ReJITCompilationStarted`、各関数に対して複数のペアと[ReJITCompilationFinished](icorprofilercallback4-rejitcompilationfinished-method.md)メソッド呼び出しを受け取ることも可能です。</span><span class="sxs-lookup"><span data-stu-id="609c8-111">It is possible to receive more than one pair of `ReJITCompilationStarted` and [ReJITCompilationFinished](icorprofilercallback4-rejitcompilationfinished-method.md) method calls for each function because of the way the runtime handles class constructors.</span></span> <span data-ttu-id="609c8-112">たとえば、ランタイムはメソッド A の再コンパイルを開始しますが、クラス B のクラス コンストラクターを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="609c8-112">For example, the runtime starts to recompile method A, but the class constructor for class B needs to be run.</span></span> <span data-ttu-id="609c8-113">したがって、ランタイムはクラス B のコンストラクターを再コンパイルして実行します。</span><span class="sxs-lookup"><span data-stu-id="609c8-113">Therefore, the runtime recompiles the constructor for class B and runs it.</span></span> <span data-ttu-id="609c8-114">コンストラクターの実行中にメソッド A が呼び出され、メソッド A が再コンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="609c8-114">While the constructor is running, it makes a call to method A, which causes method A to be recompiled again.</span></span> <span data-ttu-id="609c8-115">このシナリオでは、メソッド A の最初の再コンパイルが停止します。</span><span class="sxs-lookup"><span data-stu-id="609c8-115">In this scenario, the first recompilation of method A is halted.</span></span> <span data-ttu-id="609c8-116">ただし、メソッド A の再コンパイルは、両方とも JIT 再コンパイル イベントと共に報告されます。</span><span class="sxs-lookup"><span data-stu-id="609c8-116">However, both attempts to recompile method A are reported with JIT recompilation events.</span></span>  
  
 <span data-ttu-id="609c8-117">2 つのスレッドが同時にコールバックを行っている場合、プロファイラーは JIT 再コンパイル コールバックのシーケンスをサポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="609c8-117">Profilers must support the sequence of JIT recompilation callbacks in cases where two threads are simultaneously making callbacks.</span></span> <span data-ttu-id="609c8-118">たとえば、スレッド A`ReJITCompilationStarted`が呼び出し、ただし、スレッド A[が ReJITCompilationFinished を](icorprofilercallback4-rejitcompilationfinished-method.md)呼び出す前に、スレッド B は、スレッド A`ReJITCompilationStarted`のコールバックから関数 ID を使用して[ICorProfilerCallback::ExceptionSearchFunctionEnter を](icorprofilercallback-exceptionsearchfunctionenter-method.md)呼び出します。[ReJITCompilationFinished](icorprofilercallback4-rejitcompilationfinished-method.md)の呼び出しがプロファイラーによって受信されていないため、関数 ID がまだ有効でないように見える場合があります。</span><span class="sxs-lookup"><span data-stu-id="609c8-118">For example, thread A calls `ReJITCompilationStarted`; however, before thread A calls [ReJITCompilationFinished](icorprofilercallback4-rejitcompilationfinished-method.md), thread B calls [ICorProfilerCallback::ExceptionSearchFunctionEnter](icorprofilercallback-exceptionsearchfunctionenter-method.md) with the function ID from the `ReJITCompilationStarted` callback for thread A. It might appear that the function ID should not yet be valid because a call to [ReJITCompilationFinished](icorprofilercallback4-rejitcompilationfinished-method.md) had not yet been received by the profiler.</span></span> <span data-ttu-id="609c8-119">ただし、この場合、関数 ID は有効です。</span><span class="sxs-lookup"><span data-stu-id="609c8-119">However, in this case, the function ID is valid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="609c8-120">必要条件</span><span class="sxs-lookup"><span data-stu-id="609c8-120">Requirements</span></span>  
 <span data-ttu-id="609c8-121">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="609c8-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="609c8-122">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="609c8-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="609c8-123">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="609c8-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="609c8-124">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="609c8-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="609c8-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="609c8-125">See also</span></span>

- [<span data-ttu-id="609c8-126">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="609c8-126">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="609c8-127">ICorProfilerCallback4 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="609c8-127">ICorProfilerCallback4 Interface</span></span>](icorprofilercallback4-interface.md)
- [<span data-ttu-id="609c8-128">JITCompilationFinished メソッド</span><span class="sxs-lookup"><span data-stu-id="609c8-128">JITCompilationFinished Method</span></span>](icorprofilercallback-jitcompilationfinished-method.md)
- [<span data-ttu-id="609c8-129">ReJITCompilationFinished メソッド</span><span class="sxs-lookup"><span data-stu-id="609c8-129">ReJITCompilationFinished Method</span></span>](icorprofilercallback4-rejitcompilationfinished-method.md)
