---
title: IMetaDataAssemblyImport インターフェイス
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport
helpviewer_keywords:
- IMetaDataAssemblyImport interface [.NET Framework metadata]
ms.assetid: 29c6fba5-4cea-417d-b484-7ed22ebff1c9
topic_type:
- apiref
ms.openlocfilehash: 289e26868ff2eb9e1d97cf084e9a888815062ea4
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436306"
---
# <a name="imetadataassemblyimport-interface"></a><span data-ttu-id="876c2-102">IMetaDataAssemblyImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="876c2-102">IMetaDataAssemblyImport Interface</span></span>
<span data-ttu-id="876c2-103">アセンブリ マニフェストの内容にアクセスして確認するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="876c2-103">Provides methods to access and examine the contents of an assembly manifest.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="876c2-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="876c2-104">Methods</span></span>  
  
|<span data-ttu-id="876c2-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="876c2-105">Method</span></span>|<span data-ttu-id="876c2-106">説明</span><span class="sxs-lookup"><span data-stu-id="876c2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="876c2-107">CloseEnum メソッド</span><span class="sxs-lookup"><span data-stu-id="876c2-107">CloseEnum Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-closeenum-method.md)|<span data-ttu-id="876c2-108">Releases the handle to the specified enumerator.</span><span class="sxs-lookup"><span data-stu-id="876c2-108">Releases the handle to the specified enumerator.</span></span>|  
|[<span data-ttu-id="876c2-109">EnumAssemblyRefs メソッド</span><span class="sxs-lookup"><span data-stu-id="876c2-109">EnumAssemblyRefs Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumassemblyrefs-method.md)|<span data-ttu-id="876c2-110">Gets an interface pointer to an enumerator that contains the `mdAssemblyRef` tokens of the assemblies referenced by the assembly in the current metadata scope.</span><span class="sxs-lookup"><span data-stu-id="876c2-110">Gets an interface pointer to an enumerator that contains the `mdAssemblyRef` tokens of the assemblies referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="876c2-111">EnumExportedTypes メソッド</span><span class="sxs-lookup"><span data-stu-id="876c2-111">EnumExportedTypes Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumexportedtypes-method.md)|<span data-ttu-id="876c2-112">Gets an interface pointer to an enumerator that contains the `mdExportedType` tokens of the COM types referenced by the assembly in the current metadata scope.</span><span class="sxs-lookup"><span data-stu-id="876c2-112">Gets an interface pointer to an enumerator that contains the `mdExportedType` tokens of the COM types referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="876c2-113">EnumFiles メソッド</span><span class="sxs-lookup"><span data-stu-id="876c2-113">EnumFiles Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumfiles-method.md)|<span data-ttu-id="876c2-114">Gets an interface pointer to an enumerator that contains the `mdFile` tokens of the files referenced by the assembly in the current metadata scope.</span><span class="sxs-lookup"><span data-stu-id="876c2-114">Gets an interface pointer to an enumerator that contains the `mdFile` tokens of the files referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="876c2-115">EnumManifestResources メソッド</span><span class="sxs-lookup"><span data-stu-id="876c2-115">EnumManifestResources Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enummanifestresources-method.md)|<span data-ttu-id="876c2-116">Gets an interface pointer to an enumerator that contains the `mdManifestResource` tokens of the resources referenced by the assembly in the current metadata scope.</span><span class="sxs-lookup"><span data-stu-id="876c2-116">Gets an interface pointer to an enumerator that contains the `mdManifestResource` tokens of the resources referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="876c2-117">FindAssembliesByName メソッド</span><span class="sxs-lookup"><span data-stu-id="876c2-117">FindAssembliesByName Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findassembliesbyname-method.md)|<span data-ttu-id="876c2-118">Gets an array of `mdAssemblyRef` tokens for the assemblies with the specified name.</span><span class="sxs-lookup"><span data-stu-id="876c2-118">Gets an array of `mdAssemblyRef` tokens for the assemblies with the specified name.</span></span>|  
|[<span data-ttu-id="876c2-119">FindExportedTypeByName メソッド</span><span class="sxs-lookup"><span data-stu-id="876c2-119">FindExportedTypeByName Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findexportedtypebyname-method.md)|<span data-ttu-id="876c2-120">Gets an `mdExportedType` token for the COM type with the specified name.</span><span class="sxs-lookup"><span data-stu-id="876c2-120">Gets an `mdExportedType` token for the COM type with the specified name.</span></span>|  
|[<span data-ttu-id="876c2-121">FindManifestResourceByName メソッド</span><span class="sxs-lookup"><span data-stu-id="876c2-121">FindManifestResourceByName Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findmanifestresourcebyname-method.md)|<span data-ttu-id="876c2-122">Gets an `mdManifestResource` token for the resource with the specified name.</span><span class="sxs-lookup"><span data-stu-id="876c2-122">Gets an `mdManifestResource` token for the resource with the specified name.</span></span>|  
|[<span data-ttu-id="876c2-123">GetAssemblyFromScope メソッド</span><span class="sxs-lookup"><span data-stu-id="876c2-123">GetAssemblyFromScope Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyfromscope-method.md)|<span data-ttu-id="876c2-124">Gets the token for the assembly in the current metadata scope.</span><span class="sxs-lookup"><span data-stu-id="876c2-124">Gets the token for the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="876c2-125">GetAssemblyProps メソッド</span><span class="sxs-lookup"><span data-stu-id="876c2-125">GetAssemblyProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyprops-method.md)|<span data-ttu-id="876c2-126">Gets the property settings of the specified assembly.</span><span class="sxs-lookup"><span data-stu-id="876c2-126">Gets the property settings of the specified assembly.</span></span>|  
|[<span data-ttu-id="876c2-127">GetAssemblyRefProps メソッド</span><span class="sxs-lookup"><span data-stu-id="876c2-127">GetAssemblyRefProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyrefprops-method.md)|<span data-ttu-id="876c2-128">Gets the property settings of the specified `mdAssemblyRef` token.</span><span class="sxs-lookup"><span data-stu-id="876c2-128">Gets the property settings of the specified `mdAssemblyRef` token.</span></span>|  
|[<span data-ttu-id="876c2-129">GetExportedTypeProps メソッド</span><span class="sxs-lookup"><span data-stu-id="876c2-129">GetExportedTypeProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getexportedtypeprops-method.md)|<span data-ttu-id="876c2-130">Gets the property settings of the specified COM type.</span><span class="sxs-lookup"><span data-stu-id="876c2-130">Gets the property settings of the specified COM type.</span></span>|  
|[<span data-ttu-id="876c2-131">GetFileProps メソッド</span><span class="sxs-lookup"><span data-stu-id="876c2-131">GetFileProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getfileprops-method.md)|<span data-ttu-id="876c2-132">Gets the property settings of the specified file.</span><span class="sxs-lookup"><span data-stu-id="876c2-132">Gets the property settings of the specified file.</span></span>|  
|[<span data-ttu-id="876c2-133">GetManifestResourceProps メソッド</span><span class="sxs-lookup"><span data-stu-id="876c2-133">GetManifestResourceProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getmanifestresourceprops-method.md)|<span data-ttu-id="876c2-134">Gets the property settings of the specified manifest resource.</span><span class="sxs-lookup"><span data-stu-id="876c2-134">Gets the property settings of the specified manifest resource.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="876c2-135">［要件］</span><span class="sxs-lookup"><span data-stu-id="876c2-135">Requirements</span></span>  
 <span data-ttu-id="876c2-136">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="876c2-136">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="876c2-137">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="876c2-137">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="876c2-138">**Library:** Used as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="876c2-138">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="876c2-139">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="876c2-139">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="876c2-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="876c2-140">See also</span></span>

- [<span data-ttu-id="876c2-141">メタデータ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="876c2-141">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [<span data-ttu-id="876c2-142">IMetaDataAssemblyEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="876c2-142">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
