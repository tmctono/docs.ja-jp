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
ms.openlocfilehash: f1cfef464569b577923fbb16624c99358998d29c
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866248"
---
# <a name="icorprofilercallbackjitcompilationfinished-method"></a><span data-ttu-id="86232-102">ICorProfilerCallback::JITCompilationFinished メソッド</span><span class="sxs-lookup"><span data-stu-id="86232-102">ICorProfilerCallback::JITCompilationFinished Method</span></span>
<span data-ttu-id="86232-103">Just-in-time (JIT) コンパイラが関数のコンパイルを完了したことをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="86232-103">Notifies the profiler that the just-in-time (JIT) compiler has finished compiling a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86232-104">構文</span><span class="sxs-lookup"><span data-stu-id="86232-104">Syntax</span></span>  
  
```cpp  
HRESULT JITCompilationFinished(  
    [in] FunctionID functionId,  
    [in] HRESULT    hrStatus,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a><span data-ttu-id="86232-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="86232-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="86232-106">\[] コンパイルされた関数の ID。</span><span class="sxs-lookup"><span data-stu-id="86232-106">\[in] The ID of the function that was compiled.</span></span>

- `hrStatus`

  <span data-ttu-id="86232-107">\[] コンパイルが成功したかどうかを示す値。</span><span class="sxs-lookup"><span data-stu-id="86232-107">\[in] A value indicating whether compilation was successful.</span></span>

- `fIsSafeToBlock`

  <span data-ttu-id="86232-108">\[] ブロッキングがランタイムの操作に影響を与えるかどうかをプロファイラーに示す値。</span><span class="sxs-lookup"><span data-stu-id="86232-108">\[in] A value indicating to the profiler whether blocking will affect the operation of the runtime.</span></span> <span data-ttu-id="86232-109">この値は、ブロックによって、呼び出し元のスレッドがこのコールバックから戻るまでランタイムが待機する場合に `true` ます。それ以外の場合は、`false`ます。</span><span class="sxs-lookup"><span data-stu-id="86232-109">The value is `true` if blocking may cause the runtime to wait for the calling thread to return from this callback; otherwise, `false`.</span></span>

  <span data-ttu-id="86232-110">`true` の値はランタイムに害を及ぼすことはありませんが、プロファイルの結果をスキューできます。</span><span class="sxs-lookup"><span data-stu-id="86232-110">Although a value of `true` will not harm the runtime, it can skew the profiling results.</span></span>

## <a name="requirements"></a><span data-ttu-id="86232-111">要件</span><span class="sxs-lookup"><span data-stu-id="86232-111">Requirements</span></span>  
 <span data-ttu-id="86232-112">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="86232-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="86232-113">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="86232-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="86232-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="86232-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="86232-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="86232-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86232-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="86232-116">See also</span></span>

- [<span data-ttu-id="86232-117">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="86232-117">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="86232-118">JITCompilationStarted メソッド</span><span class="sxs-lookup"><span data-stu-id="86232-118">JITCompilationStarted Method</span></span>](icorprofilercallback-jitcompilationstarted-method.md)
