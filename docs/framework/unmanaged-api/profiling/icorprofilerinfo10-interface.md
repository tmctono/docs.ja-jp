---
title: ICorProfilerInfo10 インターフェイス
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: 06cce79fbb2b2eb143e77e3c6fda194e47d4f4f3
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2019
ms.locfileid: "70928800"
---
# <a name="icorprofilerinfo10-interface"></a><span data-ttu-id="e7dce-102">ICorProfilerInfo10 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e7dce-102">ICorProfilerInfo10 Interface</span></span>

<span data-ttu-id="e7dce-103">関数 IL の変更、ランタイムからの情報のクエリ、およびランタイムの中断と再開を行うメソッドを提供する[ICorProfilerInfo9](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo9-interface.md)のサブクラス。</span><span class="sxs-lookup"><span data-stu-id="e7dce-103">A subclass of [ICorProfilerInfo9](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo9-interface.md) that provides methods to modify function IL, query information from the runtime, and suspend and resume the runtime.</span></span>

## <a name="methods"></a><span data-ttu-id="e7dce-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="e7dce-104">Methods</span></span>  

| <span data-ttu-id="e7dce-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="e7dce-105">Method</span></span>|<span data-ttu-id="e7dce-106">説明</span><span class="sxs-lookup"><span data-stu-id="e7dce-106">Description</span></span>|  
| ------------|-----------------|  
|[<span data-ttu-id="e7dce-107">EnumerateObjectReferences メソッド</span><span class="sxs-lookup"><span data-stu-id="e7dce-107">EnumerateObjectReferences Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-enumerateobjectreferences-method.md)|<span data-ttu-id="e7dce-108">ObjectID、callback、および clientData を指定すると、各オブジェクト参照 (存在する場合) が列挙されます。</span><span class="sxs-lookup"><span data-stu-id="e7dce-108">Given an ObjectID, callback and clientData, enumerates each object reference (if any).</span></span> |
|[<span data-ttu-id="e7dce-109">IsFrozenObject メソッド</span><span class="sxs-lookup"><span data-stu-id="e7dce-109">IsFrozenObject Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-isfrozenobject-method.md)|<span data-ttu-id="e7dce-110">ObjectID が指定された場合、オブジェクトが読み取り専用セグメント内にあるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="e7dce-110">Given an ObjectID, determines whether the object is in a read-only segment.</span></span> |
|[<span data-ttu-id="e7dce-111">GetLOHObjectSizeThreshold メソッド</span><span class="sxs-lookup"><span data-stu-id="e7dce-111">GetLOHObjectSizeThreshold Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-getlohobjectsizethreshold-method.md)|<span data-ttu-id="e7dce-112">構成された LOH しきい値の値を取得します。</span><span class="sxs-lookup"><span data-stu-id="e7dce-112">Gets the value of the configured LOH threshold.</span></span> |
|[<span data-ttu-id="e7dce-113">RequestReJITWithInliners メソッド</span><span class="sxs-lookup"><span data-stu-id="e7dce-113">RequestReJITWithInliners Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-requestrejitwithinliners-method.md)| <span data-ttu-id="e7dce-114">要求されたメソッドのほか、要求されたメソッドの inliners を再適用します。</span><span class="sxs-lookup"><span data-stu-id="e7dce-114">ReJITs the methods requested, as well as any inliners of the methods requested.</span></span>  |
|[<span data-ttu-id="e7dce-115">SuspendRuntime メソッド</span><span class="sxs-lookup"><span data-stu-id="e7dce-115">SuspendRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-suspendruntime-method.md)| <span data-ttu-id="e7dce-116">GC を実行せずにランタイムを中断します。</span><span class="sxs-lookup"><span data-stu-id="e7dce-116">Suspends the runtime without performing a GC.</span></span> |
|[<span data-ttu-id="e7dce-117">ResumeRuntime メソッド</span><span class="sxs-lookup"><span data-stu-id="e7dce-117">ResumeRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-resumeruntime-method.md)| <span data-ttu-id="e7dce-118">GC を実行せずにランタイムを再開します。</span><span class="sxs-lookup"><span data-stu-id="e7dce-118">Resumes the runtime without performing a GC.</span></span> |

## <a name="requirements"></a><span data-ttu-id="e7dce-119">必要条件</span><span class="sxs-lookup"><span data-stu-id="e7dce-119">Requirements</span></span>  
<span data-ttu-id="e7dce-120">**・** 「 [.Net Core でサポートされるオペレーティングシステム](../../../core/windows-prerequisites.md#net-core-supported-operating-systems)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e7dce-120">**Platforms:** See [.NET Core supported operating systems](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span></span>  
<span data-ttu-id="e7dce-121">**ヘッダー:** Corprof.idl、Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="e7dce-121">**Header:** CorProf.idl, CorProf.h</span></span>  
<span data-ttu-id="e7dce-122">**.Net のバージョン:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e7dce-122">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span> 

## <a name="see-also"></a><span data-ttu-id="e7dce-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="e7dce-123">See also</span></span>

- [<span data-ttu-id="e7dce-124">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="e7dce-124">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
