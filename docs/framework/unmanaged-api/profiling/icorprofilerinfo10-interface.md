---
title: ICorProfilerInfo10 インターフェイス
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: 4c5d553744008734037975d6e63e1b07b89cf886
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175071"
---
# <a name="icorprofilerinfo10-interface"></a><span data-ttu-id="79fea-102">ICorProfilerInfo10 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="79fea-102">ICorProfilerInfo10 Interface</span></span>

<span data-ttu-id="79fea-103">関数 IL を変更し、ランタイムから情報を照会し、ランタイムを中断および再開するためのメソッドを提供する[ICorProfilerInfo9](icorprofilerinfo9-interface.md)のサブクラス。</span><span class="sxs-lookup"><span data-stu-id="79fea-103">A subclass of [ICorProfilerInfo9](icorprofilerinfo9-interface.md) that provides methods to modify function IL, query information from the runtime, and suspend and resume the runtime.</span></span>

## <a name="methods"></a><span data-ttu-id="79fea-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="79fea-104">Methods</span></span>  

| <span data-ttu-id="79fea-105">Method</span><span class="sxs-lookup"><span data-stu-id="79fea-105">Method</span></span>|<span data-ttu-id="79fea-106">説明</span><span class="sxs-lookup"><span data-stu-id="79fea-106">Description</span></span>|  
| ------------|-----------------|  
|[<span data-ttu-id="79fea-107">EnumerateObjectReferences メソッド</span><span class="sxs-lookup"><span data-stu-id="79fea-107">EnumerateObjectReferences Method</span></span>](icorprofilerinfo10-enumerateobjectreferences-method.md)|<span data-ttu-id="79fea-108">ObjectID、コールバック、および clientData を指定すると、各オブジェクト参照 (存在する場合) が列挙されます。</span><span class="sxs-lookup"><span data-stu-id="79fea-108">Given an ObjectID, callback and clientData, enumerates each object reference (if any).</span></span> |
|[<span data-ttu-id="79fea-109">IsFrozenObject メソッド</span><span class="sxs-lookup"><span data-stu-id="79fea-109">IsFrozenObject Method</span></span>](icorprofilerinfo10-isfrozenobject-method.md)|<span data-ttu-id="79fea-110">ObjectID を指定すると、オブジェクトが読み取り専用セグメント内にあるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="79fea-110">Given an ObjectID, determines whether the object is in a read-only segment.</span></span> |
|[<span data-ttu-id="79fea-111">GetLOHObjectSizeThreshold メソッド</span><span class="sxs-lookup"><span data-stu-id="79fea-111">GetLOHObjectSizeThreshold Method</span></span>](icorprofilerinfo10-getlohobjectsizethreshold-method.md)|<span data-ttu-id="79fea-112">構成済みの LOH しきい値の値を取得します。</span><span class="sxs-lookup"><span data-stu-id="79fea-112">Gets the value of the configured LOH threshold.</span></span> |
|[<span data-ttu-id="79fea-113">RequestReJITWithInliners メソッド</span><span class="sxs-lookup"><span data-stu-id="79fea-113">RequestReJITWithInliners Method</span></span>](icorprofilerinfo10-requestrejitwithinliners-method.md)| <span data-ttu-id="79fea-114">要求されたメソッドと、要求されたメソッドのインライナーを REJIT します。</span><span class="sxs-lookup"><span data-stu-id="79fea-114">ReJITs the methods requested, as well as any inliners of the methods requested.</span></span>  |
|[<span data-ttu-id="79fea-115">SuspendRuntime メソッド</span><span class="sxs-lookup"><span data-stu-id="79fea-115">SuspendRuntime Method</span></span>](icorprofilerinfo10-suspendruntime-method.md)| <span data-ttu-id="79fea-116">GC を実行せずにランタイムを中断します。</span><span class="sxs-lookup"><span data-stu-id="79fea-116">Suspends the runtime without performing a GC.</span></span> |
|[<span data-ttu-id="79fea-117">ResumeRuntime メソッド</span><span class="sxs-lookup"><span data-stu-id="79fea-117">ResumeRuntime Method</span></span>](icorprofilerinfo10-resumeruntime-method.md)| <span data-ttu-id="79fea-118">GC を実行せずにランタイムを再開します。</span><span class="sxs-lookup"><span data-stu-id="79fea-118">Resumes the runtime without performing a GC.</span></span> |

## <a name="requirements"></a><span data-ttu-id="79fea-119">必要条件</span><span class="sxs-lookup"><span data-stu-id="79fea-119">Requirements</span></span>  
<span data-ttu-id="79fea-120">**プラットフォーム:** NET [Core サポートされるオペレーティング システム](../../../core/install/dependencies.md?pivots=os-windows)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="79fea-120">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?pivots=os-windows).</span></span>  
<span data-ttu-id="79fea-121">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="79fea-121">**Header:** CorProf.idl, CorProf.h</span></span>  
<span data-ttu-id="79fea-122">**.NET バージョン:**[!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="79fea-122">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="79fea-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="79fea-123">See also</span></span>

- [<span data-ttu-id="79fea-124">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="79fea-124">Profiling Interfaces</span></span>](profiling-interfaces.md)
