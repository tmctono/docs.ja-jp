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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4b0e78e10f092bce1c8f7762362f02b7a403c86a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61597252"
---
# <a name="icorprofilercallbackjitcachedfunctionsearchfinished-method"></a><span data-ttu-id="5f00f-102">ICorProfilerCallback::JITCachedFunctionSearchFinished メソッド</span><span class="sxs-lookup"><span data-stu-id="5f00f-102">ICorProfilerCallback::JITCachedFunctionSearchFinished Method</span></span>
<span data-ttu-id="5f00f-103">ネイティブ イメージ ジェネレーター (NGen.exe) を使用して以前にコンパイルされた関数の検索が完了したことをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="5f00f-103">Notifies the profiler that a search has finished for a function that was compiled previously using the Native Image Generator (NGen.exe).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f00f-104">構文</span><span class="sxs-lookup"><span data-stu-id="5f00f-104">Syntax</span></span>  
  
```  
HRESULT JITCachedFunctionSearchFinished(  
    [in] FunctionID        functionId,  
    [in] COR_PRF_JIT_CACHE result);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5f00f-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5f00f-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="5f00f-106">[in]検索の実行対象の関数の ID。</span><span class="sxs-lookup"><span data-stu-id="5f00f-106">[in] The ID of the function for which the search was performed.</span></span>  
  
 `result`  
 <span data-ttu-id="5f00f-107">[in]値、 [COR_PRF_JIT_CACHE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-jit-cache-enumeration.md)検索の結果を示す列挙体。</span><span class="sxs-lookup"><span data-stu-id="5f00f-107">[in] A value of the [COR_PRF_JIT_CACHE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-jit-cache-enumeration.md) enumeration that indicates the result of the search.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5f00f-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="5f00f-108">Remarks</span></span>  
 <span data-ttu-id="5f00f-109">.NET Framework version 2.0 で、 [icorprofilercallback::jitcachedfunctionsearchstarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcachedfunctionsearchstarted-method.md)と`JITCachedFunctionSearchFinished`正規の NGen イメージのすべての関数のコールバックは行われません。</span><span class="sxs-lookup"><span data-stu-id="5f00f-109">In the .NET Framework version 2.0, the [ICorProfilerCallback::JITCachedFunctionSearchStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcachedfunctionsearchstarted-method.md) and `JITCachedFunctionSearchFinished` callbacks will not be made for all functions in regular NGen images.</span></span> <span data-ttu-id="5f00f-110">プロファイラー用に最適化された NGen イメージだけでは、イメージのすべての関数のコールバックが生成されます。</span><span class="sxs-lookup"><span data-stu-id="5f00f-110">Only NGen images optimized for a profiler will generate callbacks for all functions in the image.</span></span> <span data-ttu-id="5f00f-111">ただし、追加のオーバーヘッドが原因で、プロファイラー NGen イメージのプロファイラーを最適化する必要があります要求した場合、関数のコンパイル済みの just-in-time (JIT) を強制的にこれらのコールバックを使用する場合にのみにします。</span><span class="sxs-lookup"><span data-stu-id="5f00f-111">However, due to the additional overhead, a profiler should request profiler-optimized NGen images only if it intends to use these callbacks to force a function to be compiled just-in-time (JIT).</span></span> <span data-ttu-id="5f00f-112">それ以外の場合、プロファイラーは、関数の情報を収集するため、遅延の戦略を使用してください。</span><span class="sxs-lookup"><span data-stu-id="5f00f-112">Otherwise, the profiler should use a lazy strategy for gathering function information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f00f-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="5f00f-113">Requirements</span></span>  
 <span data-ttu-id="5f00f-114">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5f00f-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f00f-115">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5f00f-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5f00f-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5f00f-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5f00f-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f00f-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f00f-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="5f00f-118">See also</span></span>

- [<span data-ttu-id="5f00f-119">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5f00f-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
