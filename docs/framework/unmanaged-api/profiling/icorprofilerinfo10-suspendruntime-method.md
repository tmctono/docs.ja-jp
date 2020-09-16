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
ms.openlocfilehash: 121ed0401628193f6e2fe632a124c08aad7bd1b4
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90551440"
---
# <a name="icorprofilerinfo10suspendruntime-method"></a><span data-ttu-id="93a3c-102">ICorProfilerInfo10:: SuspendRuntime メソッド</span><span class="sxs-lookup"><span data-stu-id="93a3c-102">ICorProfilerInfo10::SuspendRuntime Method</span></span>

<span data-ttu-id="93a3c-103">GC を実行せずにランタイムを中断します。</span><span class="sxs-lookup"><span data-stu-id="93a3c-103">Suspends the runtime without performing a GC.</span></span>

## <a name="syntax"></a><span data-ttu-id="93a3c-104">構文</span><span class="sxs-lookup"><span data-stu-id="93a3c-104">Syntax</span></span>

```cpp
HRESULT SuspendRuntime();
```

## <a name="requirements"></a><span data-ttu-id="93a3c-105">必要条件</span><span class="sxs-lookup"><span data-stu-id="93a3c-105">Requirements</span></span>

<span data-ttu-id="93a3c-106">**プラットフォーム:** 「 [.Net Core でサポートされるオペレーティングシステム](../../../core/install/windows.md?pivots=os-windows)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="93a3c-106">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>

<span data-ttu-id="93a3c-107">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="93a3c-107">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="93a3c-108">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="93a3c-108">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="93a3c-109">**.Net のバージョン:**[!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="93a3c-109">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="93a3c-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="93a3c-110">See also</span></span>

- [<span data-ttu-id="93a3c-111">ICorProfilerInfo10 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="93a3c-111">ICorProfilerInfo10 Interface</span></span>](icorprofilerinfo10-interface.md)
