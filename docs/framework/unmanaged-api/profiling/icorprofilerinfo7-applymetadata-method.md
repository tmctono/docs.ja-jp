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
ms.openlocfilehash: c30206145d08a22af49c4a6a0dc83fd7382bcc06
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84495509"
---
# <a name="icorprofilerinfo7applymetadata-method"></a><span data-ttu-id="a438e-102">ICorProfilerInfo7:: ApplyMetaData メソッド</span><span class="sxs-lookup"><span data-stu-id="a438e-102">ICorProfilerInfo7::ApplyMetaData Method</span></span>
<span data-ttu-id="a438e-103">[.NET Framework 4.6.1 以降のバージョンでのみでサポート]</span><span class="sxs-lookup"><span data-stu-id="a438e-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="a438e-104">メソッドによって新たに定義されたメタデータ `IMetadataEmit::Define*` を、指定したモジュールに適用します。</span><span class="sxs-lookup"><span data-stu-id="a438e-104">Applies the metadata newly defined by the `IMetadataEmit::Define*` methods to a specified module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a438e-105">構文</span><span class="sxs-lookup"><span data-stu-id="a438e-105">Syntax</span></span>  
  
```cpp
HRESULT ApplyMetaData(  
        [in] ModuleID moduleID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a438e-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a438e-106">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="a438e-107">からメタデータが変更されたモジュールの識別子。</span><span class="sxs-lookup"><span data-stu-id="a438e-107">[in] The identifier of the module whose metadata was changed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a438e-108">解説</span><span class="sxs-lookup"><span data-stu-id="a438e-108">Remarks</span></span>  
 <span data-ttu-id="a438e-109">[Moduleloadfinished](icorprofilercallback-moduleloadfinished-method.md)コールバックの後にメタデータの変更が行われた場合は、新しいメタデータを使用する前にこのメソッドを呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="a438e-109">If metadata changes are made after the [ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) callback, you must call this method before using the new metadata.</span></span>  
  
 <span data-ttu-id="a438e-110">`ApplyMetaData`では、次の種類のメタデータの追加のみがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="a438e-110">`ApplyMetaData` only supports adding the following types of metadata:</span></span>  
  
- <span data-ttu-id="a438e-111">`AssemblyRef`[IMetaDataAssemblyEmit::D efineAssemblyRef](../metadata/imetadataassemblyemit-defineassemblyref-method.md)を呼び出すことによって作成するレコード。</span><span class="sxs-lookup"><span data-stu-id="a438e-111">`AssemblyRef` records, which you create by calling the [IMetaDataAssemblyEmit::DefineAssemblyRef](../metadata/imetadataassemblyemit-defineassemblyref-method.md).</span></span> <span data-ttu-id="a438e-112">メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="a438e-112">method.</span></span>  
  
- <span data-ttu-id="a438e-113">`TypeRef`[IMetaDataEmit::D efinetyperefbyname](../metadata/imetadataemit-definetyperefbyname-method.md)メソッドを呼び出すことによって作成するレコード。</span><span class="sxs-lookup"><span data-stu-id="a438e-113">`TypeRef` records, which you create by calling the [IMetaDataEmit::DefineTypeRefByName](../metadata/imetadataemit-definetyperefbyname-method.md) method.</span></span>  
  
- <span data-ttu-id="a438e-114">`TypeSpec`レコード。 [IMetaDataEmit:: GetTokenFromTypeSpec](../metadata/imetadataemit-gettokenfromtypespec-method.md)メソッドを呼び出すことによって作成します。</span><span class="sxs-lookup"><span data-stu-id="a438e-114">`TypeSpec` records, which you create by calling the [IMetaDataEmit::GetTokenFromTypeSpec](../metadata/imetadataemit-gettokenfromtypespec-method.md) method.</span></span>  
  
- <span data-ttu-id="a438e-115">`MemberRef`[IMetaDataEmit::D efinememberref](../metadata/imetadataemit-definememberref-method.md)メソッドを呼び出すことによって作成するレコード。</span><span class="sxs-lookup"><span data-stu-id="a438e-115">`MemberRef` records, which you create by calling the [IMetaDataEmit::DefineMemberRef](../metadata/imetadataemit-definememberref-method.md) method.</span></span>  
  
- <span data-ttu-id="a438e-116">`MemberSpec`[IMetaDataEmit2::D efinemethodspec](../metadata/imetadataemit2-definemethodspec-method.md)メソッドを呼び出すことによって作成するレコード。</span><span class="sxs-lookup"><span data-stu-id="a438e-116">`MemberSpec` records, which you create by calling the [IMetaDataEmit2::DefineMethodSpec](../metadata/imetadataemit2-definemethodspec-method.md) method.</span></span>  
  
- <span data-ttu-id="a438e-117">`UserString`レコード。 [IMetaDataEmit::D efineUserString](../metadata/imetadataemit-defineuserstring-method.md)メソッドを呼び出すことによって作成します。</span><span class="sxs-lookup"><span data-stu-id="a438e-117">`UserString` records, which you create by calling the [IMetaDataEmit::DefineUserString](../metadata/imetadataemit-defineuserstring-method.md) method.</span></span>  

<span data-ttu-id="a438e-118">.NET Core 3.0 以降では、 `ApplyMetaData` 次の型もサポートしています。</span><span class="sxs-lookup"><span data-stu-id="a438e-118">Starting with .NET Core 3.0, `ApplyMetaData` also supports the following types:</span></span>

- <span data-ttu-id="a438e-119">`TypeDef`[IMetaDataEmit::D efineTypeDef](../metadata/imetadataemit-definetypedef-method.md)メソッドを呼び出すことによって作成するレコード。</span><span class="sxs-lookup"><span data-stu-id="a438e-119">`TypeDef` records, which you create by calling the [IMetaDataEmit::DefineTypeDef](../metadata/imetadataemit-definetypedef-method.md) method.</span></span>

- <span data-ttu-id="a438e-120">`MethodDef`[IMetaDataEmit::D efinemethod](../metadata/imetadataemit-definemethod-method.md)メソッドを呼び出すことによって作成するレコード。</span><span class="sxs-lookup"><span data-stu-id="a438e-120">`MethodDef` records, which you create by calling the [IMetaDataEmit::DefineMethod](../metadata/imetadataemit-definemethod-method.md) method.</span></span> <span data-ttu-id="a438e-121">ただし、既存の型に仮想メソッドを追加することはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="a438e-121">However, adding virtual methods to an existing type is not supported.</span></span> <span data-ttu-id="a438e-122">仮想メソッドは、 [Moduleloadfinished](icorprofilercallback-moduleloadfinished-method.md)コールバックの前に追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a438e-122">Virtual methods must be added before the [ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>

## <a name="requirements"></a><span data-ttu-id="a438e-123">要件</span><span class="sxs-lookup"><span data-stu-id="a438e-123">Requirements</span></span>  
 <span data-ttu-id="a438e-124">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a438e-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a438e-125">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a438e-125">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a438e-126">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a438e-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a438e-127">**.NET Framework のバージョン:**[!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a438e-127">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a438e-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="a438e-128">See also</span></span>

- [<span data-ttu-id="a438e-129">ICorProfilerInfo7 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a438e-129">ICorProfilerInfo7 Interface</span></span>](icorprofilerinfo7-interface.md)
