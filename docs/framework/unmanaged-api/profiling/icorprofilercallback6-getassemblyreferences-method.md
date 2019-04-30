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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2c5296fbab71c67572718a58fedb9f89b064f816
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62041497"
---
# <a name="icorprofilercallback6getassemblyreferences-method"></a><span data-ttu-id="0c884-102">ICorProfilerCallback6::GetAssemblyReferences メソッド</span><span class="sxs-lookup"><span data-stu-id="0c884-102">ICorProfilerCallback6::GetAssemblyReferences Method</span></span>
<span data-ttu-id="0c884-103">[.NET Framework 4.5.2 以降のバージョンでのみでサポート]</span><span class="sxs-lookup"><span data-stu-id="0c884-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="0c884-104">共通言語ランタイムがアセンブリ参照クロージャのウォークを実行するときに、アセンブリがごく初期のローディング状態であることをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="0c884-104">Notifies the profiler that an assembly is in a very early loading stage, when the common language runtime performs an assembly reference closure walk.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c884-105">構文</span><span class="sxs-lookup"><span data-stu-id="0c884-105">Syntax</span></span>  
  
```cpp
HRESULT GetAssemblyReferences(        [in, string] const WCHAR* wszAssemblyPath,  
        [in] ICorProfilerAssemblyReferenceProvider* pAsmRefProvider  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0c884-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0c884-106">Parameters</span></span>  
 `wszAssemblyPath`  
 <span data-ttu-id="0c884-107">[in] メタデータが変更されるアセンブリのパスおよび名前。</span><span class="sxs-lookup"><span data-stu-id="0c884-107">[in] The path and name of the assembly whose metadata will be modified.</span></span>  
  
 `pAsmRefProvider`  
 <span data-ttu-id="0c884-108">[in]アドレスへのポインター、 [ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md)アセンブリを指定するインターフェイスの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="0c884-108">[in] A pointer to the address of an [ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) interface that specifies the assembly references to add.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0c884-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="0c884-109">Return Value</span></span>  
 <span data-ttu-id="0c884-110">このコールバックからの戻り値は無視されます。</span><span class="sxs-lookup"><span data-stu-id="0c884-110">Return values from this callback are ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0c884-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="0c884-111">Remarks</span></span>  
 <span data-ttu-id="0c884-112">このコールバックは設定によって制御されます、 [COR_PRF_HIGH_ADD_ASSEMBLY_REFERENCES](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md)イベント マスク フラグを呼び出すときに、 [ICorProfilerCallback5::SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="0c884-112">This callback is controlled by setting the [COR_PRF_HIGH_ADD_ASSEMBLY_REFERENCES](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) event mask flag when calling the [ICorProfilerCallback5::SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) method.</span></span> <span data-ttu-id="0c884-113">用のプロファイラーを登録する場合、 [icorprofilercallback 6::getassemblyreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md)コールバック メソッド、ランタイムへのポインターと共に読み込まれるアセンブリの名前とパスを渡します、 [ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md)メソッドへのインターフェイスのオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="0c884-113">If the profiler registers for the [ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback method, the runtime passes the path and name of the assembly to be loaded, along with a pointer to an [ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) interface object to that method.</span></span> <span data-ttu-id="0c884-114">プロファイラーを呼び出すことが、 [icorprofilerassemblyreferenceprovider::addassemblyreference](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md)メソッドを`COR_PRF_ASSEMBLY_REFERENCE_INFO`で指定されたアセンブリから参照することを計画、各ターゲット アセンブリのオブジェクト、 `GetAssemblyReferences`コールバック。</span><span class="sxs-lookup"><span data-stu-id="0c884-114">The profiler can then call the [ICorProfilerAssemblyReferenceProvider::AddAssemblyReference](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) method with a `COR_PRF_ASSEMBLY_REFERENCE_INFO` object for each target assembly it plans to reference from the assembly specified in the `GetAssemblyReferences` callback.</span></span>  
  
 <span data-ttu-id="0c884-115">`GetAssemblyReferences` コールバックを使用するのは、プロファイラーがアセンブリのメタデータを変更してアセンブリ参照を追加する必要がある場合のみです</span><span class="sxs-lookup"><span data-stu-id="0c884-115">Use the `GetAssemblyReferences` callback only if the profiler has to modify an assembly's metadata to add assembly references.</span></span> <span data-ttu-id="0c884-116">(でアセンブリのメタデータの実際の変更が実行されるに注意してください、 [icorprofilercallback::moduleloadfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)コールバック メソッドです)。プロファイラーは `GetAssemblyReferences` コールバック メソッドを実装して、モジュールがロードされたときにアセンブリ参照が追加されることを共通言語ランタイム (CLR) に知らせる必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c884-116">(But note that the actual modification of an assembly's metadata is done in the [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)callback method.) The profiler should implement the `GetAssemblyReferences` callback method to inform the common language runtime (CLR) that assembly references will be added when the module has been loaded.</span></span>  <span data-ttu-id="0c884-117">これにより、プロファイラーが後でメタデータのアセンブリ参照を変更するつもりでも、アセンブリが共有している "初期の段階で CLR によって行われた決定" は有効なままになります。</span><span class="sxs-lookup"><span data-stu-id="0c884-117">This helps ensure that assembly sharing decisions made by the CLR during this early stage remain valid although the profiler plans to modify the metadata assembly references later.</span></span>  <span data-ttu-id="0c884-118">このため一部のインスタンスでの、プロファイラーのメタデータ変更による `SECURITY_E_INCOMPATIBLE_SHARE` エラーの発生を回避できる場合があります。</span><span class="sxs-lookup"><span data-stu-id="0c884-118">This can avoid some instances in which profiler metadata modifications cause an `SECURITY_E_INCOMPATIBLE_SHARE` error.</span></span>  
  
 <span data-ttu-id="0c884-119">プロファイラーを使用して、 [ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) CLR アセンブリ参照クロージャのウォーカーへのアセンブリ参照を追加するには、このメソッドが提供するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="0c884-119">The profiler uses the [ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) object provided by this method to add assembly references to the CLR assembly reference closure walker.</span></span>  <span data-ttu-id="0c884-120">[ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md)オブジェクトは、このコールバック内からのみ使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c884-120">The [ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) object should be used only from within this callback.</span></span> <span data-ttu-id="0c884-121">呼び出し、 [icorprofilerassemblyreferenceprovider::addassemblyreference](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md)後のアセンブリ参照クロージャのウォークのみが変更されたメタデータは、このコールバックからのメソッドが生じません。</span><span class="sxs-lookup"><span data-stu-id="0c884-121">Calls to the [ICorProfilerAssemblyReferenceProvider::AddAssemblyReference](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) method from this callback don't result in modified metadata, but only in a modified assembly reference closure walk.</span></span> <span data-ttu-id="0c884-122">プロファイラーを使用する必要があります、 [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)内から明示的にアセンブリ参照を追加するオブジェクト、 [icorprofilercallback::moduleloadfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)を参照するためのコールバックアセンブリ、実装している場合でも、`GetAssemblyReferences`コールバック。</span><span class="sxs-lookup"><span data-stu-id="0c884-122">The profiler will still have to use an [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) object to explicitly add assembly references from within the [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback for the referencing assembly, even if it implements the `GetAssemblyReferences` callback.</span></span>  
  
 <span data-ttu-id="0c884-123">プロファイラーは、同じアセンブリのこのコールバックに重複する呼び出しを受信することがあり、このような重複する呼び出しごとに同じ応答する必要があります (の同じセットを作成して[ICorProfilerAssemblyReferenceProvider:。AddAssemblyReference](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md)呼び出し)。</span><span class="sxs-lookup"><span data-stu-id="0c884-123">The profiler should be prepared to receive duplicate calls to this callback for the same assembly, and should respond identically for each such duplicate call (by making the same set of [ICorProfilerAssemblyReferenceProvider::AddAssemblyReference](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) calls).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c884-124">必要条件</span><span class="sxs-lookup"><span data-stu-id="0c884-124">Requirements</span></span>  
 <span data-ttu-id="0c884-125">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c884-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c884-126">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0c884-126">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0c884-127">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0c884-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0c884-128">**.NET Framework のバージョン:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c884-128">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c884-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="0c884-129">See also</span></span>

- [<span data-ttu-id="0c884-130">ICorProfilerCallback6 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0c884-130">ICorProfilerCallback6 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-interface.md)
- [<span data-ttu-id="0c884-131">ModuleLoadFinished メソッド</span><span class="sxs-lookup"><span data-stu-id="0c884-131">ModuleLoadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)
- [<span data-ttu-id="0c884-132">COR_PRF_ASSEMBLY_REFERENCE_INFO 構造体</span><span class="sxs-lookup"><span data-stu-id="0c884-132">COR_PRF_ASSEMBLY_REFERENCE_INFO Structure</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-assembly-reference-info-structure.md)
- [<span data-ttu-id="0c884-133">ICorProfilerAssemblyReferenceProvider インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0c884-133">ICorProfilerAssemblyReferenceProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md)
