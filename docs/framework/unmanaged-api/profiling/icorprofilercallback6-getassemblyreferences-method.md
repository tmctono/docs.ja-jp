---
title: ICorProfilerCallback6::GetAssemblyReferences メソッド
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorProfilerCallback6.GetAssemblyReferences
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.assetid: 8b391afb-d79f-41bd-94ce-43ce62c6b5fc
topic_type:
- apiref
ms.openlocfilehash: d15f1b568c50cf4fca28966f94a6a4becf59e734
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141627"
---
# <a name="icorprofilercallback6getassemblyreferences-method"></a><span data-ttu-id="bcfa2-102">ICorProfilerCallback6::GetAssemblyReferences メソッド</span><span class="sxs-lookup"><span data-stu-id="bcfa2-102">ICorProfilerCallback6::GetAssemblyReferences Method</span></span>
<span data-ttu-id="bcfa2-103">[.NET Framework 4.5.2 以降のバージョンでのみでサポート]</span><span class="sxs-lookup"><span data-stu-id="bcfa2-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="bcfa2-104">共通言語ランタイムがアセンブリ参照クロージャのウォークを実行するときに、アセンブリがごく初期のローディング状態であることをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="bcfa2-104">Notifies the profiler that an assembly is in a very early loading stage, when the common language runtime performs an assembly reference closure walk.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bcfa2-105">構文</span><span class="sxs-lookup"><span data-stu-id="bcfa2-105">Syntax</span></span>  
  
