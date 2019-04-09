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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3bad1cc71b9a27896141837a6d342f2cfe068fc5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59089733"
---
# <a name="icorprofilerassemblyreferenceprovider-interface"></a><span data-ttu-id="1aa1c-102">ICorProfilerAssemblyReferenceProvider インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1aa1c-102">ICorProfilerAssemblyReferenceProvider Interface</span></span>
<span data-ttu-id="1aa1c-103">[.NET Framework 4.5.2 以降のバージョンでのみでサポート]</span><span class="sxs-lookup"><span data-stu-id="1aa1c-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="1aa1c-104">プロファイラーを追加するアセンブリ参照の共通言語ランタイム (CLR) に通知できるように、 [icorprofilercallback::moduleloadfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)コールバック。</span><span class="sxs-lookup"><span data-stu-id="1aa1c-104">Enables the profiler to inform the common language runtime (CLR) of assembly references that the profiler will add in the [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1aa1c-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="1aa1c-105">Methods</span></span>  
  
|<span data-ttu-id="1aa1c-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="1aa1c-106">Method</span></span>|<span data-ttu-id="1aa1c-107">説明</span><span class="sxs-lookup"><span data-stu-id="1aa1c-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1aa1c-108">AddAssemblyReference メソッド</span><span class="sxs-lookup"><span data-stu-id="1aa1c-108">AddAssemblyReference Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md)|<span data-ttu-id="1aa1c-109">プロファイラーを計画に追加するアセンブリ参照の CLR に通知、 [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)コールバック。</span><span class="sxs-lookup"><span data-stu-id="1aa1c-109">Informs the CLR of an assembly reference that the profiler plans to add in the [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1aa1c-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="1aa1c-110">Remarks</span></span>  
 <span data-ttu-id="1aa1c-111">CLR プロファイラーから渡される、`ICorProfilerAssemblyReferenceProvider`インターフェイス オブジェクト、 [icorprofilercallback 6::getassemblyreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md)コールバック。</span><span class="sxs-lookup"><span data-stu-id="1aa1c-111">The CLR passes the profiler an `ICorProfilerAssemblyReferenceProvider` interface object in the [ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback.</span></span> <span data-ttu-id="1aa1c-112">これにより、プロファイラーがプロファイラーが後で追加する予定のあるアセンブリ参照の CLR に通知する、 [icorprofilercallback::moduleloadfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="1aa1c-112">This enables the profiler to inform the CLR of assembly references that the profiler plans to add later in the [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md).</span></span> <span data-ttu-id="1aa1c-113">コールバック。</span><span class="sxs-lookup"><span data-stu-id="1aa1c-113">callback.</span></span> <span data-ttu-id="1aa1c-114">これにより、CLR のアセンブリ参照クロージャ ウォーカーの正確性とアセンブリが共有可能かどうかを判断するアルゴリズムが強化されます。</span><span class="sxs-lookup"><span data-stu-id="1aa1c-114">This improves the accuracy of the CLR's assembly reference closure walker and its algorithms for determining whether assemblies may be shared.</span></span>  
  
 <span data-ttu-id="1aa1c-115">このインターフェイスでのみ使用する、 [icorprofilercallback 6::getassemblyreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md)このインターフェイス オブジェクトをプロファイラーに渡されるコールバック。</span><span class="sxs-lookup"><span data-stu-id="1aa1c-115">This interface can be used only in the [ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback that passes this interface object to the profiler.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1aa1c-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="1aa1c-116">Requirements</span></span>  
 <span data-ttu-id="1aa1c-117">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1aa1c-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1aa1c-118">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1aa1c-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 **<span data-ttu-id="1aa1c-119">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="1aa1c-119">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1aa1c-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="1aa1c-120">See also</span></span>

- [<span data-ttu-id="1aa1c-121">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="1aa1c-121">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
