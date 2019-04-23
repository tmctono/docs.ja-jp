---
title: ICorProfilerCallback8::DynamicMethodJITCompilationFinished メソッド
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8.DynamicMethodJITCompilationFinished
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9dbe8d4f7050b93ffb34280be6d63367ef294ae8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59206591"
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationfinished-method"></a><span data-ttu-id="76ce4-102">ICorProfilerCallback8::DynamicMethodJITCompilationFinished メソッド</span><span class="sxs-lookup"><span data-stu-id="76ce4-102">ICorProfilerCallback8::DynamicMethodJITCompilationFinished Method</span></span>
<span data-ttu-id="76ce4-103">[.NET Framework 4.7 以降のバージョンでサポートされます]</span><span class="sxs-lookup"><span data-stu-id="76ce4-103">[Supported in the .NET Framework 4.7 and later versions]</span></span>  
  
<span data-ttu-id="76ce4-104">動的メソッドの JIT コンパイルが完了したときに、プロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="76ce4-104">Notifies the profiler whenever JIT compilation of a dynamic method has completed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76ce4-105">構文</span><span class="sxs-lookup"><span data-stu-id="76ce4-105">Syntax</span></span>  
  
```  
HRESULT DynamicMethodJITCompilationFinished(  
     [in]  FunctionID  functionId,   
     [in]  BOOL        hrStatus,   
     [in]  BOOL        fIsSafeToBlock   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="76ce4-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="76ce4-106">Parameters</span></span>  
<span data-ttu-id="76ce4-107">[入力] `functionId`</span><span class="sxs-lookup"><span data-stu-id="76ce4-107">[in] `functionId`</span></span>  
<span data-ttu-id="76ce4-108">どの JIT コンパイルが開始されてメモリ内の関数の識別子です。</span><span class="sxs-lookup"><span data-stu-id="76ce4-108">The identifier of the in-memory function for which JIT compilation is started.</span></span>   

<span data-ttu-id="76ce4-109">[in] `hrStatus` </span><span class="sxs-lookup"><span data-stu-id="76ce4-109">[in] `hrStatus` </span></span>  
<span data-ttu-id="76ce4-110">JIT コンパイルが成功したかどうかを示す値。</span><span class="sxs-lookup"><span data-stu-id="76ce4-110">A value that indicates whether the JIT compilation was successful.</span></span>

<span data-ttu-id="76ce4-111">[in] `fIsSafeToBlock` </span><span class="sxs-lookup"><span data-stu-id="76ce4-111">[in] `fIsSafeToBlock` </span></span>  
<span data-ttu-id="76ce4-112">`true` ブロックしていることにより、ランタイムでこのコールバックから返される呼び出し元のスレッドを待機するかを示す`false`をブロックしてに影響しないこと、実行時の操作を示します。</span><span class="sxs-lookup"><span data-stu-id="76ce4-112">`true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span>  

## <a name="remarks"></a><span data-ttu-id="76ce4-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="76ce4-113">Remarks</span></span>  

<span data-ttu-id="76ce4-114">動的メソッドの JIT コンパイルが完了するたびに、このコールバックがトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="76ce4-114">This callback is triggered whenever JIT compilation of a dynamic method has finished.</span></span> <span data-ttu-id="76ce4-115">これには、さまざまな IL スタブと LCG メソッドが含まれます。</span><span class="sxs-lookup"><span data-stu-id="76ce4-115">This includes various IL stubs and LCG methods.</span></span> <span data-ttu-id="76ce4-116">その目的はプロファイラー ライターをユーザーにコンパイルされたメソッドを識別するために十分な情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="76ce4-116">Its goal is to provide profiler writers with enough information to identify the compiled method to users.</span></span>

> [!NOTE]
> <span data-ttu-id="76ce4-117">`functionId` 値は、動的メソッドのメタデータがないため、メタデータ トークンを解決するのには使用できません。</span><span class="sxs-lookup"><span data-stu-id="76ce4-117">`functionId` values cannot be used to resolve to their metadata tokens, because dynamic methods have no metadata.</span></span>

## <a name="requirements"></a><span data-ttu-id="76ce4-118">必要条件</span><span class="sxs-lookup"><span data-stu-id="76ce4-118">Requirements</span></span>  
 <span data-ttu-id="76ce4-119">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="76ce4-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="76ce4-120">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="76ce4-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="76ce4-121">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="76ce4-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="76ce4-122">**.NET Framework のバージョン:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="76ce4-122">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76ce4-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="76ce4-123">See also</span></span>

- [<span data-ttu-id="76ce4-124">DynamicMethodJITCompilationStarted メソッド</span><span class="sxs-lookup"><span data-stu-id="76ce4-124">DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [<span data-ttu-id="76ce4-125">ICorProfilerCallback8 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="76ce4-125">ICorProfilerCallback8 Interface</span></span>](icorprofilercallback8-interface.md)
