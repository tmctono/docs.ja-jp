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
ms.openlocfilehash: e1fe38419cda328c919f0840d51cf6336919aa60
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76864209"
---
# <a name="icorprofilerinfoforcegc-method"></a><span data-ttu-id="d1159-102">ICorProfilerInfo::ForceGC メソッド</span><span class="sxs-lookup"><span data-stu-id="d1159-102">ICorProfilerInfo::ForceGC Method</span></span>
<span data-ttu-id="d1159-103">共通言語ランタイム (CLR) 内で強制的にガベージコレクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="d1159-103">Forces garbage collection to occur within the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1159-104">構文</span><span class="sxs-lookup"><span data-stu-id="d1159-104">Syntax</span></span>  
  
```cpp  
HRESULT ForceGC();  
```  
  
## <a name="remarks"></a><span data-ttu-id="d1159-105">コメント</span><span class="sxs-lookup"><span data-stu-id="d1159-105">Remarks</span></span>  
 <span data-ttu-id="d1159-106">`ForceGC` メソッドを呼び出すことができるのは、マネージコードを実行しておらず、そのスタックにプロファイラーコールバックがないスレッドだけです。</span><span class="sxs-lookup"><span data-stu-id="d1159-106">The `ForceGC` method must be called only from a thread that has never run managed code and does not have any profiler callbacks on its stack.</span></span> <span data-ttu-id="d1159-107">最も便利な実装は、通知されたときに `ForceGC` を呼び出す、プロファイラー内に別のスレッドを作成することです。</span><span class="sxs-lookup"><span data-stu-id="d1159-107">The most convenient implementation is to create a separate thread within the profiler that calls `ForceGC` when signaled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d1159-108">要件</span><span class="sxs-lookup"><span data-stu-id="d1159-108">Requirements</span></span>  
 <span data-ttu-id="d1159-109">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1159-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d1159-110">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d1159-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d1159-111">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d1159-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d1159-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d1159-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1159-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="d1159-113">See also</span></span>

- [<span data-ttu-id="d1159-114">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d1159-114">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
