---
title: ICorProfilerCallback4::ReJITCompilationFinished メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback4.ReJITCompilationFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4::ReJITCompilationFinished
helpviewer_keywords:
- ICorProfilerCallback4::ReJITCompilationFinished method [.NET Framework profiling]
- ReJITCompilationFinished method, ICorProfilerCallback4 interface [.NET Framework profiling]
ms.assetid: 3b5cff02-2005-44eb-a2bc-50214c4b0e1d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0ec2981cbee4675f9cd2a4fd13d507f50ad2a3ff
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61597142"
---
# <a name="icorprofilercallback4rejitcompilationfinished-method"></a><span data-ttu-id="864a4-102">ICorProfilerCallback4::ReJITCompilationFinished メソッド</span><span class="sxs-lookup"><span data-stu-id="864a4-102">ICorProfilerCallback4::ReJITCompilationFinished Method</span></span>
<span data-ttu-id="864a4-103">ジャストイン タイム (JIT) コンパイラが関数を再コンパイルを完了したことをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="864a4-103">Notifies the profiler that the just-in-time (JIT) compiler has finished recompiling a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="864a4-104">構文</span><span class="sxs-lookup"><span data-stu-id="864a4-104">Syntax</span></span>  
  
```  
HRESULT ReJITCompilationFinished(  
    [in] FunctionID functionId,    [in] ReJITID rejitId,  
    [in] HRESULT    hrStatus,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a><span data-ttu-id="864a4-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="864a4-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="864a4-106">[in]再コンパイルされた関数の ID。</span><span class="sxs-lookup"><span data-stu-id="864a4-106">[in] The ID of the function that was recompiled.</span></span>  
  
 `rejitId`  
 <span data-ttu-id="864a4-107">[in] JIT 再コンパイルされた関数のID。</span><span class="sxs-lookup"><span data-stu-id="864a4-107">[in] The identity of the JIT-recompiled function.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="864a4-108">[in]JIT 再コンパイルが成功したかどうかを示す値。</span><span class="sxs-lookup"><span data-stu-id="864a4-108">[in] A value that indicates whether the JIT recompilation was successful.</span></span>  
  
 `fIsSafeToBlock`  
 <span data-ttu-id="864a4-109">[in]`true`をブロックしていることにより、ランタイムでこのコールバックから返される呼び出し元のスレッドを待機するかを示す`false`をブロックしてに影響しないこと、実行時の操作を示します。</span><span class="sxs-lookup"><span data-stu-id="864a4-109">[in] `true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span>  
  
 <span data-ttu-id="864a4-110">値`true`ランタイムは害を及ぼしませんが、プロファイリングの結果に影響を与えることができます。</span><span class="sxs-lookup"><span data-stu-id="864a4-110">A value of `true` does not harm the runtime, but can affect the profiling results.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="864a4-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="864a4-111">Requirements</span></span>  
 <span data-ttu-id="864a4-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="864a4-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="864a4-113">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="864a4-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="864a4-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="864a4-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="864a4-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="864a4-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="864a4-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="864a4-116">See also</span></span>

- [<span data-ttu-id="864a4-117">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="864a4-117">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="864a4-118">ICorProfilerCallback4 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="864a4-118">ICorProfilerCallback4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
- [<span data-ttu-id="864a4-119">JITCompilationStarted メソッド</span><span class="sxs-lookup"><span data-stu-id="864a4-119">JITCompilationStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md)
- [<span data-ttu-id="864a4-120">ReJITCompilationStarted メソッド</span><span class="sxs-lookup"><span data-stu-id="864a4-120">ReJITCompilationStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationstarted-method.md)
