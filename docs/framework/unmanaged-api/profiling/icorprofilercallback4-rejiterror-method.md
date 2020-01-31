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
ms.openlocfilehash: 66195ea9df4c8e9ce847b38f7d020a3bebffcd37
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865182"
---
# <a name="icorprofilercallback4rejiterror-method"></a><span data-ttu-id="194f2-102">ICorProfilerCallback4::ReJITError メソッド</span><span class="sxs-lookup"><span data-stu-id="194f2-102">ICorProfilerCallback4::ReJITError Method</span></span>
<span data-ttu-id="194f2-103">Just-in-time (JIT) コンパイラが再コンパイルプロセスでエラーを検出したことをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="194f2-103">Notifies the profiler that the just-in-time (JIT) compiler encountered an error in the recompilation process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="194f2-104">構文</span><span class="sxs-lookup"><span data-stu-id="194f2-104">Syntax</span></span>  
  
```cpp  
HRESULT ReJITError(  
    [in] ModuleID    moduleId,  
    [in] mdMethodDef methodId,  
    [in] FunctionID  functionId,  
    [in] HRESULT     hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="194f2-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="194f2-105">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="194f2-106">から再コンパイルの試行が失敗した `ModuleID`。</span><span class="sxs-lookup"><span data-stu-id="194f2-106">[in] The `ModuleID` in which the failed recompilation attempt was made.</span></span>  
  
 `methodId`  
 <span data-ttu-id="194f2-107">から再コンパイルの試行が失敗したメソッドの `MethodDef`。</span><span class="sxs-lookup"><span data-stu-id="194f2-107">[in] The `MethodDef` of the method on which the failed recompilation attempt was made.</span></span>  
  
 `functionId`  
 <span data-ttu-id="194f2-108">から再コンパイルまたは再コンパイルのマークが付けられている関数インスタンス。</span><span class="sxs-lookup"><span data-stu-id="194f2-108">[in] The function instance that is being recompiled or marked for recompilation.</span></span> <span data-ttu-id="194f2-109">この値は、インスタンス化ごとにではなく、メソッドごとにエラーが発生した場合に `NULL` ことがあります (たとえば、プロファイラーがメソッドを再コンパイルするために無効なメタデータトークンを指定した場合など)。</span><span class="sxs-lookup"><span data-stu-id="194f2-109">This value may be `NULL` if the failure occurred on a per-method basis instead of a per-instantiation basis (for example, if the profiler specified an invalid metadata token for the method to be recompiled).</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="194f2-110">からエラーの性質を示す HRESULT。</span><span class="sxs-lookup"><span data-stu-id="194f2-110">[in] An HRESULT that indicates the nature of the failure.</span></span> <span data-ttu-id="194f2-111">値の一覧については、「Status HRESULT」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="194f2-111">See the Status HRESULTS section for a list of values.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="194f2-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="194f2-112">Return Value</span></span>  
 <span data-ttu-id="194f2-113">このコールバックからの戻り値は無視されます。</span><span class="sxs-lookup"><span data-stu-id="194f2-113">Return values from this callback are ignored.</span></span>  
  
## <a name="status-hresults"></a><span data-ttu-id="194f2-114">状態 HRESULT</span><span class="sxs-lookup"><span data-stu-id="194f2-114">Status HRESULTS</span></span>  
  
|<span data-ttu-id="194f2-115">状態配列 HRESULT</span><span class="sxs-lookup"><span data-stu-id="194f2-115">Status array HRESULT</span></span>|<span data-ttu-id="194f2-116">説明</span><span class="sxs-lookup"><span data-stu-id="194f2-116">Description</span></span>|  
|--------------------------|-----------------|  
|<span data-ttu-id="194f2-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="194f2-117">E_INVALIDARG</span></span>|<span data-ttu-id="194f2-118">`moduleID` または `methodDef` トークンが `NULL`。</span><span class="sxs-lookup"><span data-stu-id="194f2-118">The `moduleID` or `methodDef` token is `NULL`.</span></span>|  
|<span data-ttu-id="194f2-119">CORPROF_E_DATAINCOMPLETE</span><span class="sxs-lookup"><span data-stu-id="194f2-119">CORPROF_E_DATAINCOMPLETE</span></span>|<span data-ttu-id="194f2-120">モジュールが完全に読み込まれていないか、またはアンロード中です。</span><span class="sxs-lookup"><span data-stu-id="194f2-120">The module is not fully loaded yet, or it is in the process of being unloaded.</span></span>|  
|<span data-ttu-id="194f2-121">CORPROF_E_MODULE_IS_DYNAMIC</span><span class="sxs-lookup"><span data-stu-id="194f2-121">CORPROF_E_MODULE_IS_DYNAMIC</span></span>|<span data-ttu-id="194f2-122">指定されたモジュールは (たとえば、`Reflection.Emit`によって) 動的に生成されたため、このメソッドではサポートされません。</span><span class="sxs-lookup"><span data-stu-id="194f2-122">The specified module was dynamically generated (for example, by `Reflection.Emit`), and is thus not supported by this method.</span></span>|  
|<span data-ttu-id="194f2-123">CORPROF_E_FUNCTION_IS_COLLECTIBLE</span><span class="sxs-lookup"><span data-stu-id="194f2-123">CORPROF_E_FUNCTION_IS_COLLECTIBLE</span></span>|<span data-ttu-id="194f2-124">メソッドは、収集可能なアセンブリにインスタンス化されるため、再コンパイルできません。</span><span class="sxs-lookup"><span data-stu-id="194f2-124">The method is instantiated into a collectible assembly, and is therefore not able to be recompiled.</span></span> <span data-ttu-id="194f2-125">非リフレクションコンテキストで定義されている型および関数 (`List<MyCollectibleStruct>`など) は、収集可能なアセンブリにインスタンス化できます。</span><span class="sxs-lookup"><span data-stu-id="194f2-125">Note that types and functions defined in a non-reflection context (for example, `List<MyCollectibleStruct>`) can be instantiated into a collectible assembly.</span></span>|  
|<span data-ttu-id="194f2-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="194f2-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="194f2-127">CLR は、指定されたメソッドに JIT 再コンパイルのマークを付けようとしている間にメモリ不足になりました。</span><span class="sxs-lookup"><span data-stu-id="194f2-127">The CLR ran out of memory while trying to mark the specified method for JIT recompilation.</span></span>|  
|<span data-ttu-id="194f2-128">その他</span><span class="sxs-lookup"><span data-stu-id="194f2-128">Other</span></span>|<span data-ttu-id="194f2-129">オペレーティング システムは、CLR 制御範囲外のエラーを返しました。</span><span class="sxs-lookup"><span data-stu-id="194f2-129">The operating system returned a failure outside the control of the CLR.</span></span> <span data-ttu-id="194f2-130">たとえば、メモリページのアクセス保護を変更するシステムコールが失敗した場合、オペレーティングシステムエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="194f2-130">For example, if a system call to change the access protection of a page of memory fails, the operating system error is displayed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="194f2-131">要件</span><span class="sxs-lookup"><span data-stu-id="194f2-131">Requirements</span></span>  
 <span data-ttu-id="194f2-132">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="194f2-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="194f2-133">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="194f2-133">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="194f2-134">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="194f2-134">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="194f2-135">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="194f2-135">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="194f2-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="194f2-136">See also</span></span>

- [<span data-ttu-id="194f2-137">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="194f2-137">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="194f2-138">ICorProfilerCallback4 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="194f2-138">ICorProfilerCallback4 Interface</span></span>](icorprofilercallback4-interface.md)
