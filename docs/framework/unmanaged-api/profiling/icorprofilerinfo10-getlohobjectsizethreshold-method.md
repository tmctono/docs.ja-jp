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
ms.openlocfilehash: d4d498c1d75625b2abc37dc1f4c88d73b58ec675
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790028"
---
# <a name="icorprofilerinfo10getlohobjectsizethreshold-method"></a><span data-ttu-id="efa38-102">ICorProfilerInfo10:: GetLOHObjectSizeThreshold メソッド</span><span class="sxs-lookup"><span data-stu-id="efa38-102">ICorProfilerInfo10::GetLOHObjectSizeThreshold Method</span></span>

<span data-ttu-id="efa38-103">構成されたラージオブジェクトヒープ (LOH) のしきい値の値を取得します。</span><span class="sxs-lookup"><span data-stu-id="efa38-103">Gets the value of the configured large object heap (LOH) threshold.</span></span>

## <a name="syntax"></a><span data-ttu-id="efa38-104">構文</span><span class="sxs-lookup"><span data-stu-id="efa38-104">Syntax</span></span>

```cpp
HRESULT GetLOHObjectSizeThreshold( [out] DWORD *pThreshold );
```

## <a name="parameters"></a><span data-ttu-id="efa38-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="efa38-105">Parameters</span></span>

- `pThreshold`

  <span data-ttu-id="efa38-106">\[out] 大きなオブジェクトヒープのしきい値 (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="efa38-106">\[out] The large object heap threshold in bytes.</span></span>

## <a name="remarks"></a><span data-ttu-id="efa38-107">コメント</span><span class="sxs-lookup"><span data-stu-id="efa38-107">Remarks</span></span>

<span data-ttu-id="efa38-108">大きなオブジェクトヒープのしきい値より大きいオブジェクトは、大きなオブジェクトヒープに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="efa38-108">Objects larger than the large object heap threshold will be allocated on the large object heap.</span></span> <span data-ttu-id="efa38-109">.NET Core 3.0 以降では、大きなオブジェクトヒープのしきい値は構成可能で、`pThreshold` にはアクティブな大きなオブジェクトヒープのしきい値サイズ (バイト単位) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="efa38-109">Starting with .NET Core 3.0 the large object heap threshold is configurable, `pThreshold` will contain the active large object heap threshold size in bytes.</span></span>

## <a name="requirements"></a><span data-ttu-id="efa38-110">要件</span><span class="sxs-lookup"><span data-stu-id="efa38-110">Requirements</span></span>

<span data-ttu-id="efa38-111">**プラットフォーム:** 「 [.Net Core でサポートされるオペレーティングシステム](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="efa38-111">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span></span>

<span data-ttu-id="efa38-112">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="efa38-112">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="efa38-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="efa38-113">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="efa38-114">**.Net のバージョン:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="efa38-114">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="efa38-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="efa38-115">See also</span></span>

- [<span data-ttu-id="efa38-116">ICorProfilerInfo10 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="efa38-116">ICorProfilerInfo10 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-interface.md)
