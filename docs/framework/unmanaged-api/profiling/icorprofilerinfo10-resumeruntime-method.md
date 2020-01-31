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
ms.openlocfilehash: 49de3383902791b1278e7c9221a80c3454eb12a2
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868921"
---
# <a name="icorprofilerinfo10resumeruntime-method"></a><span data-ttu-id="663fe-102">ICorProfilerInfo10:: ResumeRuntime メソッド</span><span class="sxs-lookup"><span data-stu-id="663fe-102">ICorProfilerInfo10::ResumeRuntime Method</span></span>

<span data-ttu-id="663fe-103">GC を実行せずにランタイムを再開します。</span><span class="sxs-lookup"><span data-stu-id="663fe-103">Resumes the runtime without performing a GC.</span></span>

## <a name="syntax"></a><span data-ttu-id="663fe-104">構文</span><span class="sxs-lookup"><span data-stu-id="663fe-104">Syntax</span></span>

```cpp
HRESULT ResumeRuntime();
```

## <a name="requirements"></a><span data-ttu-id="663fe-105">要件</span><span class="sxs-lookup"><span data-stu-id="663fe-105">Requirements</span></span>

<span data-ttu-id="663fe-106">**プラットフォーム:** 「 [.Net Core でサポートされるオペレーティングシステム](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="663fe-106">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span></span>

<span data-ttu-id="663fe-107">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="663fe-107">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="663fe-108">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="663fe-108">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="663fe-109">**.Net のバージョン:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="663fe-109">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="663fe-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="663fe-110">See also</span></span>

- [<span data-ttu-id="663fe-111">ICorProfilerInfo10 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="663fe-111">ICorProfilerInfo10 Interface</span></span>](icorprofilerinfo10-interface.md)
