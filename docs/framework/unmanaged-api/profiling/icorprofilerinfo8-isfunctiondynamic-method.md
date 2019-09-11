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
ms.openlocfilehash: 01aa1df27dccf41060083333588e04bc5ea88520
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855934"
---
# <a name="icorprofilerinfo8isfunctiondynamic-method"></a><span data-ttu-id="d5427-102">ICorProfilerInfo8:: IsFunctionDynamic メソッド</span><span class="sxs-lookup"><span data-stu-id="d5427-102">ICorProfilerInfo8::IsFunctionDynamic Method</span></span>

<span data-ttu-id="d5427-103">関数にメタデータが関連付けられていないかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="d5427-103">Determines if a function does not have associated metadata.</span></span>

## <a name="syntax"></a><span data-ttu-id="d5427-104">構文</span><span class="sxs-lookup"><span data-stu-id="d5427-104">Syntax</span></span>

```cpp
HRESULT IsFunctionDynamic( [in]  FunctionID  functionId,
                           [out] BOOL        *isDynamic);
```

#### <a name="parameters"></a><span data-ttu-id="d5427-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d5427-105">Parameters</span></span>

`functionId` \
<span data-ttu-id="d5427-106">から 対象の関数を識別する。`FunctionID`</span><span class="sxs-lookup"><span data-stu-id="d5427-106">[in]  The `FunctionID` that identifies the function in question.</span></span>

`isDynamic` \
<span data-ttu-id="d5427-107">入出力関数にメタデータ`BOOL`がないかどうかを示す値を格納するへのポインター。</span><span class="sxs-lookup"><span data-stu-id="d5427-107">[out] A pointer to a `BOOL` that will contain a value indicating if the function has no metadata.</span></span>

## <a name="remarks"></a><span data-ttu-id="d5427-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="d5427-108">Remarks</span></span>

<span data-ttu-id="d5427-109">関数は、メタデータがない場合は動的と見なされます。</span><span class="sxs-lookup"><span data-stu-id="d5427-109">A function is considered dynamic if it has no metadata.</span></span> <span data-ttu-id="d5427-110">IL スタブや LCG メソッドなどの特定のメソッドには、IMetaDataImport Api を使用して取得できるメタデータが関連付けられていません。</span><span class="sxs-lookup"><span data-stu-id="d5427-110">Certain methods like IL Stubs or LCG Methods do not have associated metadata that can be retrieved using the IMetaDataImport APIs.</span></span> <span data-ttu-id="d5427-111">これらのメソッドは、命令ポインターを通じて、または[ICorProfilerCallback::D ynamicmethodjitcompilationstarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)をリッスンすることによって、プロファイラーによって検出されます。</span><span class="sxs-lookup"><span data-stu-id="d5427-111">These methods can be encountered by profilers through instruction pointers or by listening to [ICorProfilerCallback::DynamicMethodJITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="d5427-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="d5427-112">Requirements</span></span>

<span data-ttu-id="d5427-113">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d5427-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="d5427-114">**ヘッダー:** Corprof.idl、Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="d5427-114">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="d5427-115">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="d5427-115">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="d5427-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="d5427-116">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="d5427-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="d5427-117">See also</span></span>

- [<span data-ttu-id="d5427-118">ICorProfilerInfo8 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d5427-118">ICorProfilerInfo8 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-interface.md)
