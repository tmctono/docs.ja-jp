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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7525d107fec7229d9b86eee63bde2aaf2d701b1b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59190302"
---
# <a name="icorprofilerinfo3enumjitedfunctions-method"></a><span data-ttu-id="35eb0-102">ICorProfilerInfo3::EnumJITedFunctions メソッド</span><span class="sxs-lookup"><span data-stu-id="35eb0-102">ICorProfilerInfo3::EnumJITedFunctions Method</span></span>
<span data-ttu-id="35eb0-103">以前の JIT コンパイルされたすべての関数の列挙子を返します。</span><span class="sxs-lookup"><span data-stu-id="35eb0-103">Returns an enumerator for all functions that were previously JIT-compiled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35eb0-104">構文</span><span class="sxs-lookup"><span data-stu-id="35eb0-104">Syntax</span></span>  
  
```  
HRESULT EnumJITedFunctions([out] ICorProfilerFunctionEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="35eb0-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="35eb0-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="35eb0-106">[out]ポインター、 [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)列挙子。</span><span class="sxs-lookup"><span data-stu-id="35eb0-106">[out] A pointer to the [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) enumerator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="35eb0-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="35eb0-107">Remarks</span></span>  
 <span data-ttu-id="35eb0-108">このメソッドが重複する`JITCompilation`コールバックなど、 [icorprofilercallback::jitcompilationstarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="35eb0-108">This method may overlap with `JITCompilation` callbacks such as the [ICorProfilerCallback::JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md) method.</span></span> <span data-ttu-id="35eb0-109">このメソッドによって返される列挙子では、Ngen.exe で生成されたネイティブ イメージから読み込まれた関数は含まれません。</span><span class="sxs-lookup"><span data-stu-id="35eb0-109">The enumerator returned by this method does not include functions that are loaded from native images generated with Ngen.exe.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="35eb0-110">返された列挙体には値を「0」のみが含まれています、`COR_PRF_FUNCTION::reJitId`フィールド。</span><span class="sxs-lookup"><span data-stu-id="35eb0-110">The returned enumeration includes only "0" for the value of the `COR_PRF_FUNCTION::reJitId` field.</span></span>  <span data-ttu-id="35eb0-111">有効なが必要な場合`COR_PRF_FUNCTION::reJitId`、値を使用して、 [icorprofilerinfo 4::enumjitedfunctions2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumjitedfunctions2-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="35eb0-111">If you require valid `COR_PRF_FUNCTION::reJitId` values, use the [ICorProfilerInfo4::EnumJITedFunctions2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumjitedfunctions2-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35eb0-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="35eb0-112">Requirements</span></span>  
 <span data-ttu-id="35eb0-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="35eb0-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35eb0-114">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="35eb0-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="35eb0-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="35eb0-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="35eb0-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35eb0-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35eb0-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="35eb0-117">See also</span></span>

- [<span data-ttu-id="35eb0-118">ICorProfilerInfo3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="35eb0-118">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="35eb0-119">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="35eb0-119">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="35eb0-120">プロファイル</span><span class="sxs-lookup"><span data-stu-id="35eb0-120">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
