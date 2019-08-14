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
ms.openlocfilehash: 919ebc4ddcdee930bc660a4f7e62d9bc746b6dc7
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/13/2019
ms.locfileid: "68973972"
---
# <a name="icorprofilerinfo10resumeruntime-method"></a><span data-ttu-id="81d4d-102">ICorProfilerInfo10:: ResumeRuntime メソッド</span><span class="sxs-lookup"><span data-stu-id="81d4d-102">ICorProfilerInfo10::ResumeRuntime Method</span></span>
  
<span data-ttu-id="81d4d-103">GC を実行せずにランタイムを再開します。</span><span class="sxs-lookup"><span data-stu-id="81d4d-103">Resumes the runtime without performing a GC.</span></span>   
  
## <a name="syntax"></a><span data-ttu-id="81d4d-104">構文</span><span class="sxs-lookup"><span data-stu-id="81d4d-104">Syntax</span></span>  
  
```cpp
HRESULT ResumeRuntime();
```  

## <a name="requirements"></a><span data-ttu-id="81d4d-105">必要条件</span><span class="sxs-lookup"><span data-stu-id="81d4d-105">Requirements</span></span>  
 <span data-ttu-id="81d4d-106">**・** 「 [.Net Core でサポートされるオペレーティングシステム](../../../core/windows-prerequisites.md#net-core-supported-operating-systems)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="81d4d-106">**Platforms:** See [.NET Core supported operating systems](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span></span>  
  
 <span data-ttu-id="81d4d-107">**ヘッダー:** Corprof.idl、Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="81d4d-107">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="81d4d-108">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="81d4d-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="81d4d-109">**.Net のバージョン:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81d4d-109">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>
  
## <a name="see-also"></a><span data-ttu-id="81d4d-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="81d4d-110">See also</span></span>
- [<span data-ttu-id="81d4d-111">ICorProfilerInfo10 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="81d4d-111">ICorProfilerInfo10 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-interface.md)

