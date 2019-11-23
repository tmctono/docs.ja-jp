---
title: ICorProfilerCallback8::D ynamicMethodJITCompilationFinished メソッド
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8.DynamicMethodJITCompilationFinished
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 0e04459614ca697908fb9b71ecc3931ac305a838
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136581"
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationfinished-method"></a><span data-ttu-id="2386e-102">ICorProfilerCallback8::D ynamicMethodJITCompilationFinished メソッド</span><span class="sxs-lookup"><span data-stu-id="2386e-102">ICorProfilerCallback8::DynamicMethodJITCompilationFinished Method</span></span>
<span data-ttu-id="2386e-103">[.NET Framework 4.7 以降のバージョンでサポートされています]</span><span class="sxs-lookup"><span data-stu-id="2386e-103">[Supported in the .NET Framework 4.7 and later versions]</span></span>  
  
<span data-ttu-id="2386e-104">動的メソッドの JIT コンパイルが完了するたびにプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="2386e-104">Notifies the profiler whenever JIT compilation of a dynamic method has completed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2386e-105">構文</span><span class="sxs-lookup"><span data-stu-id="2386e-105">Syntax</span></span>  
  
```cpp  
HRESULT DynamicMethodJITCompilationFinished(  
     [in]  FunctionID  functionId,   
     [in]  BOOL        hrStatus,   
     [in]  BOOL        fIsSafeToBlock   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2386e-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2386e-106">Parameters</span></span>  
<span data-ttu-id="2386e-107">[入力] `functionId`</span><span class="sxs-lookup"><span data-stu-id="2386e-107">[in] `functionId`</span></span>  
<span data-ttu-id="2386e-108">JIT コンパイルが開始されるメモリ内関数の識別子。</span><span class="sxs-lookup"><span data-stu-id="2386e-108">The identifier of the in-memory function for which JIT compilation is started.</span></span>   

<span data-ttu-id="2386e-109">[入力] `hrStatus` </span><span class="sxs-lookup"><span data-stu-id="2386e-109">[in] `hrStatus` </span></span>  
<span data-ttu-id="2386e-110">JIT コンパイルが成功したかどうかを示す値。</span><span class="sxs-lookup"><span data-stu-id="2386e-110">A value that indicates whether the JIT compilation was successful.</span></span>

<span data-ttu-id="2386e-111">[入力] `fIsSafeToBlock` </span><span class="sxs-lookup"><span data-stu-id="2386e-111">[in] `fIsSafeToBlock` </span></span>  
<span data-ttu-id="2386e-112">ブロックによって、呼び出し元のスレッドがこのコールバックから戻るまでランタイムが待機する可能性があることを示す `true` ます。`false` は、ブロックがランタイムの操作に影響を与えないことを示します。</span><span class="sxs-lookup"><span data-stu-id="2386e-112">`true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span>  

## <a name="remarks"></a><span data-ttu-id="2386e-113">コメント</span><span class="sxs-lookup"><span data-stu-id="2386e-113">Remarks</span></span>  

<span data-ttu-id="2386e-114">このコールバックは、動的メソッドの JIT コンパイルが完了するたびにトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="2386e-114">This callback is triggered whenever JIT compilation of a dynamic method has finished.</span></span> <span data-ttu-id="2386e-115">これには、さまざまな IL スタブおよび LCG メソッドが含まれます。</span><span class="sxs-lookup"><span data-stu-id="2386e-115">This includes various IL stubs and LCG methods.</span></span> <span data-ttu-id="2386e-116">その目的は、コンパイルされたメソッドをユーザーに識別するのに十分な情報をプロファイラーライターに提供することです。</span><span class="sxs-lookup"><span data-stu-id="2386e-116">Its goal is to provide profiler writers with enough information to identify the compiled method to users.</span></span>

> [!NOTE]
> <span data-ttu-id="2386e-117">動的メソッドにはメタデータがないため、`functionId` 値を使用してメタデータトークンに解決することはできません。</span><span class="sxs-lookup"><span data-stu-id="2386e-117">`functionId` values cannot be used to resolve to their metadata tokens, because dynamic methods have no metadata.</span></span>

## <a name="requirements"></a><span data-ttu-id="2386e-118">要件</span><span class="sxs-lookup"><span data-stu-id="2386e-118">Requirements</span></span>  
 <span data-ttu-id="2386e-119">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2386e-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2386e-120">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2386e-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2386e-121">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2386e-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2386e-122">**.NET Framework のバージョン:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="2386e-122">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2386e-123">参照</span><span class="sxs-lookup"><span data-stu-id="2386e-123">See also</span></span>

- [<span data-ttu-id="2386e-124">DynamicMethodJITCompilationStarted メソッド</span><span class="sxs-lookup"><span data-stu-id="2386e-124">DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [<span data-ttu-id="2386e-125">ICorProfilerCallback8 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2386e-125">ICorProfilerCallback8 Interface</span></span>](icorprofilercallback8-interface.md)
