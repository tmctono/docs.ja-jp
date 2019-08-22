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
ms.openlocfilehash: cf599e5ded73b09d54c98dcd99f51b30c6a4ba82
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2019
ms.locfileid: "69661204"
---
# <a name="icorprofilerinfo10resumeruntime-method"></a><span data-ttu-id="e5b1c-102">ICorProfilerInfo10:: ResumeRuntime メソッド</span><span class="sxs-lookup"><span data-stu-id="e5b1c-102">ICorProfilerInfo10::ResumeRuntime Method</span></span>

<span data-ttu-id="e5b1c-103">GC を実行せずにランタイムを再開します。</span><span class="sxs-lookup"><span data-stu-id="e5b1c-103">Resumes the runtime without performing a GC.</span></span>

## <a name="syntax"></a><span data-ttu-id="e5b1c-104">構文</span><span class="sxs-lookup"><span data-stu-id="e5b1c-104">Syntax</span></span>

```cpp
HRESULT ResumeRuntime();
```

## <a name="requirements"></a><span data-ttu-id="e5b1c-105">必要条件</span><span class="sxs-lookup"><span data-stu-id="e5b1c-105">Requirements</span></span>

<span data-ttu-id="e5b1c-106">**・** 「 [.Net Core でサポートされるオペレーティングシステム](../../../core/windows-prerequisites.md#net-core-supported-operating-systems)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5b1c-106">**Platforms:** See [.NET Core supported operating systems](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span></span>

<span data-ttu-id="e5b1c-107">**ヘッダー:** Corprof.idl、Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="e5b1c-107">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="e5b1c-108">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="e5b1c-108">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="e5b1c-109">**.Net のバージョン:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5b1c-109">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="e5b1c-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="e5b1c-110">See also</span></span>

- [<span data-ttu-id="e5b1c-111">ICorProfilerInfo10 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e5b1c-111">ICorProfilerInfo10 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-interface.md)
