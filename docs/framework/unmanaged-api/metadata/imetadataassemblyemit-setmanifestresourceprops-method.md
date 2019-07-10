---
title: IMetaDataAssemblyEmit::SetManifestResourceProps メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetManifestResourceProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetManifestResourceProps
helpviewer_keywords:
- SetManifestResourceProps method [.NET Framework metadata]
- IMetaDataAssemblyEmit::SetManifestResourceProps method [.NET Framework metadata]
ms.assetid: ef77efd1-849c-4e51-ba92-7ee3d2bf0339
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d080a3077df2cb4ad57ef463b5e02a3a28d8429d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779406"
---
# <a name="imetadataassemblyemitsetmanifestresourceprops-method"></a><span data-ttu-id="8ef93-102">IMetaDataAssemblyEmit::SetManifestResourceProps メソッド</span><span class="sxs-lookup"><span data-stu-id="8ef93-102">IMetaDataAssemblyEmit::SetManifestResourceProps Method</span></span>
<span data-ttu-id="8ef93-103">指定された `ManifestResource` メタデータ構造体を変更します。</span><span class="sxs-lookup"><span data-stu-id="8ef93-103">Modifies the specified `ManifestResource` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ef93-104">構文</span><span class="sxs-lookup"><span data-stu-id="8ef93-104">Syntax</span></span>  
  
```cpp  
HRESULT SetManifestResourceProps (  
    [in] mdManifestResource  mr,  
    [in] mdToken             tkImplementation,   
    [in] DWORD               dwOffset,  
    [in] DWORD               dwResourceFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8ef93-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8ef93-105">Parameters</span></span>  
 `mr`  
 <span data-ttu-id="8ef93-106">[in]トークンを指定する、`ManifestResource`メタデータ構造を変更します。</span><span class="sxs-lookup"><span data-stu-id="8ef93-106">[in] The token that specifies the `ManifestResource` metadata structure to be modified.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="8ef93-107">[in]型のトークン`File`または`AssemblyRef`、リソース プロバイダーにマップされます。</span><span class="sxs-lookup"><span data-stu-id="8ef93-107">[in] The token, of type `File` or `AssemblyRef`, that maps to the resource provider.</span></span>  
  
 `dwOffset`  
 <span data-ttu-id="8ef93-108">[in]リソース ファイル内の先頭までのオフセット。</span><span class="sxs-lookup"><span data-stu-id="8ef93-108">[in] The offset to the beginning of the resource within the file.</span></span>  
  
 `dwResourceFlags`  
 <span data-ttu-id="8ef93-109">[in]リソースの属性を指定するフラグの値のビットごとの組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="8ef93-109">[in] A bitwise combination of flag values that specify the attributes of the resource.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8ef93-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="8ef93-110">Remarks</span></span>  
 <span data-ttu-id="8ef93-111">作成する、`ManifestResource`メタデータ構造体を使用して、 [imetadataassemblyemit::definemanifestresource](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="8ef93-111">To create a `ManifestResource` metadata structure, use the [IMetaDataAssemblyEmit::DefineManifestResource](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8ef93-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="8ef93-112">Requirements</span></span>  
 <span data-ttu-id="8ef93-113">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ef93-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ef93-114">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="8ef93-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8ef93-115">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="8ef93-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8ef93-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8ef93-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ef93-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="8ef93-117">See also</span></span>

- [<span data-ttu-id="8ef93-118">IMetaDataAssemblyEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8ef93-118">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
