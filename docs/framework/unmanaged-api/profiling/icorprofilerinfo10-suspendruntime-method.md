---
title: ICorProfilerInfo10::SuspendRuntime
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo10.SuspendRuntime
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: f5104c779f99ef9f26a9eccc00008ded62336d8e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74426967"
---
# <a name="icorprofilerinfo10suspendruntime-method"></a><span data-ttu-id="c666e-102">ICorProfilerInfo10:: SuspendRuntime メソッド</span><span class="sxs-lookup"><span data-stu-id="c666e-102">ICorProfilerInfo10::SuspendRuntime Method</span></span>

<span data-ttu-id="c666e-103">GC を実行せずにランタイムを中断します。</span><span class="sxs-lookup"><span data-stu-id="c666e-103">Suspends the runtime without performing a GC.</span></span>

## <a name="syntax"></a><span data-ttu-id="c666e-104">構文</span><span class="sxs-lookup"><span data-stu-id="c666e-104">Syntax</span></span>

```cpp
HRESULT SuspendRuntime();
```

## <a name="requirements"></a><span data-ttu-id="c666e-105">要件</span><span class="sxs-lookup"><span data-stu-id="c666e-105">Requirements</span></span>

<span data-ttu-id="c666e-106">**プラットフォーム:** 「 [.Net Core でサポートされるオペレーティングシステム](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c666e-106">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span></span>

<span data-ttu-id="c666e-107">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c666e-107">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="c666e-108">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c666e-108">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="c666e-109">**.Net のバージョン:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c666e-109">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="c666e-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="c666e-110">See also</span></span>

- [<span data-ttu-id="c666e-111">ICorProfilerInfo10 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c666e-111">ICorProfilerInfo10 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-interface.md)
