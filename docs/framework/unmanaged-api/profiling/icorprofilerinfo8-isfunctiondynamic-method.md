---
title: 'ICorProfilerInfo8:: IsFunctionDynamic'
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo8.IsFunctionDynamic
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 50b4de2de3e74a5835ee5706999892735269d4c2
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76861737"
---
# <a name="icorprofilerinfo8isfunctiondynamic-method"></a><span data-ttu-id="c9afb-102">ICorProfilerInfo8:: IsFunctionDynamic メソッド</span><span class="sxs-lookup"><span data-stu-id="c9afb-102">ICorProfilerInfo8::IsFunctionDynamic Method</span></span>

<span data-ttu-id="c9afb-103">関数にメタデータが関連付けられていないかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="c9afb-103">Determines if a function does not have associated metadata.</span></span>

## <a name="syntax"></a><span data-ttu-id="c9afb-104">構文</span><span class="sxs-lookup"><span data-stu-id="c9afb-104">Syntax</span></span>

```cpp
HRESULT IsFunctionDynamic( [in]  FunctionID  functionId,
                           [out] BOOL        *isDynamic);
```

## <a name="parameters"></a><span data-ttu-id="c9afb-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c9afb-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="c9afb-106">\[] には、対象の関数を識別する `FunctionID` を指定します。</span><span class="sxs-lookup"><span data-stu-id="c9afb-106">\[in]  The `FunctionID` that identifies the function in question.</span></span>

- `isDynamic`

  <span data-ttu-id="c9afb-107">\[out] 関数にメタデータが含まれていないかどうかを示す値を格納する `BOOL` へのポインター。</span><span class="sxs-lookup"><span data-stu-id="c9afb-107">\[out] A pointer to a `BOOL` that will contain a value indicating if the function has no metadata.</span></span>

## <a name="remarks"></a><span data-ttu-id="c9afb-108">コメント</span><span class="sxs-lookup"><span data-stu-id="c9afb-108">Remarks</span></span>

<span data-ttu-id="c9afb-109">関数は、メタデータがない場合は動的と見なされます。</span><span class="sxs-lookup"><span data-stu-id="c9afb-109">A function is considered dynamic if it has no metadata.</span></span> <span data-ttu-id="c9afb-110">IL スタブや LCG メソッドなどの特定のメソッドには、IMetaDataImport Api を使用して取得できるメタデータが関連付けられていません。</span><span class="sxs-lookup"><span data-stu-id="c9afb-110">Certain methods like IL Stubs or LCG Methods do not have associated metadata that can be retrieved using the IMetaDataImport APIs.</span></span> <span data-ttu-id="c9afb-111">これらのメソッドは、命令ポインターを通じて、または[ICorProfilerCallback::D ynamicmethodjitcompilationstarted](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)をリッスンすることによって、プロファイラーによって検出されます。</span><span class="sxs-lookup"><span data-stu-id="c9afb-111">These methods can be encountered by profilers through instruction pointers or by listening to [ICorProfilerCallback::DynamicMethodJITCompilationStarted](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="c9afb-112">要件</span><span class="sxs-lookup"><span data-stu-id="c9afb-112">Requirements</span></span>

<span data-ttu-id="c9afb-113">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c9afb-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="c9afb-114">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c9afb-114">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="c9afb-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c9afb-115">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="c9afb-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="c9afb-116">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="c9afb-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="c9afb-117">See also</span></span>

- [<span data-ttu-id="c9afb-118">ICorProfilerInfo8 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c9afb-118">ICorProfilerInfo8 Interface</span></span>](icorprofilerinfo8-interface.md)
