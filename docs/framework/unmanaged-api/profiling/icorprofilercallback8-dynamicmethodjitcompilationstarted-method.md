---
title: ICorProfilerCallback8::DynamicMethodJITCompilationStarted メソッド
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8.DynamicMethodJITCompilationStarted
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c4b8bffeb71497a7dd8e2ed25b833f9216d8017e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62049740"
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationstarted-method"></a><span data-ttu-id="a6447-102">ICorProfilerCallback8::DynamicMethodJITCompilationStarted メソッド</span><span class="sxs-lookup"><span data-stu-id="a6447-102">ICorProfilerCallback8::DynamicMethodJITCompilationStarted Method</span></span>
<span data-ttu-id="a6447-103">[.NET Framework 4.7 以降のバージョンでサポートされます]</span><span class="sxs-lookup"><span data-stu-id="a6447-103">[Supported in the .NET Framework 4.7 and later versions]</span></span>  
  
<span data-ttu-id="a6447-104">動的メソッドの JIT コンパイルが開始されるたびに、プロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="a6447-104">Notifies the profiler whenever JIT compilation of a dynamic method has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6447-105">構文</span><span class="sxs-lookup"><span data-stu-id="a6447-105">Syntax</span></span>  
  
```  
HRESULT DynamicMethodJITCompilationStarted(  
     [in]  FunctionID  functionId,   
     [in]  BOOL        fIsSafeToBlock,   
     [in]  LPCBYTE     pILHeader,   
     [in]  LONG        cbILHeader   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a6447-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a6447-106">Parameters</span></span>  
<span data-ttu-id="a6447-107">[入力] `functionId`</span><span class="sxs-lookup"><span data-stu-id="a6447-107">[in] `functionId`</span></span>  
<span data-ttu-id="a6447-108">どの JIT コンパイルが開始されてメモリ内の関数の識別子です。</span><span class="sxs-lookup"><span data-stu-id="a6447-108">The identifier of the in-memory function for which JIT compilation is started.</span></span>   

<span data-ttu-id="a6447-109">[in] `fIsSafeToBlock` </span><span class="sxs-lookup"><span data-stu-id="a6447-109">[in] `fIsSafeToBlock` </span></span>  
<span data-ttu-id="a6447-110">`true` ブロックしていることにより、ランタイムでこのコールバックから返される呼び出し元のスレッドを待機するかを示す`false`をブロックしてに影響しないこと、実行時の操作を示します。</span><span class="sxs-lookup"><span data-stu-id="a6447-110">`true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span>  

<span data-ttu-id="a6447-111">[in] `pILHeader`  </span><span class="sxs-lookup"><span data-stu-id="a6447-111">[in] `pILHeader`  </span></span>  
<span data-ttu-id="a6447-112">メソッドの IL のヘッダーの最初のバイトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="a6447-112">A pointer to the first byte of the method's IL header.</span></span>   

<span data-ttu-id="a6447-113">[in] `cbILHeader`  </span><span class="sxs-lookup"><span data-stu-id="a6447-113">[in] `cbILHeader`  </span></span>  
<span data-ttu-id="a6447-114">IL ヘッダーのバイト数。</span><span class="sxs-lookup"><span data-stu-id="a6447-114">The number of bytes in the IL header.</span></span> 

## <a name="remarks"></a><span data-ttu-id="a6447-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="a6447-115">Remarks</span></span>  

<span data-ttu-id="a6447-116">動的メソッドが JIT コンパイルされるたびに、このコールバックがトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="a6447-116">This callback is triggered whenever a dynamic method is JIT-compiled.</span></span> <span data-ttu-id="a6447-117">これには、さまざまな IL スタブと LCG メソッドが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a6447-117">This includes various IL stubs and LCG methods.</span></span> <span data-ttu-id="a6447-118">その目的はプロファイラー ライターをユーザーにコンパイルされたメソッドを識別するために十分な情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="a6447-118">Its goal is to provide profiler writers with enough information to identify the compiled method to users.</span></span>

> [!NOTE]
> <span data-ttu-id="a6447-119">`functionId` 値は、動的メソッドのメタデータがないため、メタデータ トークンを解決するのには使用できません。</span><span class="sxs-lookup"><span data-stu-id="a6447-119">`functionId` values cannot be used to resolve to their metadata tokens, because dynamic methods have no metadata.</span></span>

<span data-ttu-id="a6447-120">`pILHeader`ポインターは、コールバック中にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="a6447-120">The `pILHeader` pointer is only valid during the callback.</span></span>

## <a name="requirements"></a><span data-ttu-id="a6447-121">必要条件</span><span class="sxs-lookup"><span data-stu-id="a6447-121">Requirements</span></span>  
 <span data-ttu-id="a6447-122">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6447-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6447-123">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a6447-123">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a6447-124">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a6447-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a6447-125">**.NET Framework のバージョン:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="a6447-125">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6447-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="a6447-126">See also</span></span>

- [<span data-ttu-id="a6447-127">DynamicMethodJITCompilationFinished メソッド</span><span class="sxs-lookup"><span data-stu-id="a6447-127">DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
- [<span data-ttu-id="a6447-128">ICorProfilerCallback8 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a6447-128">ICorProfilerCallback8 Interface</span></span>](icorprofilercallback8-interface.md)
