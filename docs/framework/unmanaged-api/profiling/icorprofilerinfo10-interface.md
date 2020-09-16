---
title: ICorProfilerInfo10 インターフェイス
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: 7e483bae9b7898e25c376fa92d0449fc49c6f9ee
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90548687"
---
# <a name="icorprofilerinfo10-interface"></a><span data-ttu-id="b6424-102">ICorProfilerInfo10 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b6424-102">ICorProfilerInfo10 Interface</span></span>

<span data-ttu-id="b6424-103">関数 IL の変更、ランタイムからの情報のクエリ、およびランタイムの中断と再開を行うメソッドを提供する [ICorProfilerInfo9](icorprofilerinfo9-interface.md) のサブクラス。</span><span class="sxs-lookup"><span data-stu-id="b6424-103">A subclass of [ICorProfilerInfo9](icorprofilerinfo9-interface.md) that provides methods to modify function IL, query information from the runtime, and suspend and resume the runtime.</span></span>

## <a name="methods"></a><span data-ttu-id="b6424-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="b6424-104">Methods</span></span>  

| <span data-ttu-id="b6424-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="b6424-105">Method</span></span>|<span data-ttu-id="b6424-106">説明</span><span class="sxs-lookup"><span data-stu-id="b6424-106">Description</span></span>|  
| ------------|-----------------|  
|[<span data-ttu-id="b6424-107">EnumerateObjectReferences メソッド</span><span class="sxs-lookup"><span data-stu-id="b6424-107">EnumerateObjectReferences Method</span></span>](icorprofilerinfo10-enumerateobjectreferences-method.md)|<span data-ttu-id="b6424-108">ObjectID、callback、および clientData を指定すると、各オブジェクト参照 (存在する場合) が列挙されます。</span><span class="sxs-lookup"><span data-stu-id="b6424-108">Given an ObjectID, callback and clientData, enumerates each object reference (if any).</span></span> |
|[<span data-ttu-id="b6424-109">IsFrozenObject メソッド</span><span class="sxs-lookup"><span data-stu-id="b6424-109">IsFrozenObject Method</span></span>](icorprofilerinfo10-isfrozenobject-method.md)|<span data-ttu-id="b6424-110">ObjectID が指定された場合、オブジェクトが読み取り専用セグメント内にあるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="b6424-110">Given an ObjectID, determines whether the object is in a read-only segment.</span></span> |
|[<span data-ttu-id="b6424-111">GetLOHObjectSizeThreshold メソッド</span><span class="sxs-lookup"><span data-stu-id="b6424-111">GetLOHObjectSizeThreshold Method</span></span>](icorprofilerinfo10-getlohobjectsizethreshold-method.md)|<span data-ttu-id="b6424-112">構成された LOH しきい値の値を取得します。</span><span class="sxs-lookup"><span data-stu-id="b6424-112">Gets the value of the configured LOH threshold.</span></span> |
|[<span data-ttu-id="b6424-113">RequestReJITWithInliners メソッド</span><span class="sxs-lookup"><span data-stu-id="b6424-113">RequestReJITWithInliners Method</span></span>](icorprofilerinfo10-requestrejitwithinliners-method.md)| <span data-ttu-id="b6424-114">要求されたメソッドのほか、要求されたメソッドの inliners を再適用します。</span><span class="sxs-lookup"><span data-stu-id="b6424-114">ReJITs the methods requested, as well as any inliners of the methods requested.</span></span>  |
|[<span data-ttu-id="b6424-115">SuspendRuntime メソッド</span><span class="sxs-lookup"><span data-stu-id="b6424-115">SuspendRuntime Method</span></span>](icorprofilerinfo10-suspendruntime-method.md)| <span data-ttu-id="b6424-116">GC を実行せずにランタイムを中断します。</span><span class="sxs-lookup"><span data-stu-id="b6424-116">Suspends the runtime without performing a GC.</span></span> |
|[<span data-ttu-id="b6424-117">ResumeRuntime メソッド</span><span class="sxs-lookup"><span data-stu-id="b6424-117">ResumeRuntime Method</span></span>](icorprofilerinfo10-resumeruntime-method.md)| <span data-ttu-id="b6424-118">GC を実行せずにランタイムを再開します。</span><span class="sxs-lookup"><span data-stu-id="b6424-118">Resumes the runtime without performing a GC.</span></span> |

## <a name="requirements"></a><span data-ttu-id="b6424-119">必要条件</span><span class="sxs-lookup"><span data-stu-id="b6424-119">Requirements</span></span>  
<span data-ttu-id="b6424-120">**プラットフォーム:** 「 [.Net Core でサポートされるオペレーティングシステム](../../../core/install/windows.md?pivots=os-windows)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6424-120">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>  
<span data-ttu-id="b6424-121">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b6424-121">**Header:** CorProf.idl, CorProf.h</span></span>  
<span data-ttu-id="b6424-122">**.Net のバージョン:**[!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b6424-122">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="b6424-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="b6424-123">See also</span></span>

- [<span data-ttu-id="b6424-124">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="b6424-124">Profiling Interfaces</span></span>](profiling-interfaces.md)
