---
title: 'ICorProfilerInfo7:: ApplyMetaData メソッド'
ms.date: 02/15/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo7.ApplyMetaData
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: a1bfb649-4584-4d35-b3e6-8fe59b53992a
ms.openlocfilehash: 00d9bef1e2b59a2d2207d1e343380e0e81bee848
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130357"
---
# <a name="icorprofilerinfo7applymetadata-method"></a><span data-ttu-id="2380c-102">ICorProfilerInfo7:: ApplyMetaData メソッド</span><span class="sxs-lookup"><span data-stu-id="2380c-102">ICorProfilerInfo7::ApplyMetaData Method</span></span>
<span data-ttu-id="2380c-103">[.NET Framework 4.6.1 以降のバージョンでのみでサポート]</span><span class="sxs-lookup"><span data-stu-id="2380c-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="2380c-104">`IMetadataEmit::Define*` メソッドによって新たに定義されたメタデータを、指定したモジュールに適用します。</span><span class="sxs-lookup"><span data-stu-id="2380c-104">Applies the metadata newly defined by the `IMetadataEmit::Define*` methods to a specified module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2380c-105">構文</span><span class="sxs-lookup"><span data-stu-id="2380c-105">Syntax</span></span>  
  
```cpp
HRESULT ApplyMetaData(  
        [in] ModuleID moduleID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2380c-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2380c-106">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="2380c-107">からメタデータが変更されたモジュールの識別子。</span><span class="sxs-lookup"><span data-stu-id="2380c-107">[in] The identifier of the module whose metadata was changed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2380c-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="2380c-108">Remarks</span></span>  
 <span data-ttu-id="2380c-109">[Moduleloadfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)コールバックの後にメタデータの変更が行われた場合は、新しいメタデータを使用する前にこのメソッドを呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="2380c-109">If metadata changes are made after the [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback, you must call this method before using the new metadata.</span></span>  
  
 <span data-ttu-id="2380c-110">`ApplyMetaData` は、次の種類のメタデータの追加のみをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="2380c-110">`ApplyMetaData` only supports adding the following types of metadata:</span></span>  
  
- <span data-ttu-id="2380c-111">`AssemblyRef` レコードは、 [IMetaDataAssemblyEmit::D efineAssemblyRef](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md)を呼び出すことによって作成します。</span><span class="sxs-lookup"><span data-stu-id="2380c-111">`AssemblyRef` records, which you create by calling the [IMetaDataAssemblyEmit::DefineAssemblyRef](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md).</span></span> <span data-ttu-id="2380c-112">メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="2380c-112">method.</span></span>  
  
- <span data-ttu-id="2380c-113">`TypeRef` レコードは、 [IMetaDataEmit::D efinetyperefbyname](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md)メソッドを呼び出すことによって作成します。</span><span class="sxs-lookup"><span data-stu-id="2380c-113">`TypeRef` records, which you create by calling the [IMetaDataEmit::DefineTypeRefByName](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) method.</span></span>  
  
- <span data-ttu-id="2380c-114">[IMetaDataEmit:: GetTokenFromTypeSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md)メソッドを呼び出すことによって作成するレコードを `TypeSpec` します。</span><span class="sxs-lookup"><span data-stu-id="2380c-114">`TypeSpec` records, which you create by calling the [IMetaDataEmit::GetTokenFromTypeSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md) method.</span></span>  
  
- <span data-ttu-id="2380c-115">`MemberRef` レコードは、 [IMetaDataEmit::D efinememberref](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md)メソッドを呼び出すことによって作成します。</span><span class="sxs-lookup"><span data-stu-id="2380c-115">`MemberRef` records, which you create by calling the [IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md) method.</span></span>  
  
- <span data-ttu-id="2380c-116">`MemberSpec` レコードは、 [IMetaDataEmit2::D efinemethodspec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definemethodspec-method.md)メソッドを呼び出すことによって作成します。</span><span class="sxs-lookup"><span data-stu-id="2380c-116">`MemberSpec` records, which you create by calling the [IMetaDataEmit2::DefineMethodSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definemethodspec-method.md) method.</span></span>  
  
- <span data-ttu-id="2380c-117">`UserString` レコードは、 [IMetaDataEmit::D efineUserString](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md)メソッドを呼び出すことによって作成します。</span><span class="sxs-lookup"><span data-stu-id="2380c-117">`UserString` records, which you create by calling the [IMetaDataEmit::DefineUserString](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md) method.</span></span>  

<span data-ttu-id="2380c-118">.NET Core 3.0 以降では、`ApplyMetaData` も次の型をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="2380c-118">Starting with .NET Core 3.0, `ApplyMetaData` also supports the following types:</span></span>

- <span data-ttu-id="2380c-119">`TypeDef` レコードは、 [IMetaDataEmit::D efineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md)メソッドを呼び出すことによって作成します。</span><span class="sxs-lookup"><span data-stu-id="2380c-119">`TypeDef` records, which you create by calling the [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md) method.</span></span>

- <span data-ttu-id="2380c-120">`MethodDef` レコードは、 [IMetaDataEmit::D efinemethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md)メソッドを呼び出すことによって作成します。</span><span class="sxs-lookup"><span data-stu-id="2380c-120">`MethodDef` records, which you create by calling the [IMetaDataEmit::DefineMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md) method.</span></span> <span data-ttu-id="2380c-121">ただし、既存の型に仮想メソッドを追加することはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="2380c-121">However, adding virtual methods to an existing type is not supported.</span></span> <span data-ttu-id="2380c-122">仮想メソッドは、 [Moduleloadfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)コールバックの前に追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2380c-122">Virtual methods must be added before the [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>

## <a name="requirements"></a><span data-ttu-id="2380c-123">［要件］</span><span class="sxs-lookup"><span data-stu-id="2380c-123">Requirements</span></span>  
 <span data-ttu-id="2380c-124">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2380c-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2380c-125">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2380c-125">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2380c-126">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2380c-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2380c-127">**.NET Framework のバージョン:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2380c-127">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2380c-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="2380c-128">See also</span></span>

- [<span data-ttu-id="2380c-129">ICorProfilerInfo7 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2380c-129">ICorProfilerInfo7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)
