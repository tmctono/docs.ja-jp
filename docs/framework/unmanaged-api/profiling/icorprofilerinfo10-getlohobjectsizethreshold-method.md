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
ms.openlocfilehash: d6b6575cf04635b40b504b11bc415f61f05b4205
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/13/2019
ms.locfileid: "68974022"
---
# <a name="icorprofilerinfo10getlohobjectsizethreshold-method"></a><span data-ttu-id="b1fb0-102">ICorProfilerInfo10:: GetLOHObjectSizeThreshold メソッド</span><span class="sxs-lookup"><span data-stu-id="b1fb0-102">ICorProfilerInfo10::GetLOHObjectSizeThreshold Method</span></span>
  
 <span data-ttu-id="b1fb0-103">構成されたラージオブジェクトヒープ (LOH) のしきい値の値を取得します。</span><span class="sxs-lookup"><span data-stu-id="b1fb0-103">Gets the value of the configured large object heap (LOH) threshold.</span></span>   
  
## <a name="syntax"></a><span data-ttu-id="b1fb0-104">構文</span><span class="sxs-lookup"><span data-stu-id="b1fb0-104">Syntax</span></span>  
  
```cpp
HRESULT GetLOHObjectSizeThreshold( [out] DWORD *pThreshold );
```  
  
#### <a name="parameters"></a><span data-ttu-id="b1fb0-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b1fb0-105">Parameters</span></span>  
 `pThreshold` \
 <span data-ttu-id="b1fb0-106">入出力ラージオブジェクトヒープのしきい値 (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="b1fb0-106">[out] The large object heap threshold in bytes.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="b1fb0-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="b1fb0-107">Remarks</span></span>  
 <span data-ttu-id="b1fb0-108">大きなオブジェクトヒープのしきい値より大きいオブジェクトは、大きなオブジェクトヒープに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="b1fb0-108">Objects larger than the large object heap threshold will be allocated on the large object heap.</span></span> <span data-ttu-id="b1fb0-109">.Net Core 3.0 以降では、大きなオブジェクトヒープのしきい値`pThreshold`は構成可能で、アクティブなラージオブジェクトヒープのしきい値のサイズはバイト単位で格納されます。</span><span class="sxs-lookup"><span data-stu-id="b1fb0-109">Starting with .NET Core 3.0 the large object heap threshold is configurable, `pThreshold` will contain the active large object heap threshold size in bytes.</span></span>

## <a name="requirements"></a><span data-ttu-id="b1fb0-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="b1fb0-110">Requirements</span></span>  
 <span data-ttu-id="b1fb0-111">**・** 「 [.Net Core でサポートされるオペレーティングシステム](../../../core/windows-prerequisites.md#net-core-supported-operating-systems)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1fb0-111">**Platforms:** See [.NET Core supported operating systems](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span></span>  
  
 <span data-ttu-id="b1fb0-112">**ヘッダー:** Corprof.idl、Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="b1fb0-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b1fb0-113">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="b1fb0-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b1fb0-114">**.Net のバージョン:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b1fb0-114">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b1fb0-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="b1fb0-115">See also</span></span>
- [<span data-ttu-id="b1fb0-116">ICorProfilerInfo10 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b1fb0-116">ICorProfilerInfo10 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-interface.md)

