---
title: ICorProfilerCallback4 インターフェイス
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback4
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4
helpviewer_keywords:
- ICorProfilerCallback4 interface [.NET Framework profiling]
ms.assetid: 665f3cfc-cd6f-4880-906c-ea65ad384783
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3eb1f46900199db65be5d14c56bfc0b6f55bf269
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61598192"
---
# <a name="icorprofilercallback4-interface"></a><span data-ttu-id="2973f-102">ICorProfilerCallback4 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2973f-102">ICorProfilerCallback4 Interface</span></span>
<span data-ttu-id="2973f-103">共通言語ランタイム (CLR) がプロファイラーに情報を通信に使用するコールバック メソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="2973f-103">Provides callback methods that the common language runtime (CLR) uses to communicate information to the profiler.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2973f-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="2973f-104">Methods</span></span>  
  
|<span data-ttu-id="2973f-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="2973f-105">Method</span></span>|<span data-ttu-id="2973f-106">説明</span><span class="sxs-lookup"><span data-stu-id="2973f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2973f-107">GetReJITParameters メソッド</span><span class="sxs-lookup"><span data-stu-id="2973f-107">GetReJITParameters Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md)|<span data-ttu-id="2973f-108">新しい再コンパイルされたメソッド本体の代替コード生成フラグを設定するコード プロファイラーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="2973f-108">Allows the code profiler to set alternate code generation flags for a new recompiled method body.</span></span>|  
|[<span data-ttu-id="2973f-109">MovedReferences2 メソッド</span><span class="sxs-lookup"><span data-stu-id="2973f-109">MovedReferences2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-movedreferences2-method.md)|<span data-ttu-id="2973f-110">圧縮ガベージ コレクション ヒープ内のオブジェクトの新しいレイアウトを報告します。</span><span class="sxs-lookup"><span data-stu-id="2973f-110">Reports the new layout of objects in the heap as a result of a compacting garbage collection.</span></span>|  
|[<span data-ttu-id="2973f-111">ReJITCompilationFinished メソッド</span><span class="sxs-lookup"><span data-stu-id="2973f-111">ReJITCompilationFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md)|<span data-ttu-id="2973f-112">ジャストイン タイム (JIT) コンパイラが関数の再コンパイルを完了したことをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="2973f-112">Notifies the profiler that the just-in-time (JIT) compiler has finished the recompilation of a function.</span></span>|  
|[<span data-ttu-id="2973f-113">ReJITCompilationStarted メソッド</span><span class="sxs-lookup"><span data-stu-id="2973f-113">ReJITCompilationStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationstarted-method.md)|<span data-ttu-id="2973f-114">関数を再コンパイル、ジャストイン タイム (JIT) コンパイラが開始されたことをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="2973f-114">Notifies the profiler that the just-in-time (JIT) compiler has started to recompile a function.</span></span>|  
|[<span data-ttu-id="2973f-115">ReJITError メソッド</span><span class="sxs-lookup"><span data-stu-id="2973f-115">ReJITError Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejiterror-method.md)|<span data-ttu-id="2973f-116">再コンパイル要求の処理中に発生したエラーを報告します。</span><span class="sxs-lookup"><span data-stu-id="2973f-116">Reports an error encountered while processing a recompile request.</span></span>|  
|[<span data-ttu-id="2973f-117">SurvivingReferences2 メソッド</span><span class="sxs-lookup"><span data-stu-id="2973f-117">SurvivingReferences2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-survivingreferences2-method.md)|<span data-ttu-id="2973f-118">非圧縮ガベージ コレクションを実行した後の、ヒープ内のオブジェクトのレイアウトを報告します。</span><span class="sxs-lookup"><span data-stu-id="2973f-118">Reports the layout of objects in the heap as a result of a non-compacting garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2973f-119">Remarks</span><span class="sxs-lookup"><span data-stu-id="2973f-119">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2973f-120">必要条件</span><span class="sxs-lookup"><span data-stu-id="2973f-120">Requirements</span></span>  
 <span data-ttu-id="2973f-121">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2973f-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2973f-122">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2973f-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2973f-123">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2973f-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2973f-124">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2973f-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2973f-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="2973f-125">See also</span></span>

- [<span data-ttu-id="2973f-126">ICorProfilerCallback2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2973f-126">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
- [<span data-ttu-id="2973f-127">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="2973f-127">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="2973f-128">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2973f-128">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
