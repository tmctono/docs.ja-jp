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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 58293929b576493d3751f9ce30ba00cec92e180c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67758168"
---
# <a name="icorprofilercallback4rejitcompilationstarted-method"></a><span data-ttu-id="464a3-102">ICorProfilerCallback4::ReJITCompilationStarted メソッド</span><span class="sxs-lookup"><span data-stu-id="464a3-102">ICorProfilerCallback4::ReJITCompilationStarted Method</span></span>
<span data-ttu-id="464a3-103">関数を再コンパイル、ジャストイン タイム (JIT) コンパイラが開始されたことをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="464a3-103">Notifies the profiler that the just-in-time (JIT) compiler has started to recompile a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="464a3-104">構文</span><span class="sxs-lookup"><span data-stu-id="464a3-104">Syntax</span></span>  
  
```cpp  
HRESULT ReJITCompilationStarted(   
    [in] FunctionID functionId,  
    [in] ReJITID    rejitId,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a><span data-ttu-id="464a3-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="464a3-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="464a3-106">[in]再コンパイル、JIT コンパイラが開始した関数の ID。</span><span class="sxs-lookup"><span data-stu-id="464a3-106">[in] The ID of the function that the JIT compiler has started to recompile.</span></span>  
  
 `rejitId`  
 <span data-ttu-id="464a3-107">[in]関数の新しいバージョンの再コンパイルの ID。</span><span class="sxs-lookup"><span data-stu-id="464a3-107">[in] The recompilation ID of the new version of the function.</span></span>  
  
 `fIsSafeToBlock`  
 <span data-ttu-id="464a3-108">[in]`true`をブロックしていることにより、ランタイムでこのコールバックから返される呼び出し元のスレッドを待機するかを示す`false`をブロックしてに影響しないこと、実行時の操作を示します。</span><span class="sxs-lookup"><span data-stu-id="464a3-108">[in] `true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span> <span data-ttu-id="464a3-109">値`true`ランタイムは害を及ぼしませんが、プロファイリングの結果に影響を与えることができます。</span><span class="sxs-lookup"><span data-stu-id="464a3-109">A value of `true` does not harm the runtime, but can affect the profiling results.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="464a3-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="464a3-110">Remarks</span></span>  
 <span data-ttu-id="464a3-111">1 つ以上のペアを受信することは`ReJITCompilationStarted`と[ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md)メソッド呼び出しの各関数の方法により、ランタイム ハンドル クラスのコンス トラクター。</span><span class="sxs-lookup"><span data-stu-id="464a3-111">It is possible to receive more than one pair of `ReJITCompilationStarted` and [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md) method calls for each function because of the way the runtime handles class constructors.</span></span> <span data-ttu-id="464a3-112">たとえば、メソッドを再コンパイルする、ランタイムが開始されますが、クラス B のクラス コンス トラクターを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="464a3-112">For example, the runtime starts to recompile method A, but the class constructor for class B needs to be run.</span></span> <span data-ttu-id="464a3-113">そのため、ランタイムは B クラスのコンス トラクターを再コンパイルし、それを実行します。</span><span class="sxs-lookup"><span data-stu-id="464a3-113">Therefore, the runtime recompiles the constructor for class B and runs it.</span></span> <span data-ttu-id="464a3-114">コンス トラクターが実行されている、A で、メソッド、もう一度再コンパイルすると、メソッドの呼び出しになります。</span><span class="sxs-lookup"><span data-stu-id="464a3-114">While the constructor is running, it makes a call to method A, which causes method A to be recompiled again.</span></span> <span data-ttu-id="464a3-115">このシナリオでは、メソッド A の最初の再コンパイルが停止します。</span><span class="sxs-lookup"><span data-stu-id="464a3-115">In this scenario, the first recompilation of method A is halted.</span></span> <span data-ttu-id="464a3-116">ただし、両方は、メソッドの JIT 再コンパイル イベントで報告されるが再コンパイルを試行します。</span><span class="sxs-lookup"><span data-stu-id="464a3-116">However, both attempts to recompile method A are reported with JIT recompilation events.</span></span>  
  
 <span data-ttu-id="464a3-117">プロファイラーは、場合、2 つのスレッドではコールバックを行う同時に JIT 再コンパイルのコールバックのシーケンスをサポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="464a3-117">Profilers must support the sequence of JIT recompilation callbacks in cases where two threads are simultaneously making callbacks.</span></span> <span data-ttu-id="464a3-118">たとえば、スレッド A が呼び出す`ReJITCompilationStarted`ただし、スレッド A 呼び出しの前に[ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md)、スレッド B 呼び出し[icorprofilercallback::exceptionsearchfunctionenter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md)関数の id。`ReJITCompilationStarted`スレッド A のコールバック関数の ID がまだされないこと有効が表示されるためへの呼び出し[ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md)プロファイラーがまだ受信したされません。</span><span class="sxs-lookup"><span data-stu-id="464a3-118">For example, thread A calls `ReJITCompilationStarted`; however, before thread A calls [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md), thread B calls [ICorProfilerCallback::ExceptionSearchFunctionEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md) with the function ID from the `ReJITCompilationStarted` callback for thread A. It might appear that the function ID should not yet be valid because a call to [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md) had not yet been received by the profiler.</span></span> <span data-ttu-id="464a3-119">ただし、この場合、関数の ID は有効です。</span><span class="sxs-lookup"><span data-stu-id="464a3-119">However, in this case, the function ID is valid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="464a3-120">必要条件</span><span class="sxs-lookup"><span data-stu-id="464a3-120">Requirements</span></span>  
 <span data-ttu-id="464a3-121">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="464a3-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="464a3-122">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="464a3-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="464a3-123">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="464a3-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="464a3-124">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="464a3-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="464a3-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="464a3-125">See also</span></span>

- [<span data-ttu-id="464a3-126">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="464a3-126">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="464a3-127">ICorProfilerCallback4 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="464a3-127">ICorProfilerCallback4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
- [<span data-ttu-id="464a3-128">JITCompilationFinished メソッド</span><span class="sxs-lookup"><span data-stu-id="464a3-128">JITCompilationFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md)
- [<span data-ttu-id="464a3-129">ReJITCompilationFinished メソッド</span><span class="sxs-lookup"><span data-stu-id="464a3-129">ReJITCompilationFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md)
