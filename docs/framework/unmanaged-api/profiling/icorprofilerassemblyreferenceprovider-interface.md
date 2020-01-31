---
title: ICorProfilerAssemblyReferenceProvider インターフェイス
ms.date: 03/30/2017
api_name:
- ICorProfilerAssemblyReferenceProvider
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: 17205116-66e1-4acc-8f01-532fb3867028
topic_type:
- apiref
ms.openlocfilehash: 13a298451c3e8e1c5809cc1cb222acb5ab85714b
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866690"
---
# <a name="icorprofilerassemblyreferenceprovider-interface"></a><span data-ttu-id="dcd6a-102">ICorProfilerAssemblyReferenceProvider インターフェイス</span><span class="sxs-lookup"><span data-stu-id="dcd6a-102">ICorProfilerAssemblyReferenceProvider Interface</span></span>
<span data-ttu-id="dcd6a-103">[.NET Framework 4.5.2 以降のバージョンでのみでサポート]</span><span class="sxs-lookup"><span data-stu-id="dcd6a-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="dcd6a-104">プロファイラーが[ICorProfilerCallback:: ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md)コールバックに追加するアセンブリ参照の共通言語ランタイム (CLR) を通知できるようにします。</span><span class="sxs-lookup"><span data-stu-id="dcd6a-104">Enables the profiler to inform the common language runtime (CLR) of assembly references that the profiler will add in the [ICorProfilerCallback::ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="dcd6a-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="dcd6a-105">Methods</span></span>  
  
|<span data-ttu-id="dcd6a-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="dcd6a-106">Method</span></span>|<span data-ttu-id="dcd6a-107">説明</span><span class="sxs-lookup"><span data-stu-id="dcd6a-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="dcd6a-108">AddAssemblyReference メソッド</span><span class="sxs-lookup"><span data-stu-id="dcd6a-108">AddAssemblyReference Method</span></span>](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md)|<span data-ttu-id="dcd6a-109">プロファイラーが[Moduleloadfinished](icorprofilercallback-moduleloadfinished-method.md)コールバックに追加する予定のアセンブリ参照を CLR に通知します。</span><span class="sxs-lookup"><span data-stu-id="dcd6a-109">Informs the CLR of an assembly reference that the profiler plans to add in the [ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dcd6a-110">コメント</span><span class="sxs-lookup"><span data-stu-id="dcd6a-110">Remarks</span></span>  
 <span data-ttu-id="dcd6a-111">CLR は、 [ICorProfilerCallback6:: GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md)コールバックでプロファイラーに `ICorProfilerAssemblyReferenceProvider` インターフェイスオブジェクトを渡します。</span><span class="sxs-lookup"><span data-stu-id="dcd6a-111">The CLR passes the profiler an `ICorProfilerAssemblyReferenceProvider` interface object in the [ICorProfilerCallback6::GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) callback.</span></span> <span data-ttu-id="dcd6a-112">これにより、プロファイラーは、後で[ICorProfilerCallback:: ModuleLoadFinished 終了](icorprofilercallback-moduleloadfinished-method.md)した後に追加することを計画しているアセンブリ参照を CLR に通知できます。</span><span class="sxs-lookup"><span data-stu-id="dcd6a-112">This enables the profiler to inform the CLR of assembly references that the profiler plans to add later in the [ICorProfilerCallback::ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md).</span></span> <span data-ttu-id="dcd6a-113">コールバック。</span><span class="sxs-lookup"><span data-stu-id="dcd6a-113">callback.</span></span> <span data-ttu-id="dcd6a-114">これにより、CLR のアセンブリ参照クロージャ ウォーカーの正確性とアセンブリが共有可能かどうかを判断するアルゴリズムが強化されます。</span><span class="sxs-lookup"><span data-stu-id="dcd6a-114">This improves the accuracy of the CLR's assembly reference closure walker and its algorithms for determining whether assemblies may be shared.</span></span>  
  
 <span data-ttu-id="dcd6a-115">このインターフェイスは、このインターフェイスオブジェクトをプロファイラーに渡す[ICorProfilerCallback6:: GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md)コールバックでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="dcd6a-115">This interface can be used only in the [ICorProfilerCallback6::GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) callback that passes this interface object to the profiler.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dcd6a-116">要件</span><span class="sxs-lookup"><span data-stu-id="dcd6a-116">Requirements</span></span>  
 <span data-ttu-id="dcd6a-117">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dcd6a-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dcd6a-118">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="dcd6a-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="dcd6a-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dcd6a-119">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcd6a-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="dcd6a-120">See also</span></span>

- [<span data-ttu-id="dcd6a-121">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="dcd6a-121">Profiling Interfaces</span></span>](profiling-interfaces.md)
