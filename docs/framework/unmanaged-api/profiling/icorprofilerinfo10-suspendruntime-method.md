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
ms.openlocfilehash: 8d00718579f44a164cd83e2b05d41f70f1c65785
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452150"
---
# <a name="icorprofilerinfo10suspendruntime-method"></a><span data-ttu-id="55be1-102">ICorProfilerInfo10:: SuspendRuntime メソッド</span><span class="sxs-lookup"><span data-stu-id="55be1-102">ICorProfilerInfo10::SuspendRuntime Method</span></span>

<span data-ttu-id="55be1-103">GC を実行せずにランタイムを中断します。</span><span class="sxs-lookup"><span data-stu-id="55be1-103">Suspends the runtime without performing a GC.</span></span>

## <a name="syntax"></a><span data-ttu-id="55be1-104">構文</span><span class="sxs-lookup"><span data-stu-id="55be1-104">Syntax</span></span>

```cpp
HRESULT SuspendRuntime();
```

## <a name="requirements"></a><span data-ttu-id="55be1-105">要件</span><span class="sxs-lookup"><span data-stu-id="55be1-105">Requirements</span></span>

<span data-ttu-id="55be1-106">**プラットフォーム:** 「 [.Net Core でサポートされるオペレーティングシステム](../../../core/install/dependencies.md?pivots=os-windows)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="55be1-106">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?pivots=os-windows).</span></span>

<span data-ttu-id="55be1-107">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="55be1-107">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="55be1-108">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="55be1-108">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="55be1-109">**.Net のバージョン:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55be1-109">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="55be1-110">参照</span><span class="sxs-lookup"><span data-stu-id="55be1-110">See also</span></span>

- [<span data-ttu-id="55be1-111">ICorProfilerInfo10 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="55be1-111">ICorProfilerInfo10 Interface</span></span>](icorprofilerinfo10-interface.md)
