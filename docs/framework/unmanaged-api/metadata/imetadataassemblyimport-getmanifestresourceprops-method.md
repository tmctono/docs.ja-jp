---
title: IMetaDataAssemblyImport::GetManifestResourceProps メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetManifestResourceProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetManifestResourceProps
helpviewer_keywords:
- GetManifestResourceProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetManifestResourceProps method [.NET Framework metadata]
ms.assetid: 00be4789-ac63-4397-b2ec-1629a5c5a585
topic_type:
- apiref
ms.openlocfilehash: d87d0d46ede65cf44c84edba92fe246174088a4e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177653"
---
# <a name="imetadataassemblyimportgetmanifestresourceprops-method"></a><span data-ttu-id="ed0b3-102">IMetaDataAssemblyImport::GetManifestResourceProps メソッド</span><span class="sxs-lookup"><span data-stu-id="ed0b3-102">IMetaDataAssemblyImport::GetManifestResourceProps Method</span></span>
<span data-ttu-id="ed0b3-103">指定したメタデータ シグネチャを持つマニフェスト リソースのプロパティのセットを取得します。</span><span class="sxs-lookup"><span data-stu-id="ed0b3-103">Gets the set of properties of the manifest resource with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed0b3-104">構文</span><span class="sxs-lookup"><span data-stu-id="ed0b3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetManifestResourceProps (  
    [in]  mdManifestResource   mdmr,
    [out] LPWSTR               szName,
    [in]  ULONG                cchName,
    [out] ULONG                *pchName,
    [out] mdToken              *ptkImplementation,
    [out] DWORD                *pdwOffset,
    [out] DWORD                *pdwResourceFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ed0b3-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ed0b3-105">Parameters</span></span>  
 `mdmr`  
 <span data-ttu-id="ed0b3-106">[in]プロパティ`mdManifestResource`を取得するリソースを表すトークン。</span><span class="sxs-lookup"><span data-stu-id="ed0b3-106">[in] An `mdManifestResource` token that represents the resource for which to get the properties.</span></span>  
  
 `szName`  
 <span data-ttu-id="ed0b3-107">[アウト]リソースの名前。</span><span class="sxs-lookup"><span data-stu-id="ed0b3-107">[out] The name of the resource.</span></span>  
  
 `cchName`  
 <span data-ttu-id="ed0b3-108">[in]のサイズ、ワイド文字で`szName`、 のサイズ。</span><span class="sxs-lookup"><span data-stu-id="ed0b3-108">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="ed0b3-109">[アウト]で実際に返されるワイド文字の数へのポインタ`szName`。</span><span class="sxs-lookup"><span data-stu-id="ed0b3-109">[out] A pointer to the number of wide chars actually returned in `szName`.</span></span>  
  
 `ptkImplementation`  
 <span data-ttu-id="ed0b3-110">[アウト]リソースを`mdFile`含むファイルまたはアセンブリ`mdAssemblyRef`を表すトークンまたはトークンへのポインター。</span><span class="sxs-lookup"><span data-stu-id="ed0b3-110">[out] A pointer to an `mdFile` token or an `mdAssemblyRef` token that represents the file or assembly, respectively, that contains the resource.</span></span>  
  
 `pdwOffset`  
 <span data-ttu-id="ed0b3-111">[アウト]ファイル内のリソースの先頭へのオフセットを指定する値へのポインター。</span><span class="sxs-lookup"><span data-stu-id="ed0b3-111">[out] A pointer to a value that specifies the offset to the beginning of the resource within the file.</span></span>  
  
 `pdwResourceFlags`  
 <span data-ttu-id="ed0b3-112">[アウト]リソースに適用されるメタデータを記述するフラグへのポインター。</span><span class="sxs-lookup"><span data-stu-id="ed0b3-112">[out] A pointer to flags that describe the metadata applied to a resource.</span></span> <span data-ttu-id="ed0b3-113">フラグ値は、1 つ以上の[CorManifestResourceFlags](../../../../docs/framework/unmanaged-api/metadata/cormanifestresourceflags-enumeration.md)値の組み合わせです。</span><span class="sxs-lookup"><span data-stu-id="ed0b3-113">The flags value is a combination of one or more [CorManifestResourceFlags](../../../../docs/framework/unmanaged-api/metadata/cormanifestresourceflags-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed0b3-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="ed0b3-114">Requirements</span></span>  
 <span data-ttu-id="ed0b3-115">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ed0b3-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed0b3-116">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="ed0b3-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ed0b3-117">**ライブラリ:** MsCorEE.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="ed0b3-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ed0b3-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed0b3-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed0b3-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="ed0b3-119">See also</span></span>

- [<span data-ttu-id="ed0b3-120">IMetaDataAssemblyImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ed0b3-120">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
