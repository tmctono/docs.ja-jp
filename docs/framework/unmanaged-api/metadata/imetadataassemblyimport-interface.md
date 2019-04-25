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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 373ff0470e2403f91534df0c0ffe4039dbb0f832
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61905412"
---
# <a name="imetadataassemblyimport-interface"></a><span data-ttu-id="af39d-102">IMetaDataAssemblyImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="af39d-102">IMetaDataAssemblyImport Interface</span></span>
<span data-ttu-id="af39d-103">アセンブリ マニフェストの内容にアクセスして確認するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="af39d-103">Provides methods to access and examine the contents of an assembly manifest.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="af39d-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="af39d-104">Methods</span></span>  
  
|<span data-ttu-id="af39d-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="af39d-105">Method</span></span>|<span data-ttu-id="af39d-106">説明</span><span class="sxs-lookup"><span data-stu-id="af39d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="af39d-107">CloseEnum メソッド</span><span class="sxs-lookup"><span data-stu-id="af39d-107">CloseEnum Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-closeenum-method.md)|<span data-ttu-id="af39d-108">指定された列挙子を識別するハンドルを解放します。</span><span class="sxs-lookup"><span data-stu-id="af39d-108">Releases the handle to the specified enumerator.</span></span>|  
|[<span data-ttu-id="af39d-109">EnumAssemblyRefs メソッド</span><span class="sxs-lookup"><span data-stu-id="af39d-109">EnumAssemblyRefs Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumassemblyrefs-method.md)|<span data-ttu-id="af39d-110">含む列挙子へのインターフェイス ポインターを取得、`mdAssemblyRef`の現在のメタデータ スコープ内のアセンブリによって参照されるアセンブリのトークン。</span><span class="sxs-lookup"><span data-stu-id="af39d-110">Gets an interface pointer to an enumerator that contains the `mdAssemblyRef` tokens of the assemblies referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="af39d-111">EnumExportedTypes メソッド</span><span class="sxs-lookup"><span data-stu-id="af39d-111">EnumExportedTypes Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumexportedtypes-method.md)|<span data-ttu-id="af39d-112">含む列挙子へのインターフェイス ポインターを取得、`mdExportedType`の現在のメタデータ スコープ内のアセンブリによって参照されている COM 型のトークン。</span><span class="sxs-lookup"><span data-stu-id="af39d-112">Gets an interface pointer to an enumerator that contains the `mdExportedType` tokens of the COM types referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="af39d-113">EnumFiles メソッド</span><span class="sxs-lookup"><span data-stu-id="af39d-113">EnumFiles Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumfiles-method.md)|<span data-ttu-id="af39d-114">含む列挙子へのインターフェイス ポインターを取得、`mdFile`の現在のメタデータ スコープ内のアセンブリによって参照されるファイルのトークン。</span><span class="sxs-lookup"><span data-stu-id="af39d-114">Gets an interface pointer to an enumerator that contains the `mdFile` tokens of the files referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="af39d-115">EnumManifestResources メソッド</span><span class="sxs-lookup"><span data-stu-id="af39d-115">EnumManifestResources Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enummanifestresources-method.md)|<span data-ttu-id="af39d-116">含む列挙子へのインターフェイス ポインターを取得、`mdManifestResource`の現在のメタデータ スコープ内のアセンブリによって参照されているリソースのトークン。</span><span class="sxs-lookup"><span data-stu-id="af39d-116">Gets an interface pointer to an enumerator that contains the `mdManifestResource` tokens of the resources referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="af39d-117">FindAssembliesByName メソッド</span><span class="sxs-lookup"><span data-stu-id="af39d-117">FindAssembliesByName Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findassembliesbyname-method.md)|<span data-ttu-id="af39d-118">配列を取得します`mdAssemblyRef`トークンを指定した名前のアセンブリ。</span><span class="sxs-lookup"><span data-stu-id="af39d-118">Gets an array of `mdAssemblyRef` tokens for the assemblies with the specified name.</span></span>|  
|[<span data-ttu-id="af39d-119">FindExportedTypeByName メソッド</span><span class="sxs-lookup"><span data-stu-id="af39d-119">FindExportedTypeByName Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findexportedtypebyname-method.md)|<span data-ttu-id="af39d-120">取得、`mdExportedType`指定した名前の COM 型のトークン。</span><span class="sxs-lookup"><span data-stu-id="af39d-120">Gets an `mdExportedType` token for the COM type with the specified name.</span></span>|  
|[<span data-ttu-id="af39d-121">FindManifestResourceByName メソッド</span><span class="sxs-lookup"><span data-stu-id="af39d-121">FindManifestResourceByName Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findmanifestresourcebyname-method.md)|<span data-ttu-id="af39d-122">取得、`mdManifestResource`指定した名前のリソースのトークン。</span><span class="sxs-lookup"><span data-stu-id="af39d-122">Gets an `mdManifestResource` token for the resource with the specified name.</span></span>|  
|[<span data-ttu-id="af39d-123">GetAssemblyFromScope メソッド</span><span class="sxs-lookup"><span data-stu-id="af39d-123">GetAssemblyFromScope Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyfromscope-method.md)|<span data-ttu-id="af39d-124">現在のメタデータ スコープ内のアセンブリのトークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="af39d-124">Gets the token for the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="af39d-125">GetAssemblyProps メソッド</span><span class="sxs-lookup"><span data-stu-id="af39d-125">GetAssemblyProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyprops-method.md)|<span data-ttu-id="af39d-126">指定したアセンブリのプロパティの設定を取得します。</span><span class="sxs-lookup"><span data-stu-id="af39d-126">Gets the property settings of the specified assembly.</span></span>|  
|[<span data-ttu-id="af39d-127">GetAssemblyRefProps メソッド</span><span class="sxs-lookup"><span data-stu-id="af39d-127">GetAssemblyRefProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyrefprops-method.md)|<span data-ttu-id="af39d-128">指定したプロパティ設定を取得`mdAssemblyRef`トークンです。</span><span class="sxs-lookup"><span data-stu-id="af39d-128">Gets the property settings of the specified `mdAssemblyRef` token.</span></span>|  
|[<span data-ttu-id="af39d-129">GetExportedTypeProps メソッド</span><span class="sxs-lookup"><span data-stu-id="af39d-129">GetExportedTypeProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getexportedtypeprops-method.md)|<span data-ttu-id="af39d-130">指定した COM 型のプロパティの設定を取得します。</span><span class="sxs-lookup"><span data-stu-id="af39d-130">Gets the property settings of the specified COM type.</span></span>|  
|[<span data-ttu-id="af39d-131">GetFileProps メソッド</span><span class="sxs-lookup"><span data-stu-id="af39d-131">GetFileProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getfileprops-method.md)|<span data-ttu-id="af39d-132">指定したファイルのプロパティの設定を取得します。</span><span class="sxs-lookup"><span data-stu-id="af39d-132">Gets the property settings of the specified file.</span></span>|  
|[<span data-ttu-id="af39d-133">GetManifestResourceProps メソッド</span><span class="sxs-lookup"><span data-stu-id="af39d-133">GetManifestResourceProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getmanifestresourceprops-method.md)|<span data-ttu-id="af39d-134">指定されたマニフェスト リソースのプロパティの設定を取得します。</span><span class="sxs-lookup"><span data-stu-id="af39d-134">Gets the property settings of the specified manifest resource.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="af39d-135">必要条件</span><span class="sxs-lookup"><span data-stu-id="af39d-135">Requirements</span></span>  
 <span data-ttu-id="af39d-136">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="af39d-136">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af39d-137">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="af39d-137">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="af39d-138">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="af39d-138">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="af39d-139">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af39d-139">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af39d-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="af39d-140">See also</span></span>

- [<span data-ttu-id="af39d-141">メタデータ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="af39d-141">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [<span data-ttu-id="af39d-142">IMetaDataAssemblyEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="af39d-142">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
