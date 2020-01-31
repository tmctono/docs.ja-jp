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
ms.openlocfilehash: a4c875f6aae996271dee9ac193768ef6981efc19
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76863037"
---
# <a name="icorprofilerinfo10suspendruntime-method"></a><span data-ttu-id="c1a29-102">ICorProfilerInfo10:: SuspendRuntime メソッド</span><span class="sxs-lookup"><span data-stu-id="c1a29-102">ICorProfilerInfo10::SuspendRuntime Method</span></span>

<span data-ttu-id="c1a29-103">GC を実行せずにランタイムを中断します。</span><span class="sxs-lookup"><span data-stu-id="c1a29-103">Suspends the runtime without performing a GC.</span></span>

## <a name="syntax"></a><span data-ttu-id="c1a29-104">構文</span><span class="sxs-lookup"><span data-stu-id="c1a29-104">Syntax</span></span>

```cpp
HRESULT SuspendRuntime();
```

## <a name="requirements"></a><span data-ttu-id="c1a29-105">要件</span><span class="sxs-lookup"><span data-stu-id="c1a29-105">Requirements</span></span>

<span data-ttu-id="c1a29-106">**プラットフォーム:** 「 [.Net Core でサポートされるオペレーティングシステム](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c1a29-106">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span></span>

<span data-ttu-id="c1a29-107">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c1a29-107">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="c1a29-108">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c1a29-108">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="c1a29-109">**.Net のバージョン:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1a29-109">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="c1a29-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="c1a29-110">See also</span></span>

- [<span data-ttu-id="c1a29-111">ICorProfilerInfo10 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c1a29-111">ICorProfilerInfo10 Interface</span></span>](icorprofilerinfo10-interface.md)
