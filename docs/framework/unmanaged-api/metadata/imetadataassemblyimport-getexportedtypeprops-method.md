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
ms.openlocfilehash: 944941c2356cae93ecc85f1714b4b29aefcb50ad
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008405"
---
# <a name="imetadataassemblyimportgetexportedtypeprops-method"></a><span data-ttu-id="5c5df-102">IMetaDataAssemblyImport::GetExportedTypeProps メソッド</span><span class="sxs-lookup"><span data-stu-id="5c5df-102">IMetaDataAssemblyImport::GetExportedTypeProps Method</span></span>
<span data-ttu-id="5c5df-103">指定したメタデータシグネチャを持つ、エクスポートされた型のプロパティのセットを取得します。</span><span class="sxs-lookup"><span data-stu-id="5c5df-103">Gets the set of properties of the exported type with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c5df-104">構文</span><span class="sxs-lookup"><span data-stu-id="5c5df-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="5c5df-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5c5df-105">Parameters</span></span>  
 `mdct`  
 <span data-ttu-id="5c5df-106">からエクスポートされた `mdExportedType` 型を表すメタデータトークン。</span><span class="sxs-lookup"><span data-stu-id="5c5df-106">[in] An `mdExportedType` metadata token that represents the exported type.</span></span>  
  
 `szName`  
 <span data-ttu-id="5c5df-107">入出力エクスポートされた型の名前。</span><span class="sxs-lookup"><span data-stu-id="5c5df-107">[out] The name of the exported type.</span></span>  
  
 `cchName`  
 <span data-ttu-id="5c5df-108">からのサイズ (ワイド文字単位) `szName` 。</span><span class="sxs-lookup"><span data-stu-id="5c5df-108">[in] The size, in wide characters, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="5c5df-109">入出力実際に返されるワイド文字の数`szName`</span><span class="sxs-lookup"><span data-stu-id="5c5df-109">[out] The number of wide characters actually returned in `szName`</span></span>  
  
 `ptkImplementation`  
 <span data-ttu-id="5c5df-110">入出力`mdFile` `mdAssemblyRef` エクスポートされた `mdExportedType` 型のプロパティへのアクセスを格納または許可する、、、またはメタデータトークン。</span><span class="sxs-lookup"><span data-stu-id="5c5df-110">[out] An `mdFile`, `mdAssemblyRef`, or `mdExportedType` metadata token that contains or allows access to the properties of the exported type.</span></span>  
  
 `ptkTypeDef`  
 <span data-ttu-id="5c5df-111">入出力`mdTypeDef`ファイル内の型を表すトークンへのポインター。</span><span class="sxs-lookup"><span data-stu-id="5c5df-111">[out] A pointer to an `mdTypeDef` token that represents a type in the file.</span></span>  
  
 `pdwExportedTypeFlags`  
 <span data-ttu-id="5c5df-112">入出力エクスポートされた型に適用されるメタデータを記述するフラグへのポインター。</span><span class="sxs-lookup"><span data-stu-id="5c5df-112">[out] A pointer to the flags that describe the metadata applied to the exported type.</span></span> <span data-ttu-id="5c5df-113">Flags 値には、1つまたは複数の[Cortypeattr](cortypeattr-enumeration.md)値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="5c5df-113">The flags value can be one or more [CorTypeAttr](cortypeattr-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c5df-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="5c5df-114">Requirements</span></span>  
 <span data-ttu-id="5c5df-115">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c5df-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c5df-116">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="5c5df-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5c5df-117">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="5c5df-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5c5df-118">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c5df-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c5df-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="5c5df-119">See also</span></span>

- [<span data-ttu-id="5c5df-120">IMetaDataAssemblyImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5c5df-120">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
