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
ms.openlocfilehash: 1d0e1914ac13b5004f9e66a6e6dc2d4c914c6fd5
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/13/2019
ms.locfileid: "68974002"
---
# <a name="icorprofilerinfo10suspendruntime-method"></a><span data-ttu-id="d11c5-102">ICorProfilerInfo10:: SuspendRuntime メソッド</span><span class="sxs-lookup"><span data-stu-id="d11c5-102">ICorProfilerInfo10::SuspendRuntime Method</span></span>
  
 <span data-ttu-id="d11c5-103">GC を実行せずにランタイムを中断します。</span><span class="sxs-lookup"><span data-stu-id="d11c5-103">Suspends the runtime without performing a GC.</span></span>   
  
## <a name="syntax"></a><span data-ttu-id="d11c5-104">構文</span><span class="sxs-lookup"><span data-stu-id="d11c5-104">Syntax</span></span>  
  
```cpp
HRESULT SuspendRuntime();
```  

## <a name="requirements"></a><span data-ttu-id="d11c5-105">必要条件</span><span class="sxs-lookup"><span data-stu-id="d11c5-105">Requirements</span></span>  
 <span data-ttu-id="d11c5-106">**・** 「 [.Net Core でサポートされるオペレーティングシステム](../../../core/windows-prerequisites.md#net-core-supported-operating-systems)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d11c5-106">**Platforms:** See [.NET Core supported operating systems](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span></span>  
  
 <span data-ttu-id="d11c5-107">**ヘッダー:** Corprof.idl、Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="d11c5-107">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d11c5-108">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="d11c5-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d11c5-109">**.Net のバージョン:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d11c5-109">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d11c5-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="d11c5-110">See also</span></span>
- [<span data-ttu-id="d11c5-111">ICorProfilerInfo10 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d11c5-111">ICorProfilerInfo10 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-interface.md)

