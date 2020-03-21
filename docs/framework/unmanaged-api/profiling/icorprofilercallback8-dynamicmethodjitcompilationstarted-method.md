---
title: メソッドを開始 :Dしました。
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8.DynamicMethodJITCompilationStarted
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: e8b1a243b691d8d5eb364fd16821fd9156505c60
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177047"
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationstarted-method"></a><span data-ttu-id="b8d90-102">メソッドを開始 :Dしました。</span><span class="sxs-lookup"><span data-stu-id="b8d90-102">ICorProfilerCallback8::DynamicMethodJITCompilationStarted Method</span></span>
<span data-ttu-id="b8d90-103">[.NET Framework 4.7 以降のバージョンでサポートされています]</span><span class="sxs-lookup"><span data-stu-id="b8d90-103">[Supported in the .NET Framework 4.7 and later versions]</span></span>  
  
<span data-ttu-id="b8d90-104">動的メソッドの JIT コンパイルが開始されるたびにプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="b8d90-104">Notifies the profiler whenever JIT compilation of a dynamic method has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8d90-105">構文</span><span class="sxs-lookup"><span data-stu-id="b8d90-105">Syntax</span></span>  
  
```cpp  
HRESULT DynamicMethodJITCompilationStarted(  
     [in]  FunctionID  functionId,
     [in]  BOOL        fIsSafeToBlock,
     [in]  LPCBYTE     pILHeader,
     [in]  LONG        cbILHeader
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b8d90-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b8d90-106">Parameters</span></span>  
<span data-ttu-id="b8d90-107">[入力] `functionId`</span><span class="sxs-lookup"><span data-stu-id="b8d90-107">[in] `functionId`</span></span>  
<span data-ttu-id="b8d90-108">JIT コンパイルを開始するインメモリ関数の識別子。</span><span class="sxs-lookup"><span data-stu-id="b8d90-108">The identifier of the in-memory function for which JIT compilation is started.</span></span>

<span data-ttu-id="b8d90-109">[in]`fIsSafeToBlock`をクリックすると、呼び出し元のスレッドがこのコールバックから返されるのをランタイムが待機する可能性があることを示
`true`します。`false`ブロックがランタイムの操作に影響しないことを示します。</span><span class="sxs-lookup"><span data-stu-id="b8d90-109">[in] `fIsSafeToBlock`
`true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span>  

<span data-ttu-id="b8d90-110">[in]`pILHeader`メソッドの IL ヘッダーの最初のバイトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="b8d90-110">[in] `pILHeader` A pointer to the first byte of the method's IL header.</span></span>

<span data-ttu-id="b8d90-111">[in]`cbILHeader` IL ヘッダーのバイト数。</span><span class="sxs-lookup"><span data-stu-id="b8d90-111">[in] `cbILHeader` The number of bytes in the IL header.</span></span>

## <a name="remarks"></a><span data-ttu-id="b8d90-112">解説</span><span class="sxs-lookup"><span data-stu-id="b8d90-112">Remarks</span></span>  

<span data-ttu-id="b8d90-113">このコールバックは、動的メソッドが JIT コンパイルされたときにトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="b8d90-113">This callback is triggered whenever a dynamic method is JIT-compiled.</span></span> <span data-ttu-id="b8d90-114">これには、さまざまな IL スタブと LCG メソッドが含まれます。</span><span class="sxs-lookup"><span data-stu-id="b8d90-114">This includes various IL stubs and LCG methods.</span></span> <span data-ttu-id="b8d90-115">その目的は、プロファイラーの作成者に、コンパイルされたメソッドを識別するための十分な情報をユーザーに提供することです。</span><span class="sxs-lookup"><span data-stu-id="b8d90-115">Its goal is to provide profiler writers with enough information to identify the compiled method to users.</span></span>

> [!NOTE]
> <span data-ttu-id="b8d90-116">`functionId`動的メソッドにはメタデータがないため、値をメタデータ トークンに解決するために使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="b8d90-116">`functionId` values cannot be used to resolve to their metadata tokens, because dynamic methods have no metadata.</span></span>

<span data-ttu-id="b8d90-117">ポインター`pILHeader`はコールバック中にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="b8d90-117">The `pILHeader` pointer is only valid during the callback.</span></span>

## <a name="requirements"></a><span data-ttu-id="b8d90-118">必要条件</span><span class="sxs-lookup"><span data-stu-id="b8d90-118">Requirements</span></span>  
 <span data-ttu-id="b8d90-119">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b8d90-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8d90-120">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b8d90-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b8d90-121">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b8d90-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b8d90-122">**.NET Framework のバージョン:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b8d90-122">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8d90-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="b8d90-123">See also</span></span>

- [<span data-ttu-id="b8d90-124">DynamicMethodJITCompilationFinished メソッド</span><span class="sxs-lookup"><span data-stu-id="b8d90-124">DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
- [<span data-ttu-id="b8d90-125">ICorProfilerCallback8 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b8d90-125">ICorProfilerCallback8 Interface</span></span>](icorprofilercallback8-interface.md)
