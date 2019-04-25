---
title: IMetaDataAssemblyImport::GetExportedTypeProps メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetExportedTypeProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetExportedTypeProps
helpviewer_keywords:
- GetExportedTypeProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetExportedTypeProps method [.NET Framework metadata]
ms.assetid: 25ca7623-5a55-4f09-b44a-36b03d142278
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 91b1e4469f07954dc433769911c78d72bb3c36cb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61904983"
---
# <a name="imetadataassemblyimportgetexportedtypeprops-method"></a><span data-ttu-id="00924-102">IMetaDataAssemblyImport::GetExportedTypeProps メソッド</span><span class="sxs-lookup"><span data-stu-id="00924-102">IMetaDataAssemblyImport::GetExportedTypeProps Method</span></span>
<span data-ttu-id="00924-103">指定したメタデータ シグネチャを持つエクスポートされた型のプロパティのセットを取得します。</span><span class="sxs-lookup"><span data-stu-id="00924-103">Gets the set of properties of the exported type with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00924-104">構文</span><span class="sxs-lookup"><span data-stu-id="00924-104">Syntax</span></span>  
  
```  
HRESULT GetExportedTypeProps (  
    [in]  mdExportedType    mdct,   
    [out] LPWSTR            szName,   
    [in]  ULONG             cchName,   
    [out] ULONG             *pchName,   
    [out] mdToken           *ptkImplementation,   
    [out] mdTypeDef         *ptkTypeDef,   
    [out] DWORD             *pdwExportedTypeFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="00924-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="00924-105">Parameters</span></span>  
 `mdct`  
 <span data-ttu-id="00924-106">[in]`mdExportedType`エクスポートされた型を表すメタデータ トークン。</span><span class="sxs-lookup"><span data-stu-id="00924-106">[in] An `mdExportedType` metadata token that represents the exported type.</span></span>  
  
 `szName`  
 <span data-ttu-id="00924-107">[out]エクスポートされる型の名前。</span><span class="sxs-lookup"><span data-stu-id="00924-107">[out] The name of the exported type.</span></span>  
  
 `cchName`  
 <span data-ttu-id="00924-108">[in]ワイド文字単位のサイズの`szName`します。</span><span class="sxs-lookup"><span data-stu-id="00924-108">[in] The size, in wide characters, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="00924-109">[out]実際に返されるワイド文字の数 `szName`</span><span class="sxs-lookup"><span data-stu-id="00924-109">[out] The number of wide characters actually returned in `szName`</span></span>  
  
 `ptkImplementation`  
 <span data-ttu-id="00924-110">[out]`mdFile`、 `mdAssemblyRef`、または`mdExportedType`またはエクスポートされる型のプロパティにアクセスできるようにするメタデータ トークン。</span><span class="sxs-lookup"><span data-stu-id="00924-110">[out] An `mdFile`, `mdAssemblyRef`, or `mdExportedType` metadata token that contains or allows access to the properties of the exported type.</span></span>  
  
 `ptkTypeDef`  
 <span data-ttu-id="00924-111">[out]ポインター、`mdTypeDef`ファイル内の型を表すトークン。</span><span class="sxs-lookup"><span data-stu-id="00924-111">[out] A pointer to an `mdTypeDef` token that represents a type in the file.</span></span>  
  
 `pdwExportedTypeFlags`  
 <span data-ttu-id="00924-112">[out]エクスポートされた型に適用されるメタデータを記述するフラグへのポインター。</span><span class="sxs-lookup"><span data-stu-id="00924-112">[out] A pointer to the flags that describe the metadata applied to the exported type.</span></span> <span data-ttu-id="00924-113">1 つまたは複数フラグ値を指定できます[CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md)値。</span><span class="sxs-lookup"><span data-stu-id="00924-113">The flags value can be one or more [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="00924-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="00924-114">Requirements</span></span>  
 <span data-ttu-id="00924-115">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="00924-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00924-116">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="00924-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="00924-117">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="00924-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="00924-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00924-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00924-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="00924-119">See also</span></span>

- [<span data-ttu-id="00924-120">IMetaDataAssemblyImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="00924-120">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
