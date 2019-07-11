---
title: ICorProfilerCallback4::GetReJITParameters メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback4.GetReJITParameters
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4::GetReJITParameters
helpviewer_keywords:
- ICorProfilerCallback4::GetReJITParameters method [.NET Framework profiling]
- GetReJITParameters method, ICorProfilerCallback4 interface [.NET Framework profiling]
ms.assetid: 0e9bfe07-9f20-498c-b568-9017c8f6056c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 03b7ca218318df517832d198e72d4f79d30827b8
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779238"
---
# <a name="icorprofilercallback4getrejitparameters-method"></a><span data-ttu-id="cb660-102">ICorProfilerCallback4::GetReJITParameters メソッド</span><span class="sxs-lookup"><span data-stu-id="cb660-102">ICorProfilerCallback4::GetReJITParameters Method</span></span>
<span data-ttu-id="cb660-103">新しい再コンパイルされたメソッド本体の代替コード生成フラグを設定するコード プロファイラーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="cb660-103">Allows the code profiler to set alternate code generation flags for a new recompiled method body.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb660-104">構文</span><span class="sxs-lookup"><span data-stu-id="cb660-104">Syntax</span></span>  
  
```cpp  
HRESULT GetReJITParameters(     [in] ModuleID moduleId,     [in] mdMethodDef methodId,     [in] ICorProfilerFunctionControl *pFunctionControl);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cb660-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="cb660-105">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="cb660-106">[in]このモジュールは、CLR で JIT 再コンパイル パラメーターを必要なメソッドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="cb660-106">[in] The module that contains the method for which the CLR needs JIT recompilation parameters.</span></span>  
  
 `methodId`  
 <span data-ttu-id="cb660-107">[in]`MethodDef`のメソッドの CLR が JIT 再コンパイル パラメーターを必要があります。</span><span class="sxs-lookup"><span data-stu-id="cb660-107">[in] The `MethodDef` of the method for which the CLR needs JIT recompilation parameters.</span></span>  
  
 `pFunctionControl`  
 <span data-ttu-id="cb660-108">[in]ポインター、 [ICorProfilerFunctionControl](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md)プロファイラーを使用して再コンパイルされるメソッドの JIT 再コンパイルの情報を提供するインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="cb660-108">[in] A pointer to an [ICorProfilerFunctionControl](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md) interface that the profiler can use to provide JIT recompilation information for the method being recompiled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cb660-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="cb660-109">Remarks</span></span>  
 <span data-ttu-id="cb660-110">CLR の問題、`GetReJITParameters`コールバック、プロファイラーは、特定のメソッドを再コンパイルのパラメーターを指定できるようにします。</span><span class="sxs-lookup"><span data-stu-id="cb660-110">The CLR issues a `GetReJITParameters` callback so that the profiler can specify the parameters for recompiling a given method.</span></span> <span data-ttu-id="cb660-111">`GetReJITParameters`関数ごとのコールバックは、1 回だけ発行されます。 プロファイラーによって指定されたパラメーターは、その関数のすべてのインスタンスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="cb660-111">The `GetReJITParameters` callback is issued only once per function; the parameters supplied by the profiler apply to all instances of that function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cb660-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="cb660-112">Requirements</span></span>  
 <span data-ttu-id="cb660-113">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb660-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb660-114">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="cb660-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="cb660-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cb660-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cb660-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cb660-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb660-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="cb660-117">See also</span></span>

- [<span data-ttu-id="cb660-118">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cb660-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="cb660-119">ICorProfilerCallback4 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cb660-119">ICorProfilerCallback4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
- [<span data-ttu-id="cb660-120">JITCompilationStarted メソッド</span><span class="sxs-lookup"><span data-stu-id="cb660-120">JITCompilationStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md)
- [<span data-ttu-id="cb660-121">ReJITCompilationStarted メソッド</span><span class="sxs-lookup"><span data-stu-id="cb660-121">ReJITCompilationStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationstarted-method.md)
