---
title: ICorProfilerCallback6 インターフェイス
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback6
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.assetid: edc420b7-96d1-4dec-ace0-36d907f644bc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8fda98c20b42355b9f52595929bbf5b980b5b857
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59077239"
---
# <a name="icorprofilercallback6-interface"></a><span data-ttu-id="d99b6-102">ICorProfilerCallback6 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d99b6-102">ICorProfilerCallback6 Interface</span></span>
<span data-ttu-id="d99b6-103">[.NET Framework 4.5.2 以降のバージョンでのみでサポート]</span><span class="sxs-lookup"><span data-stu-id="d99b6-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="d99b6-104">サブクラス[ICorProfilerCallback5](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-interface.md)共通言語ランタイムを使用してアセンブリを読み込むことをプロファイラーに通知するコールバック メソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="d99b6-104">A subclass of [ICorProfilerCallback5](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-interface.md) that provides a callback method that the common language runtime uses to notify a profiler that an assembly is loading.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d99b6-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="d99b6-105">Methods</span></span>  
  
|<span data-ttu-id="d99b6-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="d99b6-106">Method</span></span>|<span data-ttu-id="d99b6-107">説明</span><span class="sxs-lookup"><span data-stu-id="d99b6-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d99b6-108">GetAssemblyReferences メソッド</span><span class="sxs-lookup"><span data-stu-id="d99b6-108">GetAssemblyReferences Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md)|<span data-ttu-id="d99b6-109">共通言語ランタイムがアセンブリ参照クロージャのウォークを実行するときに、アセンブリがごく初期のローディング状態であることをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="d99b6-109">Notifies the profiler that an assembly is in a very early loading stage, when the common language runtime performs an assembly reference closure walk.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d99b6-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="d99b6-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d99b6-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="d99b6-111">Requirements</span></span>  
 <span data-ttu-id="d99b6-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d99b6-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d99b6-113">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d99b6-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 **<span data-ttu-id="d99b6-114">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="d99b6-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d99b6-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="d99b6-115">See also</span></span>

- [<span data-ttu-id="d99b6-116">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="d99b6-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
