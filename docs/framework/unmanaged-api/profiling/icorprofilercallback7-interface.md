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
ms.openlocfilehash: 9a49d8e1ff31942c6564ab560d6726b9ede26466
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499143"
---
# <a name="icorprofilercallback7-interface"></a><span data-ttu-id="1489a-102">ICorProfilerCallback7 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1489a-102">ICorProfilerCallback7 Interface</span></span>
<span data-ttu-id="1489a-103">[.NET Framework 4.6.1 以降のバージョンでのみでサポート]</span><span class="sxs-lookup"><span data-stu-id="1489a-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="1489a-104">[ICorProfilerCallback6](icorprofilercallback6-interface.md) のサブクラスは、メモリ内のモジュールに関連付けられているシンボルのストリームが更新されたことをプロファイラーに通知するために、共通言語ランタイムが使用するコールバック メソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="1489a-104">A subclass of [ICorProfilerCallback6](icorprofilercallback6-interface.md) that provides a callback method that the common language runtime uses to notify the profiler that the symbol stream associated with an in-memory module is updated.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1489a-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="1489a-105">Methods</span></span>  
  
|<span data-ttu-id="1489a-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="1489a-106">Method</span></span>|<span data-ttu-id="1489a-107">説明</span><span class="sxs-lookup"><span data-stu-id="1489a-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1489a-108">ModuleInMemorySymbolsUpdated メソッド</span><span class="sxs-lookup"><span data-stu-id="1489a-108">ModuleInMemorySymbolsUpdated Method</span></span>](icorprofilercallback7-moduleinmemorysymbolsupdated-method.md)|<span data-ttu-id="1489a-109">メモリ内のモジュールに関連付けられているシンボルのストリームが更新されていることをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="1489a-109">Notifies the profiler that the symbol stream associated with an in-memory module is updated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1489a-110">要件</span><span class="sxs-lookup"><span data-stu-id="1489a-110">Requirements</span></span>  
 <span data-ttu-id="1489a-111">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1489a-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1489a-112">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1489a-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1489a-113">**.NET Framework のバージョン:**[!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1489a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1489a-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="1489a-114">See also</span></span>

- [<span data-ttu-id="1489a-115">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="1489a-115">Profiling Interfaces</span></span>](profiling-interfaces.md)
