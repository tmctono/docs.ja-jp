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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5672d1b89b4260d1ebfbf444deb2702f215a0e95
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62049649"
---
# <a name="icorprofilerinfoforcegc-method"></a><span data-ttu-id="9b6f5-102">ICorProfilerInfo::ForceGC メソッド</span><span class="sxs-lookup"><span data-stu-id="9b6f5-102">ICorProfilerInfo::ForceGC Method</span></span>
<span data-ttu-id="9b6f5-103">共通言語ランタイム (CLR) 内に発生する強制的にガベージ コレクション。</span><span class="sxs-lookup"><span data-stu-id="9b6f5-103">Forces garbage collection to occur within the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b6f5-104">構文</span><span class="sxs-lookup"><span data-stu-id="9b6f5-104">Syntax</span></span>  
  
```  
HRESULT ForceGC();  
```  
  
## <a name="remarks"></a><span data-ttu-id="9b6f5-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="9b6f5-105">Remarks</span></span>  
 <span data-ttu-id="9b6f5-106">`ForceGC`メソッドは、マネージ コードを実行していないと、スタックに任意のプロファイラーのコールバックがないスレッドからのみ呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b6f5-106">The `ForceGC` method must be called only from a thread that has never run managed code and does not have any profiler callbacks on its stack.</span></span> <span data-ttu-id="9b6f5-107">呼び出すプロファイラー内で別のスレッドを作成する最も便利な実装は、`ForceGC`シグナルを受け取るとします。</span><span class="sxs-lookup"><span data-stu-id="9b6f5-107">The most convenient implementation is to create a separate thread within the profiler that calls `ForceGC` when signaled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b6f5-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="9b6f5-108">Requirements</span></span>  
 <span data-ttu-id="9b6f5-109">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9b6f5-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b6f5-110">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9b6f5-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9b6f5-111">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9b6f5-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9b6f5-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b6f5-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b6f5-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="9b6f5-113">See also</span></span>

- [<span data-ttu-id="9b6f5-114">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9b6f5-114">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
