---
title: IMetaDataAssemblyEmit インターフェイス
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit
helpviewer_keywords:
- IMetaDataAssemblyEmit interface [.NET Framework metadata]
ms.assetid: 34fb03cc-2285-4a45-ac48-ad993b7a921a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3a66ef090a205019493e099919739867e3936873
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61905230"
---
# <a name="imetadataassemblyemit-interface"></a><span data-ttu-id="b9a5a-102">IMetaDataAssemblyEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b9a5a-102">IMetaDataAssemblyEmit Interface</span></span>
<span data-ttu-id="b9a5a-103">共通言語ランタイムがリソースの解決および消費に使用する自己記述モデルをサポートするメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-103">Provides methods that support the self-description model used by the common language runtime to resolve and consume resources.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b9a5a-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="b9a5a-104">Methods</span></span>  
  
|<span data-ttu-id="b9a5a-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="b9a5a-105">Method</span></span>|<span data-ttu-id="b9a5a-106">説明</span><span class="sxs-lookup"><span data-stu-id="b9a5a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b9a5a-107">DefineAssembly メソッド</span><span class="sxs-lookup"><span data-stu-id="b9a5a-107">DefineAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassembly-method.md)|<span data-ttu-id="b9a5a-108">指定したアセンブリのメタデータを含むアセンブリ データ構造体を作成し、関連付けられたメタデータ トークンを返します。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-108">Creates an assembly data structure containing metadata for the specified assembly, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="b9a5a-109">DefineAssemblyRef メソッド</span><span class="sxs-lookup"><span data-stu-id="b9a5a-109">DefineAssemblyRef Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md)|<span data-ttu-id="b9a5a-110">このアセンブリが参照するアセンブリのメタデータを含む `AssemblyRef` 構造体を作成し、関連付けられたメタデータ トークンを返します。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-110">Creates an `AssemblyRef` structure containing metadata for the assembly that this assembly references, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="b9a5a-111">DefineExportedType メソッド</span><span class="sxs-lookup"><span data-stu-id="b9a5a-111">DefineExportedType Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md)|<span data-ttu-id="b9a5a-112">指定してエクスポートした型のメタデータが含まれる `ExportedType` 構造体を作成し、関連付けられたメタデータ トークンを返します。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-112">Creates an `ExportedType` structure containing metadata for the specified exported type, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="b9a5a-113">DefineFile メソッド</span><span class="sxs-lookup"><span data-stu-id="b9a5a-113">DefineFile Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md)|<span data-ttu-id="b9a5a-114">このアセンブリが参照するアセンブリのメタデータを含む `File` メタデータ構造体を作成し、関連付けられたメタデータ トークンを返します。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-114">Creates a `File` metadata structure containing metadata for assembly referenced by this assembly, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="b9a5a-115">DefineManifestResource メソッド</span><span class="sxs-lookup"><span data-stu-id="b9a5a-115">DefineManifestResource Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md)|<span data-ttu-id="b9a5a-116">指定したマニフェスト リソースのメタデータを含む `ManifestResource` 構造体を作成し、関連付けられたメタデータ トークンを返します。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-116">Creates a `ManifestResource` structure containing metadata for the specified manifest resource, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="b9a5a-117">SetAssemblyProps メソッド</span><span class="sxs-lookup"><span data-stu-id="b9a5a-117">SetAssemblyProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-setassemblyprops-method.md)|<span data-ttu-id="b9a5a-118">指定された `Assembly` メタデータ構造体を変更します。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-118">Modifies the specified `Assembly` metadata structure.</span></span>|  
|[<span data-ttu-id="b9a5a-119">SetAssemblyRefProps メソッド</span><span class="sxs-lookup"><span data-stu-id="b9a5a-119">SetAssemblyRefProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-setassemblyrefprops-method.md)|<span data-ttu-id="b9a5a-120">指定された `AssemblyRef` メタデータ構造体を変更します。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-120">Modifies the specified `AssemblyRef` metadata structure.</span></span>|  
|[<span data-ttu-id="b9a5a-121">SetExportedTypeProps メソッド</span><span class="sxs-lookup"><span data-stu-id="b9a5a-121">SetExportedTypeProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-setexportedtypeprops-method.md)|<span data-ttu-id="b9a5a-122">指定された `ExportedType` メタデータ構造体を変更します。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-122">Modifies the specified `ExportedType` metadata structure.</span></span>|  
|[<span data-ttu-id="b9a5a-123">SetFileProps メソッド</span><span class="sxs-lookup"><span data-stu-id="b9a5a-123">SetFileProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-setfileprops-method.md)|<span data-ttu-id="b9a5a-124">指定された `File` メタデータ構造体を変更します。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-124">Modifies the specified `File` metadata structure.</span></span>|  
|[<span data-ttu-id="b9a5a-125">SetManifestResourceProps メソッド</span><span class="sxs-lookup"><span data-stu-id="b9a5a-125">SetManifestResourceProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-setmanifestresourceprops-method.md)|<span data-ttu-id="b9a5a-126">指定された `ManifestResource` メタデータ構造体を変更します。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-126">Modifies the specified `ManifestResource` metadata structure.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b9a5a-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="b9a5a-127">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9a5a-128">必要条件</span><span class="sxs-lookup"><span data-stu-id="b9a5a-128">Requirements</span></span>  
 <span data-ttu-id="b9a5a-129">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9a5a-130">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b9a5a-130">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b9a5a-131">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="b9a5a-131">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b9a5a-132">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9a5a-132">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9a5a-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="b9a5a-133">See also</span></span>

- [<span data-ttu-id="b9a5a-134">メタデータ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b9a5a-134">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [<span data-ttu-id="b9a5a-135">IMetaDataAssemblyImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b9a5a-135">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
