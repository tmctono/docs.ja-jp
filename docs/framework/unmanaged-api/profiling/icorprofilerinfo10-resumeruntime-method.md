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
ms.openlocfilehash: 41e95a9f3ad34853f9cd71fa2cb81d3fca0fb2cd
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90540566"
---
# <a name="icorprofilerinfo10resumeruntime-method"></a><span data-ttu-id="fc577-102">ICorProfilerInfo10:: ResumeRuntime メソッド</span><span class="sxs-lookup"><span data-stu-id="fc577-102">ICorProfilerInfo10::ResumeRuntime Method</span></span>

<span data-ttu-id="fc577-103">GC を実行せずにランタイムを再開します。</span><span class="sxs-lookup"><span data-stu-id="fc577-103">Resumes the runtime without performing a GC.</span></span>

## <a name="syntax"></a><span data-ttu-id="fc577-104">構文</span><span class="sxs-lookup"><span data-stu-id="fc577-104">Syntax</span></span>

```cpp
HRESULT ResumeRuntime();
```

## <a name="requirements"></a><span data-ttu-id="fc577-105">必要条件</span><span class="sxs-lookup"><span data-stu-id="fc577-105">Requirements</span></span>

<span data-ttu-id="fc577-106">**プラットフォーム:** 「 [.Net Core でサポートされるオペレーティングシステム](../../../core/install/windows.md?pivots=os-windows)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fc577-106">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>

<span data-ttu-id="fc577-107">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fc577-107">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="fc577-108">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fc577-108">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="fc577-109">**.Net のバージョン:**[!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc577-109">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="fc577-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="fc577-110">See also</span></span>

- [<span data-ttu-id="fc577-111">ICorProfilerInfo10 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fc577-111">ICorProfilerInfo10 Interface</span></span>](icorprofilerinfo10-interface.md)
