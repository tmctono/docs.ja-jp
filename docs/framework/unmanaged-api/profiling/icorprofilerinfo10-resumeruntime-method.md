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
ms.openlocfilehash: 515b42d649f68345f9924f57a91d146556480e0a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449807"
---
# <a name="icorprofilerinfo10resumeruntime-method"></a><span data-ttu-id="5b499-102">ICorProfilerInfo10:: ResumeRuntime メソッド</span><span class="sxs-lookup"><span data-stu-id="5b499-102">ICorProfilerInfo10::ResumeRuntime Method</span></span>

<span data-ttu-id="5b499-103">GC を実行せずにランタイムを再開します。</span><span class="sxs-lookup"><span data-stu-id="5b499-103">Resumes the runtime without performing a GC.</span></span>

## <a name="syntax"></a><span data-ttu-id="5b499-104">構文</span><span class="sxs-lookup"><span data-stu-id="5b499-104">Syntax</span></span>

```cpp
HRESULT ResumeRuntime();
```

## <a name="requirements"></a><span data-ttu-id="5b499-105">要件</span><span class="sxs-lookup"><span data-stu-id="5b499-105">Requirements</span></span>

<span data-ttu-id="5b499-106">**プラットフォーム:** 「 [.Net Core でサポートされるオペレーティングシステム](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5b499-106">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span></span>

<span data-ttu-id="5b499-107">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5b499-107">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="5b499-108">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5b499-108">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="5b499-109">**.Net のバージョン:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b499-109">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="5b499-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="5b499-110">See also</span></span>

- [<span data-ttu-id="5b499-111">ICorProfilerInfo10 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5b499-111">ICorProfilerInfo10 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-interface.md)
