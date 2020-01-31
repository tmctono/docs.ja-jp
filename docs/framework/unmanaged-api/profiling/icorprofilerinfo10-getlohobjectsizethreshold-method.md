---
title: ICorProfilerInfo10::GetLOHObjectSizeThreshold
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo10.GetLOHObjectSizeThreshold
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 95473a8ce8d5fd7540228ecd9767448e51b5b326
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868985"
---
# <a name="icorprofilerinfo10getlohobjectsizethreshold-method"></a><span data-ttu-id="5e07c-102">ICorProfilerInfo10:: GetLOHObjectSizeThreshold メソッド</span><span class="sxs-lookup"><span data-stu-id="5e07c-102">ICorProfilerInfo10::GetLOHObjectSizeThreshold Method</span></span>

<span data-ttu-id="5e07c-103">構成されたラージオブジェクトヒープ (LOH) のしきい値の値を取得します。</span><span class="sxs-lookup"><span data-stu-id="5e07c-103">Gets the value of the configured large object heap (LOH) threshold.</span></span>

## <a name="syntax"></a><span data-ttu-id="5e07c-104">構文</span><span class="sxs-lookup"><span data-stu-id="5e07c-104">Syntax</span></span>

```cpp
HRESULT GetLOHObjectSizeThreshold( [out] DWORD *pThreshold );
```

## <a name="parameters"></a><span data-ttu-id="5e07c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5e07c-105">Parameters</span></span>

- `pThreshold`

  <span data-ttu-id="5e07c-106">\[out] 大きなオブジェクトヒープのしきい値 (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="5e07c-106">\[out] The large object heap threshold in bytes.</span></span>

## <a name="remarks"></a><span data-ttu-id="5e07c-107">コメント</span><span class="sxs-lookup"><span data-stu-id="5e07c-107">Remarks</span></span>

<span data-ttu-id="5e07c-108">大きなオブジェクトヒープのしきい値より大きいオブジェクトは、大きなオブジェクトヒープに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="5e07c-108">Objects larger than the large object heap threshold will be allocated on the large object heap.</span></span> <span data-ttu-id="5e07c-109">.NET Core 3.0 以降では、大きなオブジェクトヒープのしきい値は構成可能で、`pThreshold` にはアクティブな大きなオブジェクトヒープのしきい値サイズ (バイト単位) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="5e07c-109">Starting with .NET Core 3.0 the large object heap threshold is configurable, `pThreshold` will contain the active large object heap threshold size in bytes.</span></span>

## <a name="requirements"></a><span data-ttu-id="5e07c-110">要件</span><span class="sxs-lookup"><span data-stu-id="5e07c-110">Requirements</span></span>

<span data-ttu-id="5e07c-111">**プラットフォーム:** 「 [.Net Core でサポートされるオペレーティングシステム](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e07c-111">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span></span>

<span data-ttu-id="5e07c-112">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5e07c-112">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="5e07c-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5e07c-113">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="5e07c-114">**.Net のバージョン:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5e07c-114">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="5e07c-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="5e07c-115">See also</span></span>

- [<span data-ttu-id="5e07c-116">ICorProfilerInfo10 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5e07c-116">ICorProfilerInfo10 Interface</span></span>](icorprofilerinfo10-interface.md)
