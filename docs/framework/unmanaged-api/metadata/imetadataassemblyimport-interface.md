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
# <a name="imetadataassemblyimport-interface"></a><span data-ttu-id="da1fb-102">IMetaDataAssemblyImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="da1fb-102">IMetaDataAssemblyImport Interface</span></span>
<span data-ttu-id="da1fb-103">アセンブリ マニフェストの内容にアクセスして確認するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="da1fb-103">Provides methods to access and examine the contents of an assembly manifest.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="da1fb-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="da1fb-104">Methods</span></span>  
  
|<span data-ttu-id="da1fb-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="da1fb-105">Method</span></span>|<span data-ttu-id="da1fb-106">説明</span><span class="sxs-lookup"><span data-stu-id="da1fb-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="da1fb-107">CloseEnum メソッド</span><span class="sxs-lookup"><span data-stu-id="da1fb-107">CloseEnum Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-closeenum-method.md)|<span data-ttu-id="da1fb-108">指定した列挙子へのハンドルを解放します。</span><span class="sxs-lookup"><span data-stu-id="da1fb-108">Releases the handle to the specified enumerator.</span></span>|  
|[<span data-ttu-id="da1fb-109">EnumAssemblyRefs メソッド</span><span class="sxs-lookup"><span data-stu-id="da1fb-109">EnumAssemblyRefs Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumassemblyrefs-method.md)|<span data-ttu-id="da1fb-110">現在のメタデータスコープ内のアセンブリによって参照されるアセンブリの `mdAssemblyRef` トークンを格納している列挙子へのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="da1fb-110">Gets an interface pointer to an enumerator that contains the `mdAssemblyRef` tokens of the assemblies referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="da1fb-111">EnumExportedTypes メソッド</span><span class="sxs-lookup"><span data-stu-id="da1fb-111">EnumExportedTypes Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumexportedtypes-method.md)|<span data-ttu-id="da1fb-112">現在のメタデータスコープ内のアセンブリによって参照される COM 型の `mdExportedType` トークンを格納している列挙子へのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="da1fb-112">Gets an interface pointer to an enumerator that contains the `mdExportedType` tokens of the COM types referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="da1fb-113">EnumFiles メソッド</span><span class="sxs-lookup"><span data-stu-id="da1fb-113">EnumFiles Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumfiles-method.md)|<span data-ttu-id="da1fb-114">現在のメタデータスコープ内のアセンブリによって参照されるファイルの `mdFile` トークンを格納している列挙子へのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="da1fb-114">Gets an interface pointer to an enumerator that contains the `mdFile` tokens of the files referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="da1fb-115">EnumManifestResources メソッド</span><span class="sxs-lookup"><span data-stu-id="da1fb-115">EnumManifestResources Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enummanifestresources-method.md)|<span data-ttu-id="da1fb-116">現在のメタデータスコープ内のアセンブリによって参照されるリソースの `mdManifestResource` トークンを格納している列挙子へのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="da1fb-116">Gets an interface pointer to an enumerator that contains the `mdManifestResource` tokens of the resources referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="da1fb-117">FindAssembliesByName メソッド</span><span class="sxs-lookup"><span data-stu-id="da1fb-117">FindAssembliesByName Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findassembliesbyname-method.md)|<span data-ttu-id="da1fb-118">指定した名前のアセンブリの `mdAssemblyRef` トークンの配列を取得します。</span><span class="sxs-lookup"><span data-stu-id="da1fb-118">Gets an array of `mdAssemblyRef` tokens for the assemblies with the specified name.</span></span>|  
|[<span data-ttu-id="da1fb-119">FindExportedTypeByName メソッド</span><span class="sxs-lookup"><span data-stu-id="da1fb-119">FindExportedTypeByName Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findexportedtypebyname-method.md)|<span data-ttu-id="da1fb-120">指定した名前を持つ COM 型の `mdExportedType` トークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="da1fb-120">Gets an `mdExportedType` token for the COM type with the specified name.</span></span>|  
|[<span data-ttu-id="da1fb-121">FindManifestResourceByName メソッド</span><span class="sxs-lookup"><span data-stu-id="da1fb-121">FindManifestResourceByName Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findmanifestresourcebyname-method.md)|<span data-ttu-id="da1fb-122">指定した名前のリソースの `mdManifestResource` トークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="da1fb-122">Gets an `mdManifestResource` token for the resource with the specified name.</span></span>|  
|[<span data-ttu-id="da1fb-123">GetAssemblyFromScope メソッド</span><span class="sxs-lookup"><span data-stu-id="da1fb-123">GetAssemblyFromScope Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyfromscope-method.md)|<span data-ttu-id="da1fb-124">現在のメタデータスコープ内のアセンブリのトークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="da1fb-124">Gets the token for the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="da1fb-125">GetAssemblyProps メソッド</span><span class="sxs-lookup"><span data-stu-id="da1fb-125">GetAssemblyProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyprops-method.md)|<span data-ttu-id="da1fb-126">指定したアセンブリのプロパティ設定を取得します。</span><span class="sxs-lookup"><span data-stu-id="da1fb-126">Gets the property settings of the specified assembly.</span></span>|  
|[<span data-ttu-id="da1fb-127">GetAssemblyRefProps メソッド</span><span class="sxs-lookup"><span data-stu-id="da1fb-127">GetAssemblyRefProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyrefprops-method.md)|<span data-ttu-id="da1fb-128">指定された `mdAssemblyRef` トークンのプロパティ設定を取得します。</span><span class="sxs-lookup"><span data-stu-id="da1fb-128">Gets the property settings of the specified `mdAssemblyRef` token.</span></span>|  
|[<span data-ttu-id="da1fb-129">GetExportedTypeProps メソッド</span><span class="sxs-lookup"><span data-stu-id="da1fb-129">GetExportedTypeProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getexportedtypeprops-method.md)|<span data-ttu-id="da1fb-130">指定した COM 型のプロパティ設定を取得します。</span><span class="sxs-lookup"><span data-stu-id="da1fb-130">Gets the property settings of the specified COM type.</span></span>|  
|[<span data-ttu-id="da1fb-131">GetFileProps メソッド</span><span class="sxs-lookup"><span data-stu-id="da1fb-131">GetFileProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getfileprops-method.md)|<span data-ttu-id="da1fb-132">指定されたファイルのプロパティ設定を取得します。</span><span class="sxs-lookup"><span data-stu-id="da1fb-132">Gets the property settings of the specified file.</span></span>|  
|[<span data-ttu-id="da1fb-133">GetManifestResourceProps メソッド</span><span class="sxs-lookup"><span data-stu-id="da1fb-133">GetManifestResourceProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getmanifestresourceprops-method.md)|<span data-ttu-id="da1fb-134">指定されたマニフェストリソースのプロパティ設定を取得します。</span><span class="sxs-lookup"><span data-stu-id="da1fb-134">Gets the property settings of the specified manifest resource.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="da1fb-135">要件</span><span class="sxs-lookup"><span data-stu-id="da1fb-135">Requirements</span></span>  
 <span data-ttu-id="da1fb-136">**プラットフォーム:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="da1fb-136">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da1fb-137">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="da1fb-137">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="da1fb-138">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="da1fb-138">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="da1fb-139">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da1fb-139">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da1fb-140">参照</span><span class="sxs-lookup"><span data-stu-id="da1fb-140">See also</span></span>

- [<span data-ttu-id="da1fb-141">メタデータ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="da1fb-141">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [<span data-ttu-id="da1fb-142">IMetaDataAssemblyEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="da1fb-142">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