```cpp
HRESULT GetAssemblyReferences(        [in, string] const WCHAR* wszAssemblyPath,  
        [in] ICorProfilerAssemblyReferenceProvider* pAsmRefProvider  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bcfa2-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="bcfa2-106">Parameters</span></span>  
 `wszAssemblyPath`  
 <span data-ttu-id="bcfa2-107">[in] メタデータが変更されるアセンブリのパスおよび名前。</span><span class="sxs-lookup"><span data-stu-id="bcfa2-107">[in] The path and name of the assembly whose metadata will be modified.</span></span>  
  
 `pAsmRefProvider`  
 <span data-ttu-id="bcfa2-108">から追加するアセンブリ参照を指定する[ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md)インターフェイスのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="bcfa2-108">[in] A pointer to the address of an [ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) interface that specifies the assembly references to add.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bcfa2-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="bcfa2-109">Return Value</span></span>  
 <span data-ttu-id="bcfa2-110">このコールバックからの戻り値は無視されます。</span><span class="sxs-lookup"><span data-stu-id="bcfa2-110">Return values from this callback are ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bcfa2-111">コメント</span><span class="sxs-lookup"><span data-stu-id="bcfa2-111">Remarks</span></span>  
 <span data-ttu-id="bcfa2-112">このコールバックは、 [ICorProfilerCallback5:: SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)メソッドを呼び出すときに、 [COR_PRF_HIGH_ADD_ASSEMBLY_REFERENCES](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md)イベントマスクフラグを設定することによって制御されます。</span><span class="sxs-lookup"><span data-stu-id="bcfa2-112">This callback is controlled by setting the [COR_PRF_HIGH_ADD_ASSEMBLY_REFERENCES](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) event mask flag when calling the [ICorProfilerCallback5::SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) method.</span></span> <span data-ttu-id="bcfa2-113">プロファイラーが[ICorProfilerCallback6:: GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback メソッドを登録すると、ランタイムは、読み込まれるアセンブリのパスと名前、およびそのメソッドへの[ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md)インターフェイスオブジェクトへのポインターを渡します。</span><span class="sxs-lookup"><span data-stu-id="bcfa2-113">If the profiler registers for the [ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback method, the runtime passes the path and name of the assembly to be loaded, along with a pointer to an [ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) interface object to that method.</span></span> <span data-ttu-id="bcfa2-114">その後、プロファイラーは、`GetAssemblyReferences` コールバックで指定されたアセンブリから参照する各ターゲットアセンブリの `COR_PRF_ASSEMBLY_REFERENCE_INFO` オブジェクトを使用して、 [ICorProfilerAssemblyReferenceProvider:: AddAssemblyReference](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md)メソッドを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="bcfa2-114">The profiler can then call the [ICorProfilerAssemblyReferenceProvider::AddAssemblyReference](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) method with a `COR_PRF_ASSEMBLY_REFERENCE_INFO` object for each target assembly it plans to reference from the assembly specified in the `GetAssemblyReferences` callback.</span></span>  
  
 <span data-ttu-id="bcfa2-115">`GetAssemblyReferences` コールバックを使用するのは、プロファイラーがアセンブリのメタデータを変更してアセンブリ参照を追加する必要がある場合のみです</span><span class="sxs-lookup"><span data-stu-id="bcfa2-115">Use the `GetAssemblyReferences` callback only if the profiler has to modify an assembly's metadata to add assembly references.</span></span> <span data-ttu-id="bcfa2-116">(ただし、アセンブリのメタデータの実際の変更は、 [ICorProfilerCallback:: ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)コールバックメソッドで行われることに注意してください)。プロファイラーは、モジュールが読み込まれたときにアセンブリ参照が追加されることを共通言語ランタイム (CLR) に通知するために、`GetAssemblyReferences` コールバックメソッドを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bcfa2-116">(But note that the actual modification of an assembly's metadata is done in the [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)callback method.) The profiler should implement the `GetAssemblyReferences` callback method to inform the common language runtime (CLR) that assembly references will be added when the module has been loaded.</span></span>  <span data-ttu-id="bcfa2-117">これにより、プロファイラーが後でメタデータのアセンブリ参照を変更するつもりでも、アセンブリが共有している "初期の段階で CLR によって行われた決定" は有効なままになります。</span><span class="sxs-lookup"><span data-stu-id="bcfa2-117">This helps ensure that assembly sharing decisions made by the CLR during this early stage remain valid although the profiler plans to modify the metadata assembly references later.</span></span>  <span data-ttu-id="bcfa2-118">このため一部のインスタンスでの、プロファイラーのメタデータ変更による `SECURITY_E_INCOMPATIBLE_SHARE` エラーの発生を回避できる場合があります。</span><span class="sxs-lookup"><span data-stu-id="bcfa2-118">This can avoid some instances in which profiler metadata modifications cause an `SECURITY_E_INCOMPATIBLE_SHARE` error.</span></span>  
  
 <span data-ttu-id="bcfa2-119">プロファイラーは、このメソッドによって提供される[ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md)オブジェクトを使用して、CLR アセンブリ参照クロージャのウォーカーにアセンブリ参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="bcfa2-119">The profiler uses the [ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) object provided by this method to add assembly references to the CLR assembly reference closure walker.</span></span>  <span data-ttu-id="bcfa2-120">[ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md)オブジェクトは、このコールバック内からのみ使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bcfa2-120">The [ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) object should be used only from within this callback.</span></span> <span data-ttu-id="bcfa2-121">このコールバックから[ICorProfilerAssemblyReferenceProvider:: AddAssemblyReference](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md)メソッドを呼び出すと、変更されたメタデータは生成されませんが、変更されたアセンブリ参照クロージャウォークでのみ発生します。</span><span class="sxs-lookup"><span data-stu-id="bcfa2-121">Calls to the [ICorProfilerAssemblyReferenceProvider::AddAssemblyReference](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) method from this callback don't result in modified metadata, but only in a modified assembly reference closure walk.</span></span> <span data-ttu-id="bcfa2-122">プロファイラーは、 [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)オブジェクトを使用して、参照元アセンブリの[ICorProfilerCallback:: moduleloadfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)コールバック内からアセンブリ参照を明示的に追加する必要があります。これは、`GetAssemblyReferences` コールバックが実装されている場合でも同様です。</span><span class="sxs-lookup"><span data-stu-id="bcfa2-122">The profiler will still have to use an [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) object to explicitly add assembly references from within the [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback for the referencing assembly, even if it implements the `GetAssemblyReferences` callback.</span></span>  
  
 <span data-ttu-id="bcfa2-123">プロファイラーは、同じアセンブリに対してこのコールバックへの重複する呼び出しを受け取るように準備する必要があります。また、同じ[ICorProfilerAssemblyReferenceProvider:: AddAssemblyReference](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md)呼び出しのセットを作成することによって、重複する各呼び出しに対して同じように応答する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bcfa2-123">The profiler should be prepared to receive duplicate calls to this callback for the same assembly, and should respond identically for each such duplicate call (by making the same set of [ICorProfilerAssemblyReferenceProvider::AddAssemblyReference](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) calls).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bcfa2-124">要件</span><span class="sxs-lookup"><span data-stu-id="bcfa2-124">Requirements</span></span>  
 <span data-ttu-id="bcfa2-125">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bcfa2-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bcfa2-126">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bcfa2-126">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bcfa2-127">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bcfa2-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bcfa2-128">**.NET Framework のバージョン:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bcfa2-128">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcfa2-129">参照</span><span class="sxs-lookup"><span data-stu-id="bcfa2-129">See also</span></span>

- [<span data-ttu-id="bcfa2-130">ICorProfilerCallback6 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bcfa2-130">ICorProfilerCallback6 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-interface.md)
- [<span data-ttu-id="bcfa2-131">ModuleLoadFinished メソッド</span><span class="sxs-lookup"><span data-stu-id="bcfa2-131">ModuleLoadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)
- [<span data-ttu-id="bcfa2-132">COR_PRF_ASSEMBLY_REFERENCE_INFO 構造体</span><span class="sxs-lookup"><span data-stu-id="bcfa2-132">COR_PRF_ASSEMBLY_REFERENCE_INFO Structure</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-assembly-reference-info-structure.md)
- [<span data-ttu-id="bcfa2-133">ICorProfilerAssemblyReferenceProvider インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bcfa2-133">ICorProfilerAssemblyReferenceProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md)
