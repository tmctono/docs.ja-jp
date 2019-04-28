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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4b75eebd8d9bf439a0317521a61c06ece3745be0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61787921"
---
# <a name="icorprofilercallbackjitcompilationstarted-method"></a><span data-ttu-id="7b911-102">ICorProfilerCallback::JITCompilationStarted メソッド</span><span class="sxs-lookup"><span data-stu-id="7b911-102">ICorProfilerCallback::JITCompilationStarted Method</span></span>
<span data-ttu-id="7b911-103">ジャストイン タイム (JIT) コンパイラが関数のコンパイルを開始されたことをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="7b911-103">Notifies the profiler that the just-in-time (JIT) compiler has started to compile a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b911-104">構文</span><span class="sxs-lookup"><span data-stu-id="7b911-104">Syntax</span></span>  
  
```  
HRESULT JITCompilationStarted(  
    [in] FunctionID functionId,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7b911-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7b911-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="7b911-106">[in]コンパイルの開始を関数の ID。</span><span class="sxs-lookup"><span data-stu-id="7b911-106">[in] The ID of the function for which the compilation is starting.</span></span>  
  
 `fIsSafeToBlock`  
 <span data-ttu-id="7b911-107">[in]プロファイラーをブロックしているかどうかを示す値は、ランタイムの操作に影響されます。</span><span class="sxs-lookup"><span data-stu-id="7b911-107">[in] A value indicating to the profiler whether blocking will affect the operation of the runtime.</span></span> <span data-ttu-id="7b911-108">値が`true`ブロックにより、ランタイムでこのコールバックから返される呼び出し元のスレッドを待機する場合は、それ以外の場合、`false`します。</span><span class="sxs-lookup"><span data-stu-id="7b911-108">The value is `true` if blocking may cause the runtime to wait for the calling thread to return from this callback; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="7b911-109">値が`true`ランタイムは害を及ぼしません、プロファイリングの結果の傾斜を実行できます。</span><span class="sxs-lookup"><span data-stu-id="7b911-109">Although a value of `true` will not harm the runtime, it can skew the profiling results.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7b911-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="7b911-110">Remarks</span></span>  
 <span data-ttu-id="7b911-111">1 つ以上のペアを受信することは`JITCompilationStarted`と[icorprofilercallback::jitcompilationfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md)ランタイムを呼び出して、各関数の方法により、ハンドル クラスのコンス トラクター。</span><span class="sxs-lookup"><span data-stu-id="7b911-111">It is possible to receive more than one pair of `JITCompilationStarted` and [ICorProfilerCallback::JITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md) calls for each function because of the way the runtime handles class constructors.</span></span> <span data-ttu-id="7b911-112">たとえば、ランタイムの JIT コンパイル メソッド A、開始しますが、クラス B のクラス コンス トラクターを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7b911-112">For example, the runtime starts to JIT-compile method A, but the class constructor for class B needs to be run.</span></span> <span data-ttu-id="7b911-113">ランタイムの JIT コンパイルではそのため、クラス B のコンス トラクターが実行されるとします。</span><span class="sxs-lookup"><span data-stu-id="7b911-113">Therefore, the runtime JIT-compiles the constructor for class B and runs it.</span></span> <span data-ttu-id="7b911-114">コンス トラクターが実行されている、メソッド、メソッドを再度 JIT コンパイルに A、A への呼び出しになります。</span><span class="sxs-lookup"><span data-stu-id="7b911-114">While the constructor is running, it makes a call to method A, which causes method A to be JIT-compiled again.</span></span> <span data-ttu-id="7b911-115">このシナリオでは、メソッド A の最初の JIT コンパイルが停止します。</span><span class="sxs-lookup"><span data-stu-id="7b911-115">In this scenario, the first JIT compilation of method A is halted.</span></span> <span data-ttu-id="7b911-116">ただし、JIT コンパイル メソッド A に両方の試行は、JIT コンパイル イベントで報告されます。</span><span class="sxs-lookup"><span data-stu-id="7b911-116">However, both attempts to JIT-compile method A are reported with JIT-compilation events.</span></span> <span data-ttu-id="7b911-117">プロファイラーを呼び出すことによってメソッド A 用の Microsoft intermediate language (MSIL) コードを置き換える場合は、 [icorprofilerinfo::setilfunctionbody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md)メソッドでは、両方を行う必要があります`JITCompilationStarted`イベントが同じ MSIL ブロックの使用可能性がありますします。</span><span class="sxs-lookup"><span data-stu-id="7b911-117">If the profiler is going to replace Microsoft intermediate language (MSIL) code for method A by calling the [ICorProfilerInfo::SetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md) method, it must do so for both `JITCompilationStarted` events, but it may use the same MSIL block for both.</span></span>  
  
 <span data-ttu-id="7b911-118">プロファイラーは、場合、2 つのスレッドではコールバックを行う同時に JIT コールバックのシーケンスをサポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7b911-118">Profilers must support the sequence of JIT callbacks in cases where two threads are simultaneously making callbacks.</span></span> <span data-ttu-id="7b911-119">たとえば、スレッド A が呼び出す`JITCompilationStarted`します。</span><span class="sxs-lookup"><span data-stu-id="7b911-119">For example, thread A calls `JITCompilationStarted`.</span></span> <span data-ttu-id="7b911-120">ただし、スレッド A 呼び出しの前に`JITCompilationFinished`、スレッド B 呼び出し[icorprofilercallback::exceptionsearchfunctionenter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md)スレッド A にから関数の ID を持つ`JITCompilationStarted`コールバック。</span><span class="sxs-lookup"><span data-stu-id="7b911-120">However, before thread A calls `JITCompilationFinished`, thread B calls [ICorProfilerCallback::ExceptionSearchFunctionEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md) with the function ID from thread A's `JITCompilationStarted` callback.</span></span> <span data-ttu-id="7b911-121">関数の ID がまだされないこと有効が表示されるためへの呼び出し`JITCompilationFinished`プロファイラーがまだ受信したされません。</span><span class="sxs-lookup"><span data-stu-id="7b911-121">It might appear that the function ID should not yet be valid because a call to `JITCompilationFinished` had not yet been received by the profiler.</span></span> <span data-ttu-id="7b911-122">ただし、このような場合は、関数の ID は有効です。</span><span class="sxs-lookup"><span data-stu-id="7b911-122">However, in a case like this one, the function ID is valid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b911-123">必要条件</span><span class="sxs-lookup"><span data-stu-id="7b911-123">Requirements</span></span>  
 <span data-ttu-id="7b911-124">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b911-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b911-125">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7b911-125">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7b911-126">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7b911-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7b911-127">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b911-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b911-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="7b911-128">See also</span></span>

- [<span data-ttu-id="7b911-129">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7b911-129">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="7b911-130">JITCompilationFinished メソッド</span><span class="sxs-lookup"><span data-stu-id="7b911-130">JITCompilationFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md)
