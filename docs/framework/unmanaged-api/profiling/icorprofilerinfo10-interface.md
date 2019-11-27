---
title: ICorProfilerInfo10 インターフェイス
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: f2bc716110c14972e5b2c32bceb3123b16e87c61
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449845"
---
# <a name="icorprofilerinfo10-interface"></a><span data-ttu-id="43c79-102">ICorProfilerInfo10 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="43c79-102">ICorProfilerInfo10 Interface</span></span>

<span data-ttu-id="43c79-103">関数 IL の変更、ランタイムからの情報のクエリ、およびランタイムの中断と再開を行うメソッドを提供する[ICorProfilerInfo9](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo9-interface.md)のサブクラス。</span><span class="sxs-lookup"><span data-stu-id="43c79-103">A subclass of [ICorProfilerInfo9](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo9-interface.md) that provides methods to modify function IL, query information from the runtime, and suspend and resume the runtime.</span></span>

## <a name="methods"></a><span data-ttu-id="43c79-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="43c79-104">Methods</span></span>  

| <span data-ttu-id="43c79-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="43c79-105">Method</span></span>|<span data-ttu-id="43c79-106">説明</span><span class="sxs-lookup"><span data-stu-id="43c79-106">Description</span></span>|  
| ------------|-----------------|  
|[<span data-ttu-id="43c79-107">EnumerateObjectReferences メソッド</span><span class="sxs-lookup"><span data-stu-id="43c79-107">EnumerateObjectReferences Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-enumerateobjectreferences-method.md)|<span data-ttu-id="43c79-108">ObjectID、callback、および clientData を指定すると、各オブジェクト参照 (存在する場合) が列挙されます。</span><span class="sxs-lookup"><span data-stu-id="43c79-108">Given an ObjectID, callback and clientData, enumerates each object reference (if any).</span></span> |
|[<span data-ttu-id="43c79-109">IsFrozenObject メソッド</span><span class="sxs-lookup"><span data-stu-id="43c79-109">IsFrozenObject Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-isfrozenobject-method.md)|<span data-ttu-id="43c79-110">ObjectID が指定された場合、オブジェクトが読み取り専用セグメント内にあるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="43c79-110">Given an ObjectID, determines whether the object is in a read-only segment.</span></span> |
|[<span data-ttu-id="43c79-111">GetLOHObjectSizeThreshold メソッド</span><span class="sxs-lookup"><span data-stu-id="43c79-111">GetLOHObjectSizeThreshold Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-getlohobjectsizethreshold-method.md)|<span data-ttu-id="43c79-112">構成された LOH しきい値の値を取得します。</span><span class="sxs-lookup"><span data-stu-id="43c79-112">Gets the value of the configured LOH threshold.</span></span> |
|[<span data-ttu-id="43c79-113">RequestReJITWithInliners メソッド</span><span class="sxs-lookup"><span data-stu-id="43c79-113">RequestReJITWithInliners Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-requestrejitwithinliners-method.md)| <span data-ttu-id="43c79-114">要求されたメソッドのほか、要求されたメソッドの inliners を再適用します。</span><span class="sxs-lookup"><span data-stu-id="43c79-114">ReJITs the methods requested, as well as any inliners of the methods requested.</span></span>  |
|[<span data-ttu-id="43c79-115">SuspendRuntime メソッド</span><span class="sxs-lookup"><span data-stu-id="43c79-115">SuspendRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-suspendruntime-method.md)| <span data-ttu-id="43c79-116">GC を実行せずにランタイムを中断します。</span><span class="sxs-lookup"><span data-stu-id="43c79-116">Suspends the runtime without performing a GC.</span></span> |
|[<span data-ttu-id="43c79-117">ResumeRuntime メソッド</span><span class="sxs-lookup"><span data-stu-id="43c79-117">ResumeRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-resumeruntime-method.md)| <span data-ttu-id="43c79-118">GC を実行せずにランタイムを再開します。</span><span class="sxs-lookup"><span data-stu-id="43c79-118">Resumes the runtime without performing a GC.</span></span> |

## <a name="requirements"></a><span data-ttu-id="43c79-119">要件</span><span class="sxs-lookup"><span data-stu-id="43c79-119">Requirements</span></span>  
<span data-ttu-id="43c79-120">**プラットフォーム:** 「 [.Net Core でサポートされるオペレーティングシステム](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="43c79-120">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span></span>  
<span data-ttu-id="43c79-121">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="43c79-121">**Header:** CorProf.idl, CorProf.h</span></span>  
<span data-ttu-id="43c79-122">**.Net のバージョン:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43c79-122">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span> 

## <a name="see-also"></a><span data-ttu-id="43c79-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="43c79-123">See also</span></span>

- [<span data-ttu-id="43c79-124">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="43c79-124">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
