---
title: ICorProfilerInfo3::EnumJITedFunctions メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.EnumJITedFunctions Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::EnumJITedFunctions
helpviewer_keywords:
- ICorProfilerInfo3::EnumJITedFunctions method [.NET Framework profiling]
- EnumJITedFunctions method [.NET Framework profiling]
ms.assetid: e2847a36-f460-45e2-9b6c-b33b008f40d9
topic_type:
- apiref
ms.openlocfilehash: d21a793a88cd7561da9acb7daab2dc3bfecf0fc7
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449759"
---
# <a name="icorprofilerinfo3enumjitedfunctions-method"></a><span data-ttu-id="a7724-102">ICorProfilerInfo3::EnumJITedFunctions メソッド</span><span class="sxs-lookup"><span data-stu-id="a7724-102">ICorProfilerInfo3::EnumJITedFunctions Method</span></span>
<span data-ttu-id="a7724-103">以前に JIT でコンパイルされたすべての関数の列挙子を返します。</span><span class="sxs-lookup"><span data-stu-id="a7724-103">Returns an enumerator for all functions that were previously JIT-compiled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7724-104">構文</span><span class="sxs-lookup"><span data-stu-id="a7724-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumJITedFunctions([out] ICorProfilerFunctionEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a7724-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a7724-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="a7724-106">入出力[ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)列挙子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="a7724-106">[out] A pointer to the [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) enumerator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a7724-107">コメント</span><span class="sxs-lookup"><span data-stu-id="a7724-107">Remarks</span></span>  
 <span data-ttu-id="a7724-108">このメソッドは、 [ICorProfilerCallback:: JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md)メソッドなどの `JITCompilation` コールバックと重複する場合があります。</span><span class="sxs-lookup"><span data-stu-id="a7724-108">This method may overlap with `JITCompilation` callbacks such as the [ICorProfilerCallback::JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md) method.</span></span> <span data-ttu-id="a7724-109">このメソッドによって返される列挙子には、Ngen.exe で生成されたネイティブイメージから読み込まれた関数は含まれません。</span><span class="sxs-lookup"><span data-stu-id="a7724-109">The enumerator returned by this method does not include functions that are loaded from native images generated with Ngen.exe.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a7724-110">返された列挙体には、`COR_PRF_FUNCTION::reJitId` フィールドの値に対して "0" のみが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a7724-110">The returned enumeration includes only "0" for the value of the `COR_PRF_FUNCTION::reJitId` field.</span></span>  <span data-ttu-id="a7724-111">有効な `COR_PRF_FUNCTION::reJitId` 値が必要な場合は、 [ICorProfilerInfo4:: EnumJITedFunctions2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumjitedfunctions2-method.md)メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="a7724-111">If you require valid `COR_PRF_FUNCTION::reJitId` values, use the [ICorProfilerInfo4::EnumJITedFunctions2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumjitedfunctions2-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7724-112">要件</span><span class="sxs-lookup"><span data-stu-id="a7724-112">Requirements</span></span>  
 <span data-ttu-id="a7724-113">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a7724-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7724-114">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a7724-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a7724-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a7724-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a7724-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7724-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7724-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="a7724-117">See also</span></span>

- [<span data-ttu-id="a7724-118">ICorProfilerInfo3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a7724-118">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="a7724-119">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="a7724-119">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="a7724-120">プロファイル</span><span class="sxs-lookup"><span data-stu-id="a7724-120">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
