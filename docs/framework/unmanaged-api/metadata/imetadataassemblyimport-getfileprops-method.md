---
title: IMetaDataAssemblyImport::GetFileProps メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetFileProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetFileProps
helpviewer_keywords:
- GetFileProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetFileProps method [.NET Framework metadata]
ms.assetid: c5e6216f-ae3d-4697-9688-66b69c1251ec
topic_type:
- apiref
ms.openlocfilehash: 78c192f10f629a0c1316ae7af7fc774819f4de8f
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007482"
---
# <a name="imetadataassemblyimportgetfileprops-method"></a><span data-ttu-id="7f33b-102">IMetaDataAssemblyImport::GetFileProps メソッド</span><span class="sxs-lookup"><span data-stu-id="7f33b-102">IMetaDataAssemblyImport::GetFileProps Method</span></span>
<span data-ttu-id="7f33b-103">指定したメタデータシグネチャを持つファイルのプロパティを取得します。</span><span class="sxs-lookup"><span data-stu-id="7f33b-103">Gets the properties of the file with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f33b-104">構文</span><span class="sxs-lookup"><span data-stu-id="7f33b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFileProps (  
    [in]  mdFile      mdf,
    [out] LPWSTR      szName,
    [in]  ULONG       cchName,
    [out] ULONG       *pchName,
    [out] const void  **ppbHashValue,
    [out] ULONG       *pcbHashValue,
    [out] DWORD       *pdwFileFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7f33b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7f33b-105">Parameters</span></span>  
 `mdf`  
 <span data-ttu-id="7f33b-106">から`mdFile`プロパティを取得する対象のファイルを表すメタデータトークン。</span><span class="sxs-lookup"><span data-stu-id="7f33b-106">[in] The `mdFile` metadata token that represents the file for which to get the properties.</span></span>  
  
 `szName`  
 <span data-ttu-id="7f33b-107">入出力ファイルの簡易名。</span><span class="sxs-lookup"><span data-stu-id="7f33b-107">[out] The simple name of the file.</span></span>  
  
 `cchName`  
 <span data-ttu-id="7f33b-108">からのサイズ (ワイド文字数) `szName` 。</span><span class="sxs-lookup"><span data-stu-id="7f33b-108">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="7f33b-109">入出力実際にで返されるワイド文字数 `szName` 。</span><span class="sxs-lookup"><span data-stu-id="7f33b-109">[out] The number of wide chars actually returned in `szName`.</span></span>  
  
 `ppbHashValue`  
 <span data-ttu-id="7f33b-110">入出力ハッシュ値へのポインター。</span><span class="sxs-lookup"><span data-stu-id="7f33b-110">[out] A pointer to the hash value.</span></span> <span data-ttu-id="7f33b-111">これは、ファイルの SHA-1 アルゴリズムを使用したハッシュです。</span><span class="sxs-lookup"><span data-stu-id="7f33b-111">This is the hash, using the SHA-1 algorithm, of the file.</span></span>  
  
 `pcbHashValue`  
 <span data-ttu-id="7f33b-112">入出力返されたハッシュ値のワイド文字の数。</span><span class="sxs-lookup"><span data-stu-id="7f33b-112">[out] The number of wide chars in the returned hash value.</span></span>  
  
 `pdwFileFlags`  
 <span data-ttu-id="7f33b-113">入出力ファイルに適用されるメタデータを記述するフラグへのポインター。</span><span class="sxs-lookup"><span data-stu-id="7f33b-113">[out] A pointer to the flags that describe the metadata applied to a file.</span></span> <span data-ttu-id="7f33b-114">Flags 値は、1つまたは複数の[Corfileflags](corfileflags-enumeration.md)値を組み合わせたものです。</span><span class="sxs-lookup"><span data-stu-id="7f33b-114">The flags value is a combination of one or more [CorFileFlags](corfileflags-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7f33b-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="7f33b-115">Requirements</span></span>  
 <span data-ttu-id="7f33b-116">**プラットフォーム:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7f33b-116">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7f33b-117">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="7f33b-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7f33b-118">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="7f33b-118">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7f33b-119">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7f33b-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f33b-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="7f33b-120">See also</span></span>

- [<span data-ttu-id="7f33b-121">IMetaDataAssemblyImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7f33b-121">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
