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
ms.openlocfilehash: 8c9a85e9f00027f597795eea55a9bbb0364790f8
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2019
ms.locfileid: "69661237"
---
# <a name="icorprofilerinfo10getlohobjectsizethreshold-method"></a><span data-ttu-id="d2230-102">ICorProfilerInfo10:: GetLOHObjectSizeThreshold メソッド</span><span class="sxs-lookup"><span data-stu-id="d2230-102">ICorProfilerInfo10::GetLOHObjectSizeThreshold Method</span></span>

<span data-ttu-id="d2230-103">構成されたラージオブジェクトヒープ (LOH) のしきい値の値を取得します。</span><span class="sxs-lookup"><span data-stu-id="d2230-103">Gets the value of the configured large object heap (LOH) threshold.</span></span>

## <a name="syntax"></a><span data-ttu-id="d2230-104">構文</span><span class="sxs-lookup"><span data-stu-id="d2230-104">Syntax</span></span>

```cpp
HRESULT GetLOHObjectSizeThreshold( [out] DWORD *pThreshold );
```

#### <a name="parameters"></a><span data-ttu-id="d2230-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d2230-105">Parameters</span></span>

`pThreshold` \
<span data-ttu-id="d2230-106">入出力ラージオブジェクトヒープのしきい値 (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="d2230-106">[out] The large object heap threshold in bytes.</span></span>

## <a name="remarks"></a><span data-ttu-id="d2230-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="d2230-107">Remarks</span></span>

<span data-ttu-id="d2230-108">大きなオブジェクトヒープのしきい値より大きいオブジェクトは、大きなオブジェクトヒープに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="d2230-108">Objects larger than the large object heap threshold will be allocated on the large object heap.</span></span> <span data-ttu-id="d2230-109">.Net Core 3.0 以降では、大きなオブジェクトヒープのしきい値`pThreshold`は構成可能で、アクティブなラージオブジェクトヒープのしきい値のサイズはバイト単位で格納されます。</span><span class="sxs-lookup"><span data-stu-id="d2230-109">Starting with .NET Core 3.0 the large object heap threshold is configurable, `pThreshold` will contain the active large object heap threshold size in bytes.</span></span>

## <a name="requirements"></a><span data-ttu-id="d2230-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="d2230-110">Requirements</span></span>

<span data-ttu-id="d2230-111">**・** 「 [.Net Core でサポートされるオペレーティングシステム](../../../core/windows-prerequisites.md#net-core-supported-operating-systems)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d2230-111">**Platforms:** See [.NET Core supported operating systems](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span></span>

<span data-ttu-id="d2230-112">**ヘッダー:** Corprof.idl、Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="d2230-112">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="d2230-113">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="d2230-113">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="d2230-114">**.Net のバージョン:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d2230-114">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="d2230-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="d2230-115">See also</span></span>

- [<span data-ttu-id="d2230-116">ICorProfilerInfo10 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d2230-116">ICorProfilerInfo10 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-interface.md)
