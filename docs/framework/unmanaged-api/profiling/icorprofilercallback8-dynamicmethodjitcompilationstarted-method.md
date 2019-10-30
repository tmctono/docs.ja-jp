---
title: ICorProfilerCallback8::D ynamicMethodJITCompilationStarted メソッド
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8.DynamicMethodJITCompilationStarted
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 1eaf29e1c93f352facde4af2ee57910783d82e5d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136464"
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationstarted-method"></a><span data-ttu-id="aaa3e-102">ICorProfilerCallback8::D ynamicMethodJITCompilationStarted メソッド</span><span class="sxs-lookup"><span data-stu-id="aaa3e-102">ICorProfilerCallback8::DynamicMethodJITCompilationStarted Method</span></span>
<span data-ttu-id="aaa3e-103">[.NET Framework 4.7 以降のバージョンでサポートされています]</span><span class="sxs-lookup"><span data-stu-id="aaa3e-103">[Supported in the .NET Framework 4.7 and later versions]</span></span>  
  
<span data-ttu-id="aaa3e-104">動的メソッドの JIT コンパイルが開始されるたびにプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="aaa3e-104">Notifies the profiler whenever JIT compilation of a dynamic method has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aaa3e-105">構文</span><span class="sxs-lookup"><span data-stu-id="aaa3e-105">Syntax</span></span>  
  
```cpp  
HRESULT DynamicMethodJITCompilationStarted(  
     [in]  FunctionID  functionId,   
     [in]  BOOL        fIsSafeToBlock,   
     [in]  LPCBYTE     pILHeader,   
     [in]  LONG        cbILHeader   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aaa3e-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="aaa3e-106">Parameters</span></span>  
<span data-ttu-id="aaa3e-107">[入力] `functionId`</span><span class="sxs-lookup"><span data-stu-id="aaa3e-107">[in] `functionId`</span></span>  
<span data-ttu-id="aaa3e-108">JIT コンパイルが開始されるメモリ内関数の識別子。</span><span class="sxs-lookup"><span data-stu-id="aaa3e-108">The identifier of the in-memory function for which JIT compilation is started.</span></span>   

<span data-ttu-id="aaa3e-109">[入力] `fIsSafeToBlock` </span><span class="sxs-lookup"><span data-stu-id="aaa3e-109">[in] `fIsSafeToBlock` </span></span>  
<span data-ttu-id="aaa3e-110">ブロックによって、呼び出し元のスレッドがこのコールバックから戻るまでランタイムが待機する可能性があることを示す `true` ます。`false` は、ブロックがランタイムの操作に影響を与えないことを示します。</span><span class="sxs-lookup"><span data-stu-id="aaa3e-110">`true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span>  

<span data-ttu-id="aaa3e-111">[入力] `pILHeader`  </span><span class="sxs-lookup"><span data-stu-id="aaa3e-111">[in] `pILHeader`  </span></span>  
<span data-ttu-id="aaa3e-112">メソッドの IL ヘッダーの最初のバイトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="aaa3e-112">A pointer to the first byte of the method's IL header.</span></span>   

<span data-ttu-id="aaa3e-113">[入力] `cbILHeader`  </span><span class="sxs-lookup"><span data-stu-id="aaa3e-113">[in] `cbILHeader`  </span></span>  
<span data-ttu-id="aaa3e-114">IL ヘッダー内のバイト数。</span><span class="sxs-lookup"><span data-stu-id="aaa3e-114">The number of bytes in the IL header.</span></span> 

## <a name="remarks"></a><span data-ttu-id="aaa3e-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="aaa3e-115">Remarks</span></span>  

<span data-ttu-id="aaa3e-116">このコールバックは、動的メソッドが JIT コンパイルされるたびにトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="aaa3e-116">This callback is triggered whenever a dynamic method is JIT-compiled.</span></span> <span data-ttu-id="aaa3e-117">これには、さまざまな IL スタブおよび LCG メソッドが含まれます。</span><span class="sxs-lookup"><span data-stu-id="aaa3e-117">This includes various IL stubs and LCG methods.</span></span> <span data-ttu-id="aaa3e-118">その目的は、コンパイルされたメソッドをユーザーに識別するのに十分な情報をプロファイラーライターに提供することです。</span><span class="sxs-lookup"><span data-stu-id="aaa3e-118">Its goal is to provide profiler writers with enough information to identify the compiled method to users.</span></span>

> [!NOTE]
> <span data-ttu-id="aaa3e-119">動的メソッドにはメタデータがないため、`functionId` 値を使用してメタデータトークンに解決することはできません。</span><span class="sxs-lookup"><span data-stu-id="aaa3e-119">`functionId` values cannot be used to resolve to their metadata tokens, because dynamic methods have no metadata.</span></span>

<span data-ttu-id="aaa3e-120">`pILHeader` ポインターは、コールバック中にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="aaa3e-120">The `pILHeader` pointer is only valid during the callback.</span></span>

## <a name="requirements"></a><span data-ttu-id="aaa3e-121">［要件］</span><span class="sxs-lookup"><span data-stu-id="aaa3e-121">Requirements</span></span>  
 <span data-ttu-id="aaa3e-122">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aaa3e-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aaa3e-123">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="aaa3e-123">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="aaa3e-124">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="aaa3e-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="aaa3e-125">**.NET Framework のバージョン:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="aaa3e-125">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aaa3e-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="aaa3e-126">See also</span></span>

- [<span data-ttu-id="aaa3e-127">DynamicMethodJITCompilationFinished メソッド</span><span class="sxs-lookup"><span data-stu-id="aaa3e-127">DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
- [<span data-ttu-id="aaa3e-128">ICorProfilerCallback8 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="aaa3e-128">ICorProfilerCallback8 Interface</span></span>](icorprofilercallback8-interface.md)
