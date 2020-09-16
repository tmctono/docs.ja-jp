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
ms.openlocfilehash: 280f0a401f87f81e1ef9d4a2c85c06599442b5ec
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90543947"
---
# <a name="icorprofilerinfo10getlohobjectsizethreshold-method"></a><span data-ttu-id="ac1f0-102">ICorProfilerInfo10:: GetLOHObjectSizeThreshold メソッド</span><span class="sxs-lookup"><span data-stu-id="ac1f0-102">ICorProfilerInfo10::GetLOHObjectSizeThreshold Method</span></span>

<span data-ttu-id="ac1f0-103">構成されたラージオブジェクトヒープ (LOH) のしきい値の値を取得します。</span><span class="sxs-lookup"><span data-stu-id="ac1f0-103">Gets the value of the configured large object heap (LOH) threshold.</span></span>

## <a name="syntax"></a><span data-ttu-id="ac1f0-104">構文</span><span class="sxs-lookup"><span data-stu-id="ac1f0-104">Syntax</span></span>

```cpp
HRESULT GetLOHObjectSizeThreshold( [out] DWORD *pThreshold );
```

## <a name="parameters"></a><span data-ttu-id="ac1f0-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ac1f0-105">Parameters</span></span>

- `pThreshold`

  <span data-ttu-id="ac1f0-106">\[out: 大きなオブジェクトヒープのしきい値 (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="ac1f0-106">\[out] The large object heap threshold in bytes.</span></span>

## <a name="remarks"></a><span data-ttu-id="ac1f0-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="ac1f0-107">Remarks</span></span>

<span data-ttu-id="ac1f0-108">大きなオブジェクトヒープのしきい値より大きいオブジェクトは、大きなオブジェクトヒープに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="ac1f0-108">Objects larger than the large object heap threshold will be allocated on the large object heap.</span></span> <span data-ttu-id="ac1f0-109">.NET Core 3.0 以降では、大きなオブジェクトヒープのしきい値は構成可能で、 `pThreshold` アクティブなラージオブジェクトヒープのしきい値のサイズはバイト単位で格納されます。</span><span class="sxs-lookup"><span data-stu-id="ac1f0-109">Starting with .NET Core 3.0 the large object heap threshold is configurable, `pThreshold` will contain the active large object heap threshold size in bytes.</span></span>

## <a name="requirements"></a><span data-ttu-id="ac1f0-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="ac1f0-110">Requirements</span></span>

<span data-ttu-id="ac1f0-111">**プラットフォーム:** 「 [.Net Core でサポートされるオペレーティングシステム](../../../core/install/windows.md?pivots=os-windows)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac1f0-111">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>

<span data-ttu-id="ac1f0-112">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ac1f0-112">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="ac1f0-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ac1f0-113">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="ac1f0-114">**.Net のバージョン:**[!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac1f0-114">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="ac1f0-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="ac1f0-115">See also</span></span>

- [<span data-ttu-id="ac1f0-116">ICorProfilerInfo10 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ac1f0-116">ICorProfilerInfo10 Interface</span></span>](icorprofilerinfo10-interface.md)
