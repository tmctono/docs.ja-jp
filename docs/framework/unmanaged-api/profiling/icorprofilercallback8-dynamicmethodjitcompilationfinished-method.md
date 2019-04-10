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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59206591"
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationfinished-method"></a><span data-ttu-id="897a8-102">ICorProfilerCallback8::DynamicMethodJITCompilationFinished メソッド</span><span class="sxs-lookup"><span data-stu-id="897a8-102">ICorProfilerCallback8::DynamicMethodJITCompilationFinished Method</span></span>
<span data-ttu-id="897a8-103">[.NET Framework 4.7 以降のバージョンでサポートされます]</span><span class="sxs-lookup"><span data-stu-id="897a8-103">[Supported in the .NET Framework 4.7 and later versions]</span></span>  
  
<span data-ttu-id="897a8-104">動的メソッドの JIT コンパイルが完了したときに、プロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="897a8-104">Notifies the profiler whenever JIT compilation of a dynamic method has completed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="897a8-105">構文</span><span class="sxs-lookup"><span data-stu-id="897a8-105">Syntax</span></span>  
  
```  
HRESULT DynamicMethodJITCompilationFinished(  
     [in]  FunctionID  functionId,   
     [in]  BOOL        hrStatus,   
     [in]  BOOL        fIsSafeToBlock   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="897a8-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="897a8-106">Parameters</span></span>  
<span data-ttu-id="897a8-107">[入力]</span><span class="sxs-lookup"><span data-stu-id="897a8-107">[in]</span></span> `functionId`  
<span data-ttu-id="897a8-108">どの JIT コンパイルが開始されてメモリ内の関数の識別子です。</span><span class="sxs-lookup"><span data-stu-id="897a8-108">The identifier of the in-memory function for which JIT compilation is started.</span></span>   

<span data-ttu-id="897a8-109">[入力]</span><span class="sxs-lookup"><span data-stu-id="897a8-109">[in]</span></span> `hrStatus`   
<span data-ttu-id="897a8-110">JIT コンパイルが成功したかどうかを示す値。</span><span class="sxs-lookup"><span data-stu-id="897a8-110">A value that indicates whether the JIT compilation was successful.</span></span>

<span data-ttu-id="897a8-111">[入力]</span><span class="sxs-lookup"><span data-stu-id="897a8-111">[in]</span></span> `fIsSafeToBlock`   
`true` <span data-ttu-id="897a8-112">ブロックしていることにより、ランタイムでこのコールバックから返される呼び出し元のスレッドを待機するかを示す`false`をブロックしてに影響しないこと、実行時の操作を示します。</span><span class="sxs-lookup"><span data-stu-id="897a8-112">to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span>  

## <a name="remarks"></a><span data-ttu-id="897a8-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="897a8-113">Remarks</span></span>  

<span data-ttu-id="897a8-114">動的メソッドの JIT コンパイルが完了するたびに、このコールバックがトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="897a8-114">This callback is triggered whenever JIT compilation of a dynamic method has finished.</span></span> <span data-ttu-id="897a8-115">これには、さまざまな IL スタブと LCG メソッドが含まれます。</span><span class="sxs-lookup"><span data-stu-id="897a8-115">This includes various IL stubs and LCG methods.</span></span> <span data-ttu-id="897a8-116">その目的はプロファイラー ライターをユーザーにコンパイルされたメソッドを識別するために十分な情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="897a8-116">Its goal is to provide profiler writers with enough information to identify the compiled method to users.</span></span>

> [!NOTE]
> `functionId` <span data-ttu-id="897a8-117">値は、動的メソッドのメタデータがないため、メタデータ トークンを解決するのには使用できません。</span><span class="sxs-lookup"><span data-stu-id="897a8-117">values cannot be used to resolve to their metadata tokens, because dynamic methods have no metadata.</span></span>

## <a name="requirements"></a><span data-ttu-id="897a8-118">必要条件</span><span class="sxs-lookup"><span data-stu-id="897a8-118">Requirements</span></span>  
 <span data-ttu-id="897a8-119">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="897a8-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="897a8-120">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="897a8-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="897a8-121">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="897a8-121">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="897a8-122">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="897a8-122">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  
  
## <a name="see-also"></a><span data-ttu-id="897a8-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="897a8-123">See also</span></span>

- [<span data-ttu-id="897a8-124">DynamicMethodJITCompilationStarted メソッド</span><span class="sxs-lookup"><span data-stu-id="897a8-124">DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [<span data-ttu-id="897a8-125">ICorProfilerCallback8 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="897a8-125">ICorProfilerCallback8 Interface</span></span>](icorprofilercallback8-interface.md)
