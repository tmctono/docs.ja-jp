---
title: ICorProfilerInfo10::ResumeRuntime
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo10.ResumeRuntime
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: a3dca2cbb138dbc43f477488032e67335c8b15f9
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452163"
---
# <a name="icorprofilerinfo10resumeruntime-method"></a><span data-ttu-id="2301f-102">ICorProfilerInfo10:: ResumeRuntime メソッド</span><span class="sxs-lookup"><span data-stu-id="2301f-102">ICorProfilerInfo10::ResumeRuntime Method</span></span>

<span data-ttu-id="2301f-103">GC を実行せずにランタイムを再開します。</span><span class="sxs-lookup"><span data-stu-id="2301f-103">Resumes the runtime without performing a GC.</span></span>

## <a name="syntax"></a><span data-ttu-id="2301f-104">構文</span><span class="sxs-lookup"><span data-stu-id="2301f-104">Syntax</span></span>

```cpp
HRESULT ResumeRuntime();
```

## <a name="requirements"></a><span data-ttu-id="2301f-105">要件</span><span class="sxs-lookup"><span data-stu-id="2301f-105">Requirements</span></span>

<span data-ttu-id="2301f-106">**プラットフォーム:** 「 [.Net Core でサポートされるオペレーティングシステム](../../../core/install/dependencies.md?pivots=os-windows)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2301f-106">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?pivots=os-windows).</span></span>

<span data-ttu-id="2301f-107">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2301f-107">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="2301f-108">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2301f-108">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="2301f-109">**.Net のバージョン:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2301f-109">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="2301f-110">参照</span><span class="sxs-lookup"><span data-stu-id="2301f-110">See also</span></span>

- [<span data-ttu-id="2301f-111">ICorProfilerInfo10 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2301f-111">ICorProfilerInfo10 Interface</span></span>](icorprofilerinfo10-interface.md)
