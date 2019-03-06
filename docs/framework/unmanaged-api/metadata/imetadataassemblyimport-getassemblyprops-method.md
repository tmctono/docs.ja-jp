---
title: IMetaDataAssemblyImport::GetAssemblyProps メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetAssemblyProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetAssemblyProps
helpviewer_keywords:
- GetAssemblyProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetAssemblyProps method [.NET Framework metadata]
ms.assetid: 0eaa4aa9-9441-444a-920c-e4b2a2db899e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 74295b14e9c774aa8a61d9c2726a39a4e3f5f8cc
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57477713"
---
# <a name="imetadataassemblyimportgetassemblyprops-method"></a><span data-ttu-id="4ea18-102">IMetaDataAssemblyImport::GetAssemblyProps メソッド</span><span class="sxs-lookup"><span data-stu-id="4ea18-102">IMetaDataAssemblyImport::GetAssemblyProps Method</span></span>
<span data-ttu-id="4ea18-103">指定したメタデータ シグネチャを持つアセンブリの一連のプロパティを取得します。</span><span class="sxs-lookup"><span data-stu-id="4ea18-103">Gets the set of properties for the assembly with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ea18-104">構文</span><span class="sxs-lookup"><span data-stu-id="4ea18-104">Syntax</span></span>  
  
```  
HRESULT GetAssemblyProps (  
    [in]  mdAssembly          mda,  
    [out] const void          **ppbPublicKey,   
    [out] ULONG               *pcbPublicKey,  
    [out] ULONG               *pulHashAlgId,  
    [out] LPWSTR              szName,  
    [in] ULONG                cchName,  
    [out] ULONG               *pchName,  
    [out] ASSEMBLYMETADATA    *pMetaData,  
    [out] DWORD               *pdwAssemblyFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4ea18-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4ea18-105">Parameters</span></span>  
 `mda`  
 <span data-ttu-id="4ea18-106">[in]。</span><span class="sxs-lookup"><span data-stu-id="4ea18-106">[in].</span></span> <span data-ttu-id="4ea18-107">`mdAssembly`プロパティを取得する対象のアセンブリを表すメタデータ トークン。</span><span class="sxs-lookup"><span data-stu-id="4ea18-107">The `mdAssembly` metadata token that represents the assembly for which to get the properties.</span></span>  
  
 `ppbPublicKey`  
 <span data-ttu-id="4ea18-108">[out]公開キーまたはメタデータ トークンへのポインター。</span><span class="sxs-lookup"><span data-stu-id="4ea18-108">[out] A pointer to the public key or the metadata token.</span></span>  
  
 `pcbPublicKey`  
 <span data-ttu-id="4ea18-109">[out]返される公開キーのバイト数。</span><span class="sxs-lookup"><span data-stu-id="4ea18-109">[out] The number of bytes in the returned public key.</span></span>  
  
 `pulHashAlgId`  
 <span data-ttu-id="4ea18-110">[out]アセンブリ内のファイルのハッシュに使用されるアルゴリズムへのポインター。</span><span class="sxs-lookup"><span data-stu-id="4ea18-110">[out] A pointer to the algorithm used to hash the files in the assembly.</span></span>  
  
 `szName`  
 <span data-ttu-id="4ea18-111">[out]アセンブリの簡易名。</span><span class="sxs-lookup"><span data-stu-id="4ea18-111">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="4ea18-112">[in]ワイド文字単位のサイズの`szName`します。</span><span class="sxs-lookup"><span data-stu-id="4ea18-112">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="4ea18-113">[out]実際に返されるワイド文字数`szName`します。</span><span class="sxs-lookup"><span data-stu-id="4ea18-113">[out] The number of wide chars actually returned in `szName`.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="4ea18-114">[out]アセンブリのメタデータを含む ASSEMBLYMETADATA 構造体へのポインター。</span><span class="sxs-lookup"><span data-stu-id="4ea18-114">[out] A pointer to an ASSEMBLYMETADATA structure that contains the assembly metadata.</span></span>  
  
 `pdwAssemblyFlags`  
 <span data-ttu-id="4ea18-115">[out]アセンブリに適用されるメタデータを記述するフラグ。</span><span class="sxs-lookup"><span data-stu-id="4ea18-115">[out] Flags that describe the metadata applied to an assembly.</span></span> <span data-ttu-id="4ea18-116">この値は、1 つ以上の組み合わせ[CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md)値。</span><span class="sxs-lookup"><span data-stu-id="4ea18-116">This value is a combination of one or more [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ea18-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="4ea18-117">Requirements</span></span>  
 <span data-ttu-id="4ea18-118">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ea18-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ea18-119">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="4ea18-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4ea18-120">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="4ea18-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4ea18-121">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4ea18-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ea18-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="4ea18-122">See also</span></span>
- [<span data-ttu-id="4ea18-123">IMetaDataAssemblyImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4ea18-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
