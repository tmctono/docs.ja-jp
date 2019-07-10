---
title: ICorProfilerCallback4::ReJITError メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback4.ReJITError
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4::ReJITError
helpviewer_keywords:
- ReJITError method, ICorProfilerCallback4 interface [.NET Framework profiling]
- ICorProfilerCallback4::ReJITError method [.NET Framework profiling]
ms.assetid: d7888aa9-dfaa-420f-9f99-e06ab35ca482
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6b01f38fbcf1cb0439b82a933b37971515b06ac4
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67758147"
---
# <a name="icorprofilercallback4rejiterror-method"></a><span data-ttu-id="71153-102">ICorProfilerCallback4::ReJITError メソッド</span><span class="sxs-lookup"><span data-stu-id="71153-102">ICorProfilerCallback4::ReJITError Method</span></span>
<span data-ttu-id="71153-103">ジャストイン タイム (JIT) コンパイラに再コンパイル プロセスでエラーが発生したことをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="71153-103">Notifies the profiler that the just-in-time (JIT) compiler encountered an error in the recompilation process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71153-104">構文</span><span class="sxs-lookup"><span data-stu-id="71153-104">Syntax</span></span>  
  
```cpp  
HRESULT ReJITError(  
    [in] ModuleID    moduleId,  
    [in] mdMethodDef methodId,  
    [in] FunctionID  functionId,  
    [in] HRESULT     hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="71153-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="71153-105">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="71153-106">[in]`ModuleID`再コンパイルが失敗した試行が行われる。</span><span class="sxs-lookup"><span data-stu-id="71153-106">[in] The `ModuleID` in which the failed recompilation attempt was made.</span></span>  
  
 `methodId`  
 <span data-ttu-id="71153-107">[in]`MethodDef`の再コンパイルが失敗した試行が行われたメソッド。</span><span class="sxs-lookup"><span data-stu-id="71153-107">[in] The `MethodDef` of the method on which the failed recompilation attempt was made.</span></span>  
  
 `functionId`  
 <span data-ttu-id="71153-108">[in]再コンパイルされたまたはマークの再コンパイルされている関数のインスタンス。</span><span class="sxs-lookup"><span data-stu-id="71153-108">[in] The function instance that is being recompiled or marked for recompilation.</span></span> <span data-ttu-id="71153-109">この値は、 `NULL` (たとえば、プロファイラーには、再コンパイルするメソッドを無効なメタデータ トークンが指定された) 場合、インスタンス化ごとにではなく、メソッドごとに障害が発生したかどうか。</span><span class="sxs-lookup"><span data-stu-id="71153-109">This value may be `NULL` if the failure occurred on a per-method basis instead of a per-instantiation basis (for example, if the profiler specified an invalid metadata token for the method to be recompiled).</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="71153-110">[in]エラーの性質を示す HRESULT。</span><span class="sxs-lookup"><span data-stu-id="71153-110">[in] An HRESULT that indicates the nature of the failure.</span></span> <span data-ttu-id="71153-111">値の一覧については、状態 HRESULT」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="71153-111">See the Status HRESULTS section for a list of values.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="71153-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="71153-112">Return Value</span></span>  
 <span data-ttu-id="71153-113">このコールバックからの戻り値は無視されます。</span><span class="sxs-lookup"><span data-stu-id="71153-113">Return values from this callback are ignored.</span></span>  
  
## <a name="status-hresults"></a><span data-ttu-id="71153-114">状態 HRESULT</span><span class="sxs-lookup"><span data-stu-id="71153-114">Status HRESULTS</span></span>  
  
|<span data-ttu-id="71153-115">状態配列 HRESULT</span><span class="sxs-lookup"><span data-stu-id="71153-115">Status array HRESULT</span></span>|<span data-ttu-id="71153-116">説明</span><span class="sxs-lookup"><span data-stu-id="71153-116">Description</span></span>|  
|--------------------------|-----------------|  
|<span data-ttu-id="71153-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="71153-117">E_INVALIDARG</span></span>|<span data-ttu-id="71153-118">`moduleID`または`methodDef`トークンが`NULL`します。</span><span class="sxs-lookup"><span data-stu-id="71153-118">The `moduleID` or `methodDef` token is `NULL`.</span></span>|  
|<span data-ttu-id="71153-119">CORPROF_E_DATAINCOMPLETE</span><span class="sxs-lookup"><span data-stu-id="71153-119">CORPROF_E_DATAINCOMPLETE</span></span>|<span data-ttu-id="71153-120">モジュールが完全に読み込まれていないか、またはアンロード中です。</span><span class="sxs-lookup"><span data-stu-id="71153-120">The module is not fully loaded yet, or it is in the process of being unloaded.</span></span>|  
|<span data-ttu-id="71153-121">CORPROF_E_MODULE_IS_DYNAMIC</span><span class="sxs-lookup"><span data-stu-id="71153-121">CORPROF_E_MODULE_IS_DYNAMIC</span></span>|<span data-ttu-id="71153-122">指定したモジュールを動的に生成されました (たとえば、 `Reflection.Emit`) はこのメソッドによってサポートされていませんので。</span><span class="sxs-lookup"><span data-stu-id="71153-122">The specified module was dynamically generated (for example, by `Reflection.Emit`), and is thus not supported by this method.</span></span>|  
|<span data-ttu-id="71153-123">CORPROF_E_FUNCTION_IS_COLLECTIBLE</span><span class="sxs-lookup"><span data-stu-id="71153-123">CORPROF_E_FUNCTION_IS_COLLECTIBLE</span></span>|<span data-ttu-id="71153-124">メソッドは、収集可能なアセンブリにインスタンス化であるため再コンパイルすることができません。</span><span class="sxs-lookup"><span data-stu-id="71153-124">The method is instantiated into a collectible assembly, and is therefore not able to be recompiled.</span></span> <span data-ttu-id="71153-125">型に注意してくださいと非リフレクション コンテキストで定義されている関数 (たとえば、 `List<MyCollectibleStruct>`) 収集可能なアセンブリにインスタンス化することができます。</span><span class="sxs-lookup"><span data-stu-id="71153-125">Note that types and functions defined in a non-reflection context (for example, `List<MyCollectibleStruct>`) can be instantiated into a collectible assembly.</span></span>|  
|<span data-ttu-id="71153-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="71153-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="71153-127">CLR は JIT 再コンパイルの指定したメソッドをマークしているときにメモリ不足になりました。</span><span class="sxs-lookup"><span data-stu-id="71153-127">The CLR ran out of memory while trying to mark the specified method for JIT recompilation.</span></span>|  
|<span data-ttu-id="71153-128">Other</span><span class="sxs-lookup"><span data-stu-id="71153-128">Other</span></span>|<span data-ttu-id="71153-129">オペレーティング システムは、CLR 制御範囲外のエラーを返しました。</span><span class="sxs-lookup"><span data-stu-id="71153-129">The operating system returned a failure outside the control of the CLR.</span></span> <span data-ttu-id="71153-130">たとえば、メモリのページのアクセスの保護を変更するシステム コールに失敗した場合、オペレーティング システム エラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="71153-130">For example, if a system call to change the access protection of a page of memory fails, the operating system error is displayed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="71153-131">必要条件</span><span class="sxs-lookup"><span data-stu-id="71153-131">Requirements</span></span>  
 <span data-ttu-id="71153-132">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="71153-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71153-133">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="71153-133">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="71153-134">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="71153-134">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="71153-135">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71153-135">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71153-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="71153-136">See also</span></span>

- [<span data-ttu-id="71153-137">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="71153-137">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="71153-138">ICorProfilerCallback4 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="71153-138">ICorProfilerCallback4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
