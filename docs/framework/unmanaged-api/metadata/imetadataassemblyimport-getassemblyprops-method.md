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
ms.openlocfilehash: dfa900e2184a8c415d75f5702c572b14c4018749
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177781"
---
# <a name="imetadataassemblyimportgetassemblyprops-method"></a><span data-ttu-id="cb14e-102">IMetaDataAssemblyImport::GetAssemblyProps メソッド</span><span class="sxs-lookup"><span data-stu-id="cb14e-102">IMetaDataAssemblyImport::GetAssemblyProps Method</span></span>
<span data-ttu-id="cb14e-103">指定したメタデータ シグネチャを持つアセンブリのプロパティのセットを取得します。</span><span class="sxs-lookup"><span data-stu-id="cb14e-103">Gets the set of properties for the assembly with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb14e-104">構文</span><span class="sxs-lookup"><span data-stu-id="cb14e-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="cb14e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="cb14e-105">Parameters</span></span>  
 `mda`  
 <span data-ttu-id="cb14e-106">[in]。</span><span class="sxs-lookup"><span data-stu-id="cb14e-106">[in].</span></span> <span data-ttu-id="cb14e-107">プロパティ`mdAssembly`を取得するアセンブリを表すメタデータ トークン。</span><span class="sxs-lookup"><span data-stu-id="cb14e-107">The `mdAssembly` metadata token that represents the assembly for which to get the properties.</span></span>  
  
 `ppbPublicKey`  
 <span data-ttu-id="cb14e-108">[アウト]公開キーまたはメタデータ トークンへのポインター。</span><span class="sxs-lookup"><span data-stu-id="cb14e-108">[out] A pointer to the public key or the metadata token.</span></span>  
  
 `pcbPublicKey`  
 <span data-ttu-id="cb14e-109">[アウト]返された公開キーのバイト数。</span><span class="sxs-lookup"><span data-stu-id="cb14e-109">[out] The number of bytes in the returned public key.</span></span>  
  
 `pulHashAlgId`  
 <span data-ttu-id="cb14e-110">[アウト]アセンブリ内のファイルをハッシュするために使用されるアルゴリズムへのポインター。</span><span class="sxs-lookup"><span data-stu-id="cb14e-110">[out] A pointer to the algorithm used to hash the files in the assembly.</span></span>  
  
 `szName`  
 <span data-ttu-id="cb14e-111">[アウト]アセンブリの簡易名。</span><span class="sxs-lookup"><span data-stu-id="cb14e-111">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="cb14e-112">[in]のサイズ、ワイド文字で`szName`、 のサイズ。</span><span class="sxs-lookup"><span data-stu-id="cb14e-112">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="cb14e-113">[アウト]で実際に返されたワイド文字の`szName`数。</span><span class="sxs-lookup"><span data-stu-id="cb14e-113">[out] The number of wide chars actually returned in `szName`.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="cb14e-114">[アウト]アセンブリ メタデータを格納する ASSEMBLYMETADATA 構造体へのポインター。</span><span class="sxs-lookup"><span data-stu-id="cb14e-114">[out] A pointer to an ASSEMBLYMETADATA structure that contains the assembly metadata.</span></span>  
  
 `pdwAssemblyFlags`  
 <span data-ttu-id="cb14e-115">[アウト]アセンブリに適用されるメタデータを記述するフラグ。</span><span class="sxs-lookup"><span data-stu-id="cb14e-115">[out] Flags that describe the metadata applied to an assembly.</span></span> <span data-ttu-id="cb14e-116">この値は、1 つ以上の[CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md)値の組み合わせです。</span><span class="sxs-lookup"><span data-stu-id="cb14e-116">This value is a combination of one or more [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cb14e-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="cb14e-117">Requirements</span></span>  
 <span data-ttu-id="cb14e-118">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb14e-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb14e-119">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="cb14e-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cb14e-120">**ライブラリ:** MsCorEE.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="cb14e-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="cb14e-121">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cb14e-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb14e-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="cb14e-122">See also</span></span>

- [<span data-ttu-id="cb14e-123">IMetaDataAssemblyImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cb14e-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
