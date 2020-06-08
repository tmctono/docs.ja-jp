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
ms.openlocfilehash: 9bc6619f3ef383c7bf60a310a87f056cfc43cddf
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84498675"
---
# <a name="icorprofilerinfoforcegc-method"></a><span data-ttu-id="13538-102">ICorProfilerInfo::ForceGC メソッド</span><span class="sxs-lookup"><span data-stu-id="13538-102">ICorProfilerInfo::ForceGC Method</span></span>
<span data-ttu-id="13538-103">共通言語ランタイム (CLR) 内で強制的にガベージコレクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="13538-103">Forces garbage collection to occur within the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13538-104">構文</span><span class="sxs-lookup"><span data-stu-id="13538-104">Syntax</span></span>  
  
```cpp  
HRESULT ForceGC();  
```  
  
## <a name="remarks"></a><span data-ttu-id="13538-105">解説</span><span class="sxs-lookup"><span data-stu-id="13538-105">Remarks</span></span>  
 <span data-ttu-id="13538-106">メソッドを呼び出す必要があるのは、 `ForceGC` マネージコードを実行しておらず、そのスタックにプロファイラーコールバックがないスレッドだけです。</span><span class="sxs-lookup"><span data-stu-id="13538-106">The `ForceGC` method must be called only from a thread that has never run managed code and does not have any profiler callbacks on its stack.</span></span> <span data-ttu-id="13538-107">最も便利な実装は、 `ForceGC` シグナル状態になったときにを呼び出す、プロファイラー内に個別のスレッドを作成することです。</span><span class="sxs-lookup"><span data-stu-id="13538-107">The most convenient implementation is to create a separate thread within the profiler that calls `ForceGC` when signaled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13538-108">要件</span><span class="sxs-lookup"><span data-stu-id="13538-108">Requirements</span></span>  
 <span data-ttu-id="13538-109">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="13538-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13538-110">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="13538-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="13538-111">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="13538-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="13538-112">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13538-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13538-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="13538-113">See also</span></span>

- [<span data-ttu-id="13538-114">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="13538-114">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
