---
title: メソッドを :D終了しました。
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8.DynamicMethodJITCompilationFinished
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: c2e9489654a0fe5fa65ec638ed0f991a6c01415a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175110"
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationfinished-method"></a><span data-ttu-id="23bad-102">メソッドを :D終了しました。</span><span class="sxs-lookup"><span data-stu-id="23bad-102">ICorProfilerCallback8::DynamicMethodJITCompilationFinished Method</span></span>
<span data-ttu-id="23bad-103">[.NET Framework 4.7 以降のバージョンでサポートされています]</span><span class="sxs-lookup"><span data-stu-id="23bad-103">[Supported in the .NET Framework 4.7 and later versions]</span></span>  
  
<span data-ttu-id="23bad-104">動的メソッドの JIT コンパイルが完了するたびにプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="23bad-104">Notifies the profiler whenever JIT compilation of a dynamic method has completed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23bad-105">構文</span><span class="sxs-lookup"><span data-stu-id="23bad-105">Syntax</span></span>  
  
```cpp  
HRESULT DynamicMethodJITCompilationFinished(  
     [in]  FunctionID  functionId,
     [in]  BOOL        hrStatus,
     [in]  BOOL        fIsSafeToBlock
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="23bad-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="23bad-106">Parameters</span></span>  
<span data-ttu-id="23bad-107">[入力] `functionId`</span><span class="sxs-lookup"><span data-stu-id="23bad-107">[in] `functionId`</span></span>  
<span data-ttu-id="23bad-108">JIT コンパイルを開始するインメモリ関数の識別子。</span><span class="sxs-lookup"><span data-stu-id="23bad-108">The identifier of the in-memory function for which JIT compilation is started.</span></span>

<span data-ttu-id="23bad-109">[in]`hrStatus` JIT コンパイルが成功したかどうかを示す値。</span><span class="sxs-lookup"><span data-stu-id="23bad-109">[in] `hrStatus` A value that indicates whether the JIT compilation was successful.</span></span>

<span data-ttu-id="23bad-110">[in]`fIsSafeToBlock`をクリックすると、呼び出し元のスレッドがこのコールバックから返されるのをランタイムが待機する可能性があることを示
`true`します。`false`ブロックがランタイムの操作に影響しないことを示します。</span><span class="sxs-lookup"><span data-stu-id="23bad-110">[in] `fIsSafeToBlock`
`true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span>  

## <a name="remarks"></a><span data-ttu-id="23bad-111">解説</span><span class="sxs-lookup"><span data-stu-id="23bad-111">Remarks</span></span>  

<span data-ttu-id="23bad-112">このコールバックは、動的メソッドの JIT コンパイルが終了するたびにトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="23bad-112">This callback is triggered whenever JIT compilation of a dynamic method has finished.</span></span> <span data-ttu-id="23bad-113">これには、さまざまな IL スタブと LCG メソッドが含まれます。</span><span class="sxs-lookup"><span data-stu-id="23bad-113">This includes various IL stubs and LCG methods.</span></span> <span data-ttu-id="23bad-114">その目的は、プロファイラーの作成者に、コンパイルされたメソッドを識別するための十分な情報をユーザーに提供することです。</span><span class="sxs-lookup"><span data-stu-id="23bad-114">Its goal is to provide profiler writers with enough information to identify the compiled method to users.</span></span>

> [!NOTE]
> <span data-ttu-id="23bad-115">`functionId`動的メソッドにはメタデータがないため、値をメタデータ トークンに解決するために使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="23bad-115">`functionId` values cannot be used to resolve to their metadata tokens, because dynamic methods have no metadata.</span></span>

## <a name="requirements"></a><span data-ttu-id="23bad-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="23bad-116">Requirements</span></span>  
 <span data-ttu-id="23bad-117">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="23bad-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23bad-118">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="23bad-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="23bad-119">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="23bad-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="23bad-120">**.NET Framework のバージョン:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="23bad-120">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23bad-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="23bad-121">See also</span></span>

- [<span data-ttu-id="23bad-122">DynamicMethodJITCompilationStarted メソッド</span><span class="sxs-lookup"><span data-stu-id="23bad-122">DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [<span data-ttu-id="23bad-123">ICorProfilerCallback8 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="23bad-123">ICorProfilerCallback8 Interface</span></span>](icorprofilercallback8-interface.md)
