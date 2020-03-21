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
ms.openlocfilehash: 15b58e01d4ce99f19f510c760819471b84380b45
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177759"
---
# <a name="imetadataassemblyimportgetexportedtypeprops-method"></a><span data-ttu-id="cecfa-102">IMetaDataAssemblyImport::GetExportedTypeProps メソッド</span><span class="sxs-lookup"><span data-stu-id="cecfa-102">IMetaDataAssemblyImport::GetExportedTypeProps Method</span></span>
<span data-ttu-id="cecfa-103">指定したメタデータ シグネチャを持つエクスポートされた型のプロパティのセットを取得します。</span><span class="sxs-lookup"><span data-stu-id="cecfa-103">Gets the set of properties of the exported type with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cecfa-104">構文</span><span class="sxs-lookup"><span data-stu-id="cecfa-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="cecfa-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="cecfa-105">Parameters</span></span>  
 `mdct`  
 <span data-ttu-id="cecfa-106">[in]エクスポート`mdExportedType`された型を表すメタデータ トークン。</span><span class="sxs-lookup"><span data-stu-id="cecfa-106">[in] An `mdExportedType` metadata token that represents the exported type.</span></span>  
  
 `szName`  
 <span data-ttu-id="cecfa-107">[アウト]エクスポートされた型の名前。</span><span class="sxs-lookup"><span data-stu-id="cecfa-107">[out] The name of the exported type.</span></span>  
  
 `cchName`  
 <span data-ttu-id="cecfa-108">[in]のサイズ (ワイド文字)`szName`です。</span><span class="sxs-lookup"><span data-stu-id="cecfa-108">[in] The size, in wide characters, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="cecfa-109">[アウト]実際に返されるワイド文字の数`szName`</span><span class="sxs-lookup"><span data-stu-id="cecfa-109">[out] The number of wide characters actually returned in `szName`</span></span>  
  
 `ptkImplementation`  
 <span data-ttu-id="cecfa-110">[アウト]エクスポート`mdFile`された`mdAssemblyRef`型の`mdExportedType`プロパティを格納または許可する 、または、エクスポートされた型のプロパティへのアクセスを許可する 、、、、またはメタデータ トークン。</span><span class="sxs-lookup"><span data-stu-id="cecfa-110">[out] An `mdFile`, `mdAssemblyRef`, or `mdExportedType` metadata token that contains or allows access to the properties of the exported type.</span></span>  
  
 `ptkTypeDef`  
 <span data-ttu-id="cecfa-111">[アウト]ファイル内の型`mdTypeDef`を表すトークンへのポインター。</span><span class="sxs-lookup"><span data-stu-id="cecfa-111">[out] A pointer to an `mdTypeDef` token that represents a type in the file.</span></span>  
  
 `pdwExportedTypeFlags`  
 <span data-ttu-id="cecfa-112">[アウト]エクスポートされた型に適用されるメタデータを記述するフラグへのポインター。</span><span class="sxs-lookup"><span data-stu-id="cecfa-112">[out] A pointer to the flags that describe the metadata applied to the exported type.</span></span> <span data-ttu-id="cecfa-113">フラグ値は、1 つまたは複数[の CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md)値にすることができます。</span><span class="sxs-lookup"><span data-stu-id="cecfa-113">The flags value can be one or more [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cecfa-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="cecfa-114">Requirements</span></span>  
 <span data-ttu-id="cecfa-115">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cecfa-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cecfa-116">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="cecfa-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cecfa-117">**ライブラリ:** MsCorEE.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="cecfa-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="cecfa-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cecfa-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cecfa-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="cecfa-119">See also</span></span>

- [<span data-ttu-id="cecfa-120">IMetaDataAssemblyImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cecfa-120">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
