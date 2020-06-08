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
ms.openlocfilehash: 0156a7dfa2a67ce9e62b502df00fc6bc5fccf925
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499182"
---
# <a name="icorprofilercallback6-interface"></a><span data-ttu-id="f65fd-102">ICorProfilerCallback6 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f65fd-102">ICorProfilerCallback6 Interface</span></span>
<span data-ttu-id="f65fd-103">[.NET Framework 4.5.2 以降のバージョンでのみでサポート]</span><span class="sxs-lookup"><span data-stu-id="f65fd-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="f65fd-104">アセンブリが読み込まれていることをプロファイラーに通知するために共通言語ランタイムが使用するコールバックメソッドを提供する[ICorProfilerCallback5](icorprofilercallback5-interface.md)のサブクラス。</span><span class="sxs-lookup"><span data-stu-id="f65fd-104">A subclass of [ICorProfilerCallback5](icorprofilercallback5-interface.md) that provides a callback method that the common language runtime uses to notify a profiler that an assembly is loading.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f65fd-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="f65fd-105">Methods</span></span>  
  
|<span data-ttu-id="f65fd-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="f65fd-106">Method</span></span>|<span data-ttu-id="f65fd-107">説明</span><span class="sxs-lookup"><span data-stu-id="f65fd-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f65fd-108">GetAssemblyReferences メソッド</span><span class="sxs-lookup"><span data-stu-id="f65fd-108">GetAssemblyReferences Method</span></span>](icorprofilercallback6-getassemblyreferences-method.md)|<span data-ttu-id="f65fd-109">共通言語ランタイムがアセンブリ参照クロージャのウォークを実行するときに、アセンブリがごく初期のローディング状態であることをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="f65fd-109">Notifies the profiler that an assembly is in a very early loading stage, when the common language runtime performs an assembly reference closure walk.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f65fd-110">解説</span><span class="sxs-lookup"><span data-stu-id="f65fd-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f65fd-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="f65fd-111">Requirements</span></span>  
 <span data-ttu-id="f65fd-112">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f65fd-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f65fd-113">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f65fd-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f65fd-114">**.NET Framework のバージョン:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f65fd-114">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f65fd-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="f65fd-115">See also</span></span>

- [<span data-ttu-id="f65fd-116">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="f65fd-116">Profiling Interfaces</span></span>](profiling-interfaces.md)
