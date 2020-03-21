---
title: IMetaDataAssemblyImport::GetAssemblyRefProps メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetAssemblyRefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetAssemblyRefProps
helpviewer_keywords:
- IMetaDataAssemblyImport::GetAssemblyRefProps method [.NET Framework metadata]
- GetAssemblyRefProps method [.NET Framework metadata]
ms.assetid: 5c6b7fb4-cbca-4479-b650-ab9a99732ea0
topic_type:
- apiref
ms.openlocfilehash: 9aef471c1155070af0e9bcca14975a65bc5dc763
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175968"
---
# <a name="imetadataassemblyimportgetassemblyrefprops-method"></a><span data-ttu-id="bc20e-102">IMetaDataAssemblyImport::GetAssemblyRefProps メソッド</span><span class="sxs-lookup"><span data-stu-id="bc20e-102">IMetaDataAssemblyImport::GetAssemblyRefProps Method</span></span>
<span data-ttu-id="bc20e-103">指定したメタデータ シグネチャを持つアセンブリ参照のプロパティのセットを取得します。</span><span class="sxs-lookup"><span data-stu-id="bc20e-103">Gets the set of properties for the assembly reference with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc20e-104">構文</span><span class="sxs-lookup"><span data-stu-id="bc20e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyRefProps (  
    [in]  mdAssemblyRef        mdar,
    [out] const void          **ppbPublicKeyOrToken,
    [out] ULONG                *pcbPublicKeyOrToken,
    [out] LPWSTR               szName,
    [in]  ULONG                cchName,
    [out] ULONG                *pchName,
    [out] ASSEMBLYMETADATA     *pMetaData,
    [out] const void           **ppbHashValue,
    [out] ULONG                *pcbHashValue,
    [out] DWORD                *pdwAssemblyRefFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bc20e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="bc20e-105">Parameters</span></span>  
 `mdar`  
 <span data-ttu-id="bc20e-106">[in]プロパティ`mdAssemblyRef`を取得するアセンブリ参照を表すメタデータ トークン。</span><span class="sxs-lookup"><span data-stu-id="bc20e-106">[in] The `mdAssemblyRef` metadata token that represents the assembly reference for which to get the properties.</span></span>  
  
 `ppbPublicKeyOrToken`  
 <span data-ttu-id="bc20e-107">[アウト]公開キーまたはメタデータ トークンへのポインター。</span><span class="sxs-lookup"><span data-stu-id="bc20e-107">[out] A pointer to the public key or the metadata token.</span></span>  
  
 `pcbPublicKeyOrToken`  
 <span data-ttu-id="bc20e-108">[アウト]返された公開キーまたはトークンのバイト数。</span><span class="sxs-lookup"><span data-stu-id="bc20e-108">[out] The number of bytes in the returned public key or token.</span></span>  
  
 `szName`  
 <span data-ttu-id="bc20e-109">[アウト]アセンブリの簡易名。</span><span class="sxs-lookup"><span data-stu-id="bc20e-109">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="bc20e-110">[in]のサイズ、ワイド文字で`szName`、 のサイズ。</span><span class="sxs-lookup"><span data-stu-id="bc20e-110">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="bc20e-111">[アウト]で実際に返されるワイド文字の数へのポインタ`szName`。</span><span class="sxs-lookup"><span data-stu-id="bc20e-111">[out] A pointer to the number of wide chars actually returned in `szName`.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="bc20e-112">[アウト]アセンブリ メタデータを格納する ASSEMBLYMETADATA 構造体へのポインター。</span><span class="sxs-lookup"><span data-stu-id="bc20e-112">[out] A pointer to an ASSEMBLYMETADATA structure that contains the assembly metadata.</span></span>  
  
 `ppbHashValue`  
 <span data-ttu-id="bc20e-113">[アウト]ハッシュ値へのポインター。</span><span class="sxs-lookup"><span data-stu-id="bc20e-113">[out] A pointer to the hash value.</span></span> <span data-ttu-id="bc20e-114">これは、`PublicKey`[参照](../../../../docs/framework/unmanaged-api/metadata/assemblyrefflags-enumeration.md)されるアセンブリのプロパティの SHA-1 アルゴリズムを使用するハッシュです。</span><span class="sxs-lookup"><span data-stu-id="bc20e-114">This is the hash, using the SHA-1 algorithm, of the `PublicKey` property of the assembly being referenced, unless the arfFullOriginator flag of the [AssemblyRefFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyrefflags-enumeration.md) enumeration is set.</span></span>  
  
 `pcbHashValue`  
 <span data-ttu-id="bc20e-115">[アウト]返されたハッシュ値のワイド文字の数。</span><span class="sxs-lookup"><span data-stu-id="bc20e-115">[out] The number of wide chars in the returned hash value.</span></span>  
  
 `pdwAssemblyRefFlags`  
 <span data-ttu-id="bc20e-116">[アウト]アセンブリに適用されるメタデータを記述するフラグへのポインター。</span><span class="sxs-lookup"><span data-stu-id="bc20e-116">[out] A pointer to flags that describe the metadata applied to an assembly.</span></span> <span data-ttu-id="bc20e-117">フラグ値は、1 つまたは複数の[CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md)値の組み合わせです。</span><span class="sxs-lookup"><span data-stu-id="bc20e-117">The flags value is a combination of one or more [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) values.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bc20e-118">戻り値</span><span class="sxs-lookup"><span data-stu-id="bc20e-118">Return Value</span></span>  
 <span data-ttu-id="bc20e-119">このメソッドは、成功した場合はS_OKを返します。それ以外の場合は、Winerror.h ヘッダー ファイルで定義されているエラー コードのいずれかを返します。</span><span class="sxs-lookup"><span data-stu-id="bc20e-119">This method returns S_OK if it succeeds; otherwise, it returns one of the error codes defined in the Winerror.h header file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bc20e-120">必要条件</span><span class="sxs-lookup"><span data-stu-id="bc20e-120">Requirements</span></span>  
 <span data-ttu-id="bc20e-121">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bc20e-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc20e-122">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="bc20e-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bc20e-123">**ライブラリ:** MsCorEE.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="bc20e-123">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bc20e-124">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc20e-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc20e-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="bc20e-125">See also</span></span>

- [<span data-ttu-id="bc20e-126">IMetaDataAssemblyImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bc20e-126">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
