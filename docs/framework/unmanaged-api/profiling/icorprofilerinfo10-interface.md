---
title: ICorProfilerInfo10 インターフェイス
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: 30179c7c198a343baa3fa01ae64f6d580a3f9e7e
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452202"
---
# <a name="icorprofilerinfo10-interface"></a><span data-ttu-id="05bfb-102">ICorProfilerInfo10 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="05bfb-102">ICorProfilerInfo10 Interface</span></span>

<span data-ttu-id="05bfb-103">関数 IL の変更、ランタイムからの情報のクエリ、およびランタイムの中断と再開を行うメソッドを提供する[ICorProfilerInfo9](icorprofilerinfo9-interface.md)のサブクラス。</span><span class="sxs-lookup"><span data-stu-id="05bfb-103">A subclass of [ICorProfilerInfo9](icorprofilerinfo9-interface.md) that provides methods to modify function IL, query information from the runtime, and suspend and resume the runtime.</span></span>

## <a name="methods"></a><span data-ttu-id="05bfb-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="05bfb-104">Methods</span></span>  

| <span data-ttu-id="05bfb-105">方法</span><span class="sxs-lookup"><span data-stu-id="05bfb-105">Method</span></span>|<span data-ttu-id="05bfb-106">説明</span><span class="sxs-lookup"><span data-stu-id="05bfb-106">Description</span></span>|  
| ------------|-----------------|  
|[<span data-ttu-id="05bfb-107">EnumerateObjectReferences メソッド</span><span class="sxs-lookup"><span data-stu-id="05bfb-107">EnumerateObjectReferences Method</span></span>](icorprofilerinfo10-enumerateobjectreferences-method.md)|<span data-ttu-id="05bfb-108">ObjectID、callback、および clientData を指定すると、各オブジェクト参照 (存在する場合) が列挙されます。</span><span class="sxs-lookup"><span data-stu-id="05bfb-108">Given an ObjectID, callback and clientData, enumerates each object reference (if any).</span></span> |
|[<span data-ttu-id="05bfb-109">IsFrozenObject メソッド</span><span class="sxs-lookup"><span data-stu-id="05bfb-109">IsFrozenObject Method</span></span>](icorprofilerinfo10-isfrozenobject-method.md)|<span data-ttu-id="05bfb-110">ObjectID が指定された場合、オブジェクトが読み取り専用セグメント内にあるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="05bfb-110">Given an ObjectID, determines whether the object is in a read-only segment.</span></span> |
|[<span data-ttu-id="05bfb-111">GetLOHObjectSizeThreshold メソッド</span><span class="sxs-lookup"><span data-stu-id="05bfb-111">GetLOHObjectSizeThreshold Method</span></span>](icorprofilerinfo10-getlohobjectsizethreshold-method.md)|<span data-ttu-id="05bfb-112">構成された LOH しきい値の値を取得します。</span><span class="sxs-lookup"><span data-stu-id="05bfb-112">Gets the value of the configured LOH threshold.</span></span> |
|[<span data-ttu-id="05bfb-113">RequestReJITWithInliners メソッド</span><span class="sxs-lookup"><span data-stu-id="05bfb-113">RequestReJITWithInliners Method</span></span>](icorprofilerinfo10-requestrejitwithinliners-method.md)| <span data-ttu-id="05bfb-114">要求されたメソッドのほか、要求されたメソッドの inliners を再適用します。</span><span class="sxs-lookup"><span data-stu-id="05bfb-114">ReJITs the methods requested, as well as any inliners of the methods requested.</span></span>  |
|[<span data-ttu-id="05bfb-115">SuspendRuntime メソッド</span><span class="sxs-lookup"><span data-stu-id="05bfb-115">SuspendRuntime Method</span></span>](icorprofilerinfo10-suspendruntime-method.md)| <span data-ttu-id="05bfb-116">GC を実行せずにランタイムを中断します。</span><span class="sxs-lookup"><span data-stu-id="05bfb-116">Suspends the runtime without performing a GC.</span></span> |
|[<span data-ttu-id="05bfb-117">ResumeRuntime メソッド</span><span class="sxs-lookup"><span data-stu-id="05bfb-117">ResumeRuntime Method</span></span>](icorprofilerinfo10-resumeruntime-method.md)| <span data-ttu-id="05bfb-118">GC を実行せずにランタイムを再開します。</span><span class="sxs-lookup"><span data-stu-id="05bfb-118">Resumes the runtime without performing a GC.</span></span> |

## <a name="requirements"></a><span data-ttu-id="05bfb-119">要件</span><span class="sxs-lookup"><span data-stu-id="05bfb-119">Requirements</span></span>  
<span data-ttu-id="05bfb-120">**プラットフォーム:** 「 [.Net Core でサポートされるオペレーティングシステム](../../../core/install/dependencies.md?pivots=os-windows)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="05bfb-120">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?pivots=os-windows).</span></span>  
<span data-ttu-id="05bfb-121">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="05bfb-121">**Header:** CorProf.idl, CorProf.h</span></span>  
<span data-ttu-id="05bfb-122">**.Net のバージョン:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="05bfb-122">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span> 

## <a name="see-also"></a><span data-ttu-id="05bfb-123">参照</span><span class="sxs-lookup"><span data-stu-id="05bfb-123">See also</span></span>

- [<span data-ttu-id="05bfb-124">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="05bfb-124">Profiling Interfaces</span></span>](profiling-interfaces.md)
