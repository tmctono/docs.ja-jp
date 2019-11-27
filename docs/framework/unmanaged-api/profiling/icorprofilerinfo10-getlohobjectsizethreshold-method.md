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
ms.openlocfilehash: 7a38ee4ae74ca5b96dd082e752fc733eb85fca3f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427027"
---
# <a name="icorprofilerinfo10getlohobjectsizethreshold-method"></a><span data-ttu-id="81526-102">ICorProfilerInfo10:: GetLOHObjectSizeThreshold メソッド</span><span class="sxs-lookup"><span data-stu-id="81526-102">ICorProfilerInfo10::GetLOHObjectSizeThreshold Method</span></span>

<span data-ttu-id="81526-103">構成されたラージオブジェクトヒープ (LOH) のしきい値の値を取得します。</span><span class="sxs-lookup"><span data-stu-id="81526-103">Gets the value of the configured large object heap (LOH) threshold.</span></span>

## <a name="syntax"></a><span data-ttu-id="81526-104">構文</span><span class="sxs-lookup"><span data-stu-id="81526-104">Syntax</span></span>

```cpp
HRESULT GetLOHObjectSizeThreshold( [out] DWORD *pThreshold );
```

#### <a name="parameters"></a><span data-ttu-id="81526-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="81526-105">Parameters</span></span>

`pThreshold` \
<span data-ttu-id="81526-106">入出力ラージオブジェクトヒープのしきい値 (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="81526-106">[out] The large object heap threshold in bytes.</span></span>

## <a name="remarks"></a><span data-ttu-id="81526-107">コメント</span><span class="sxs-lookup"><span data-stu-id="81526-107">Remarks</span></span>

<span data-ttu-id="81526-108">大きなオブジェクトヒープのしきい値より大きいオブジェクトは、大きなオブジェクトヒープに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="81526-108">Objects larger than the large object heap threshold will be allocated on the large object heap.</span></span> <span data-ttu-id="81526-109">.NET Core 3.0 以降では、大きなオブジェクトヒープのしきい値は構成可能で、`pThreshold` にはアクティブな大きなオブジェクトヒープのしきい値サイズ (バイト単位) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="81526-109">Starting with .NET Core 3.0 the large object heap threshold is configurable, `pThreshold` will contain the active large object heap threshold size in bytes.</span></span>

## <a name="requirements"></a><span data-ttu-id="81526-110">要件</span><span class="sxs-lookup"><span data-stu-id="81526-110">Requirements</span></span>

<span data-ttu-id="81526-111">**プラットフォーム:** 「 [.Net Core でサポートされるオペレーティングシステム](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="81526-111">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span></span>

<span data-ttu-id="81526-112">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="81526-112">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="81526-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="81526-113">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="81526-114">**.Net のバージョン:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81526-114">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="81526-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="81526-115">See also</span></span>

- [<span data-ttu-id="81526-116">ICorProfilerInfo10 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="81526-116">ICorProfilerInfo10 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-interface.md)
