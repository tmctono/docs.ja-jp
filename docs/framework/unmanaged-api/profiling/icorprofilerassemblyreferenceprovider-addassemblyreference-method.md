---
title: ICorProfilerAssemblyReferenceProvider::AddAssemblyReference メソッド
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorProfilerAssemblyReferenceProvider.AddAssemblyReference
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: 3d5af8e7-c337-48f4-9fa6-97c83878b9b1
topic_type:
- apiref
ms.openlocfilehash: 2325e3034dbf00441e587017affa65b80821fbb1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128751"
---
# <a name="icorprofilerassemblyreferenceprovideraddassemblyreference-method"></a><span data-ttu-id="bf36e-102">ICorProfilerAssemblyReferenceProvider::AddAssemblyReference メソッド</span><span class="sxs-lookup"><span data-stu-id="bf36e-102">ICorProfilerAssemblyReferenceProvider::AddAssemblyReference Method</span></span>
<span data-ttu-id="bf36e-103">[.NET Framework 4.5.2 以降のバージョンでのみでサポート]</span><span class="sxs-lookup"><span data-stu-id="bf36e-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="bf36e-104">プロファイラーが[ICorProfilerCallback:: ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)コールバックに追加することを計画しているアセンブリ参照の共通言語ランタイム (CLR) に通知します。</span><span class="sxs-lookup"><span data-stu-id="bf36e-104">Informs the common language runtime (CLR) of an assembly reference that the profiler plans to add in the [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf36e-105">構文</span><span class="sxs-lookup"><span data-stu-id="bf36e-105">Syntax</span></span>  
  
```cpp
HRESULT AddAssemblyReference(  
        const COR_PRF_ASSEMBLY_REFERENCE_INFO* pAssemblyRefInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bf36e-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="bf36e-106">Parameters</span></span>  
 <span data-ttu-id="bf36e-107">pAssemblyRefInfo</span><span class="sxs-lookup"><span data-stu-id="bf36e-107">pAssemblyRefInfo</span></span>  
 <span data-ttu-id="bf36e-108">アセンブリ参照クロージャウォークを実行するときに考慮する必要があるアセンブリ参照に関する情報を CLR に提供する[COR_PRF_ASSEMBLY_REFERENCE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-assembly-reference-info-structure.md)構造体へのポインター。</span><span class="sxs-lookup"><span data-stu-id="bf36e-108">A pointer to a [COR_PRF_ASSEMBLY_REFERENCE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-assembly-reference-info-structure.md) structure that provides the CLR with information about an assembly reference that it should consider when performing an assembly reference closure walk.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bf36e-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="bf36e-109">Remarks</span></span>  
 <span data-ttu-id="bf36e-110">プロファイラーは、 [ICorProfilerCallback6:: GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md)コールバックの `wszAssemblyPath` 引数で指定されたアセンブリから参照する対象アセンブリごとに、このメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="bf36e-110">The profiler calls this method for each target assembly it plans to reference from the assembly specified in the `wszAssemblyPath` argument of the [ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback.</span></span> <span data-ttu-id="bf36e-111">[ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md)インターフェイスオブジェクトは、プロファイラーの[ICorProfilerCallback6:: GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md)コールバックに、`wszAssemblyPath` 引数のアセンブリパスと名前と共に渡されます。</span><span class="sxs-lookup"><span data-stu-id="bf36e-111">The [ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) interface object is passed to the profiler's [ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback, along with the assembly path and name in the `wszAssemblyPath` argument.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf36e-112">［要件］</span><span class="sxs-lookup"><span data-stu-id="bf36e-112">Requirements</span></span>  
 <span data-ttu-id="bf36e-113">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bf36e-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf36e-114">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bf36e-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bf36e-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bf36e-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bf36e-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bf36e-116">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf36e-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="bf36e-117">See also</span></span>

- [<span data-ttu-id="bf36e-118">ICorProfilerAssemblyReferenceProvider インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bf36e-118">ICorProfilerAssemblyReferenceProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md)
- [<span data-ttu-id="bf36e-119">GetAssemblyReferences メソッド</span><span class="sxs-lookup"><span data-stu-id="bf36e-119">GetAssemblyReferences Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md)
- [<span data-ttu-id="bf36e-120">ModuleLoadFinished メソッド</span><span class="sxs-lookup"><span data-stu-id="bf36e-120">ModuleLoadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)
