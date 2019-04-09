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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 81477010b22edee71098edfc1b8557db08b6038f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59178634"
---
# <a name="icorprofilercallback7-interface"></a><span data-ttu-id="0bf0c-102">ICorProfilerCallback7 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0bf0c-102">ICorProfilerCallback7 Interface</span></span>
<span data-ttu-id="0bf0c-103">[.NET Framework 4.6.1 以降のバージョンでのみでサポート]</span><span class="sxs-lookup"><span data-stu-id="0bf0c-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="0bf0c-104">[ICorProfilerCallback6](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-interface.md) のサブクラスは、メモリ内のモジュールに関連付けられているシンボルのストリームが更新されたことをプロファイラーに通知するために、共通言語ランタイムが使用するコールバック メソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="0bf0c-104">A subclass of [ICorProfilerCallback6](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-interface.md) that provides a callback method that the common language runtime uses to notify the profiler that the symbol stream associated with an in-memory module is updated.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0bf0c-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="0bf0c-105">Methods</span></span>  
  
|<span data-ttu-id="0bf0c-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="0bf0c-106">Method</span></span>|<span data-ttu-id="0bf0c-107">説明</span><span class="sxs-lookup"><span data-stu-id="0bf0c-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0bf0c-108">ModuleInMemorySymbolsUpdated メソッド</span><span class="sxs-lookup"><span data-stu-id="0bf0c-108">ModuleInMemorySymbolsUpdated Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-moduleinmemorysymbolsupdated-method.md)|<span data-ttu-id="0bf0c-109">メモリ内のモジュールに関連付けられているシンボルのストリームが更新されていることをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="0bf0c-109">Notifies the profiler that the symbol stream associated with an in-memory module is updated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0bf0c-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="0bf0c-110">Requirements</span></span>  
 <span data-ttu-id="0bf0c-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0bf0c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0bf0c-112">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0bf0c-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 **<span data-ttu-id="0bf0c-113">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="0bf0c-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0bf0c-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="0bf0c-114">See also</span></span>

- [<span data-ttu-id="0bf0c-115">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="0bf0c-115">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
