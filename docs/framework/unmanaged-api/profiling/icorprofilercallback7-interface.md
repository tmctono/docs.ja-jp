---
title: ICorProfilerCallback7 インターフェイス
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback7
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.assetid: a0be019e-aaa1-4036-990f-565f114d4b5c
ms.openlocfilehash: f8c2fb544cf9fd6642bd0581211e0e4e49633221
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139762"
---
# <a name="icorprofilercallback7-interface"></a><span data-ttu-id="1cb1d-102">ICorProfilerCallback7 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1cb1d-102">ICorProfilerCallback7 Interface</span></span>
<span data-ttu-id="1cb1d-103">[.NET Framework 4.6.1 以降のバージョンでのみでサポート]</span><span class="sxs-lookup"><span data-stu-id="1cb1d-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="1cb1d-104">[ICorProfilerCallback6](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-interface.md) のサブクラスは、メモリ内のモジュールに関連付けられているシンボルのストリームが更新されたことをプロファイラーに通知するために、共通言語ランタイムが使用するコールバック メソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="1cb1d-104">A subclass of [ICorProfilerCallback6](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-interface.md) that provides a callback method that the common language runtime uses to notify the profiler that the symbol stream associated with an in-memory module is updated.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1cb1d-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="1cb1d-105">Methods</span></span>  
  
|<span data-ttu-id="1cb1d-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="1cb1d-106">Method</span></span>|<span data-ttu-id="1cb1d-107">説明</span><span class="sxs-lookup"><span data-stu-id="1cb1d-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1cb1d-108">ModuleInMemorySymbolsUpdated メソッド</span><span class="sxs-lookup"><span data-stu-id="1cb1d-108">ModuleInMemorySymbolsUpdated Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-moduleinmemorysymbolsupdated-method.md)|<span data-ttu-id="1cb1d-109">メモリ内のモジュールに関連付けられているシンボルのストリームが更新されていることをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="1cb1d-109">Notifies the profiler that the symbol stream associated with an in-memory module is updated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1cb1d-110">［要件］</span><span class="sxs-lookup"><span data-stu-id="1cb1d-110">Requirements</span></span>  
 <span data-ttu-id="1cb1d-111">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1cb1d-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1cb1d-112">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1cb1d-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1cb1d-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1cb1d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1cb1d-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="1cb1d-114">See also</span></span>

- [<span data-ttu-id="1cb1d-115">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="1cb1d-115">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
