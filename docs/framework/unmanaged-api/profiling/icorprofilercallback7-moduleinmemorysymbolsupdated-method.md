---
title: 'ICorProfilerCallback7:: Moduleinmemory メソッド'
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback7.ModuleInMemorySymbolsUpdated
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.assetid: f362a896-3247-4894-9727-e48dbbcd2c78
ms.openlocfilehash: f6dd10d196ffd3a653584e1bc8d1a5643850bc33
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136603"
---
# <a name="icorprofilercallback7moduleinmemorysymbolsupdated-method"></a><span data-ttu-id="e103e-102">ICorProfilerCallback7:: Moduleinmemory メソッド</span><span class="sxs-lookup"><span data-stu-id="e103e-102">ICorProfilerCallback7::ModuleInMemorySymbolsUpdated Method</span></span>
<span data-ttu-id="e103e-103">[.NET Framework 4.6.1 以降のバージョンでのみでサポート]</span><span class="sxs-lookup"><span data-stu-id="e103e-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="e103e-104">メモリ内モジュールに関連付けられているシンボルストリームが更新されるたびに、プロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="e103e-104">Notifies the profiler whenever the symbol stream associated with an in-memory module is updated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e103e-105">構文</span><span class="sxs-lookup"><span data-stu-id="e103e-105">Syntax</span></span>  
  
```cpp  
HRESULT ModuleInMemorySymbolsUpdated(  
     ModuleID moduleId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e103e-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e103e-106">Parameters</span></span>  
 <span data-ttu-id="e103e-107">[入力] `moduleId`</span><span class="sxs-lookup"><span data-stu-id="e103e-107">[in] `moduleId`</span></span>  
 <span data-ttu-id="e103e-108">シンボルストリームが更新されるメモリ内モジュールの識別子。</span><span class="sxs-lookup"><span data-stu-id="e103e-108">The identifier of the in-memory module whose symbol stream is updated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e103e-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="e103e-109">Remarks</span></span>  
 <span data-ttu-id="e103e-110">このコールバックは、 [ICorProfilerCallback5:: SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)メソッドを呼び出すときに、 [COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md)イベントマスクフラグを設定することによって制御されます。</span><span class="sxs-lookup"><span data-stu-id="e103e-110">This callback is controlled by setting the [COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) event mask flag when calling the [ICorProfilerCallback5::SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e103e-111">このイベントは、<xref:System.Reflection.Emit> Api を使用して暗黙的に作成または変更されたシンボルに対しては、現在発生していません。</span><span class="sxs-lookup"><span data-stu-id="e103e-111">This event is not currently raised for symbols implicitly created or modified via <xref:System.Reflection.Emit> APIs.</span></span>  
  
 <span data-ttu-id="e103e-112">アセンブリのシンボルを指定するための `rawSymbolStore` 引数を含むマネージ <xref:System.Reflection.Assembly.Load*?displayProperty=nameWithType> メソッドのオーバーロードの1つを呼び出すことによって、シンボルが事前に提供されている場合でも、ランタイムは実際にシンボリックデータをモジュールに関連付けます。[Moduleloadfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)コールバックが発生しました。</span><span class="sxs-lookup"><span data-stu-id="e103e-112">Even when symbols are provided up front in a call to one of the overloads of the managed <xref:System.Reflection.Assembly.Load*?displayProperty=nameWithType> methods that includes a `rawSymbolStore` argument to specify the symbols for the assembly, the runtime may not actually associate the symbolic data with the module until after the [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback has occurred.</span></span> <span data-ttu-id="e103e-113">このイベントは、後でこのようなモジュールのシンボルを収集する機会を提供します。</span><span class="sxs-lookup"><span data-stu-id="e103e-113">This event provides a later opportunity to collect symbols for such modules.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e103e-114">［要件］</span><span class="sxs-lookup"><span data-stu-id="e103e-114">Requirements</span></span>  
 <span data-ttu-id="e103e-115">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e103e-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e103e-116">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e103e-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e103e-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e103e-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e103e-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e103e-118">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e103e-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="e103e-119">See also</span></span>

- [<span data-ttu-id="e103e-120">ModuleLoadFinished メソッド</span><span class="sxs-lookup"><span data-stu-id="e103e-120">ModuleLoadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)
- [<span data-ttu-id="e103e-121">SetEventMask2 メソッド</span><span class="sxs-lookup"><span data-stu-id="e103e-121">SetEventMask2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)
- [<span data-ttu-id="e103e-122">ICorProfilerCallback7 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e103e-122">ICorProfilerCallback7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-interface.md)
