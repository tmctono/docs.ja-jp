---
title: ICorProfilerCallback::JITCachedFunctionSearchFinished メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITCachedFunctionSearchFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITCachedFunctionSearchFinished
helpviewer_keywords:
- JITCachedFunctionSearchFinished method [.NET Framework profiling]
- ICorProfilerCallback::JITCachedFunctionSearchFinished method [.NET Framework profiling]
ms.assetid: 3c325c82-cddd-4b00-b3da-e450c36abf62
topic_type:
- apiref
ms.openlocfilehash: 6efc9d407bb95f75a79252b2dfad85b396d2164a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500079"
---
# <a name="icorprofilercallbackjitcachedfunctionsearchfinished-method"></a><span data-ttu-id="d6c38-102">ICorProfilerCallback::JITCachedFunctionSearchFinished メソッド</span><span class="sxs-lookup"><span data-stu-id="d6c38-102">ICorProfilerCallback::JITCachedFunctionSearchFinished Method</span></span>
<span data-ttu-id="d6c38-103">以前にネイティブイメージジェネレーター (Ngen.exe) を使用してコンパイルされた関数の検索が終了したことをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="d6c38-103">Notifies the profiler that a search has finished for a function that was compiled previously using the Native Image Generator (NGen.exe).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6c38-104">構文</span><span class="sxs-lookup"><span data-stu-id="d6c38-104">Syntax</span></span>  
  
```cpp  
HRESULT JITCachedFunctionSearchFinished(  
    [in] FunctionID        functionId,  
    [in] COR_PRF_JIT_CACHE result);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d6c38-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d6c38-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="d6c38-106">\[in] 検索が実行された関数の ID。</span><span class="sxs-lookup"><span data-stu-id="d6c38-106">\[in] The ID of the function for which the search was performed.</span></span>

- `result`

  <span data-ttu-id="d6c38-107">\[in] 検索の結果を示す[COR_PRF_JIT_CACHE](cor-prf-jit-cache-enumeration.md)列挙体の値。</span><span class="sxs-lookup"><span data-stu-id="d6c38-107">\[in] A value of the [COR_PRF_JIT_CACHE](cor-prf-jit-cache-enumeration.md) enumeration that indicates the result of the search.</span></span>

## <a name="remarks"></a><span data-ttu-id="d6c38-108">解説</span><span class="sxs-lookup"><span data-stu-id="d6c38-108">Remarks</span></span>  
 <span data-ttu-id="d6c38-109">.NET Framework バージョン2.0 では、通常の NGen イメージのすべての関数に対して[ICorProfilerCallback:: JITCachedFunctionSearchStarted](icorprofilercallback-jitcachedfunctionsearchstarted-method.md)と `JITCachedFunctionSearchFinished` コールバックは行われません。</span><span class="sxs-lookup"><span data-stu-id="d6c38-109">In the .NET Framework version 2.0, the [ICorProfilerCallback::JITCachedFunctionSearchStarted](icorprofilercallback-jitcachedfunctionsearchstarted-method.md) and `JITCachedFunctionSearchFinished` callbacks will not be made for all functions in regular NGen images.</span></span> <span data-ttu-id="d6c38-110">プロファイラー用に最適化された NGen イメージのみが、イメージ内のすべての関数のコールバックを生成します。</span><span class="sxs-lookup"><span data-stu-id="d6c38-110">Only NGen images optimized for a profiler will generate callbacks for all functions in the image.</span></span> <span data-ttu-id="d6c38-111">ただし、オーバーヘッドが増加するため、プロファイラーは、これらのコールバックを使用して just-in-time (JIT) コンパイルを強制的に実行する場合にのみ、プロファイラーで最適化された NGen イメージを要求する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6c38-111">However, due to the additional overhead, a profiler should request profiler-optimized NGen images only if it intends to use these callbacks to force a function to be compiled just-in-time (JIT).</span></span> <span data-ttu-id="d6c38-112">それ以外の場合、プロファイラーは関数情報を収集するためにレイジー戦略を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6c38-112">Otherwise, the profiler should use a lazy strategy for gathering function information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d6c38-113">要件</span><span class="sxs-lookup"><span data-stu-id="d6c38-113">Requirements</span></span>  
 <span data-ttu-id="d6c38-114">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d6c38-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6c38-115">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d6c38-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d6c38-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d6c38-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d6c38-117">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d6c38-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6c38-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="d6c38-118">See also</span></span>

- [<span data-ttu-id="d6c38-119">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d6c38-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
