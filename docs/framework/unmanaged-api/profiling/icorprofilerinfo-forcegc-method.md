---
title: ICorProfilerInfo::ForceGC メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.ForceGC
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::ForceGC
helpviewer_keywords:
- ICorProfilerInfo::ForceGC method [.NET Framework profiling]
- ForceGC method [.NET Framework profiling]
ms.assetid: 0da1ef80-d242-4636-87d0-43e0470b342a
topic_type:
- apiref
ms.openlocfilehash: 9f97da4e68d4b76178198e91c3fb8f08b56dda7b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448187"
---
# <a name="icorprofilerinfoforcegc-method"></a><span data-ttu-id="9c7d4-102">ICorProfilerInfo::ForceGC メソッド</span><span class="sxs-lookup"><span data-stu-id="9c7d4-102">ICorProfilerInfo::ForceGC Method</span></span>
<span data-ttu-id="9c7d4-103">共通言語ランタイム (CLR) 内で強制的にガベージコレクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="9c7d4-103">Forces garbage collection to occur within the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c7d4-104">構文</span><span class="sxs-lookup"><span data-stu-id="9c7d4-104">Syntax</span></span>  
  
```cpp  
HRESULT ForceGC();  
```  
  
## <a name="remarks"></a><span data-ttu-id="9c7d4-105">コメント</span><span class="sxs-lookup"><span data-stu-id="9c7d4-105">Remarks</span></span>  
 <span data-ttu-id="9c7d4-106">`ForceGC` メソッドを呼び出すことができるのは、マネージコードを実行しておらず、そのスタックにプロファイラーコールバックがないスレッドだけです。</span><span class="sxs-lookup"><span data-stu-id="9c7d4-106">The `ForceGC` method must be called only from a thread that has never run managed code and does not have any profiler callbacks on its stack.</span></span> <span data-ttu-id="9c7d4-107">最も便利な実装は、通知されたときに `ForceGC` を呼び出す、プロファイラー内に別のスレッドを作成することです。</span><span class="sxs-lookup"><span data-stu-id="9c7d4-107">The most convenient implementation is to create a separate thread within the profiler that calls `ForceGC` when signaled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9c7d4-108">要件</span><span class="sxs-lookup"><span data-stu-id="9c7d4-108">Requirements</span></span>  
 <span data-ttu-id="9c7d4-109">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9c7d4-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9c7d4-110">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9c7d4-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9c7d4-111">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9c7d4-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9c7d4-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9c7d4-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c7d4-113">参照</span><span class="sxs-lookup"><span data-stu-id="9c7d4-113">See also</span></span>

- [<span data-ttu-id="9c7d4-114">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9c7d4-114">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
