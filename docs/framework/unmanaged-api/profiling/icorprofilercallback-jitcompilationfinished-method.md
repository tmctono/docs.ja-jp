---
title: ICorProfilerCallback::JITCompilationFinished メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITCompilationFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITCompilationFinished
helpviewer_keywords:
- JITCompilationFinished method [.NET Framework profiling]
- ICorProfilerCallback::JITCompilationFinished method [.NET Framework profiling]
ms.assetid: 8dcd7537-d0c6-498c-8a56-2c060310ef65
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1abc4dd209581c9f7c8e950ea1addc74c611d248
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61787947"
---
# <a name="icorprofilercallbackjitcompilationfinished-method"></a><span data-ttu-id="a6df3-102">ICorProfilerCallback::JITCompilationFinished メソッド</span><span class="sxs-lookup"><span data-stu-id="a6df3-102">ICorProfilerCallback::JITCompilationFinished Method</span></span>
<span data-ttu-id="a6df3-103">ジャストイン タイム (JIT) コンパイラが関数のコンパイルを完了したことをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="a6df3-103">Notifies the profiler that the just-in-time (JIT) compiler has finished compiling a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6df3-104">構文</span><span class="sxs-lookup"><span data-stu-id="a6df3-104">Syntax</span></span>  
  
```  
HRESULT JITCompilationFinished(  
    [in] FunctionID functionId,  
    [in] HRESULT    hrStatus,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a6df3-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a6df3-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="a6df3-106">[in]コンパイルされた関数の ID。</span><span class="sxs-lookup"><span data-stu-id="a6df3-106">[in] The ID of the function that was compiled.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="a6df3-107">[in]コンパイルが成功したかどうかを示す値。</span><span class="sxs-lookup"><span data-stu-id="a6df3-107">[in] A value indicating whether compilation was successful.</span></span>  
  
 `fIsSafeToBlock`  
 <span data-ttu-id="a6df3-108">[in]プロファイラーをブロックしているかどうかを示す値は、ランタイムの操作に影響されます。</span><span class="sxs-lookup"><span data-stu-id="a6df3-108">[in] A value indicating to the profiler whether blocking will affect the operation of the runtime.</span></span> <span data-ttu-id="a6df3-109">値が`true`ブロックにより、ランタイムでこのコールバックから返される呼び出し元のスレッドを待機する場合は、それ以外の場合、`false`します。</span><span class="sxs-lookup"><span data-stu-id="a6df3-109">The value is `true` if blocking may cause the runtime to wait for the calling thread to return from this callback; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="a6df3-110">値が`true`ランタイムは害を及ぼしません、プロファイリングの結果の傾斜を実行できます。</span><span class="sxs-lookup"><span data-stu-id="a6df3-110">Although a value of `true` will not harm the runtime, it can skew the profiling results.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a6df3-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="a6df3-111">Requirements</span></span>  
 <span data-ttu-id="a6df3-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6df3-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6df3-113">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a6df3-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a6df3-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a6df3-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a6df3-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6df3-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6df3-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="a6df3-116">See also</span></span>

- [<span data-ttu-id="a6df3-117">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a6df3-117">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="a6df3-118">JITCompilationStarted メソッド</span><span class="sxs-lookup"><span data-stu-id="a6df3-118">JITCompilationStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md)
