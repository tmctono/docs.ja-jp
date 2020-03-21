---
title: IMetaDataEmit2::DefineGenericParam メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.DefineGenericParam
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::DefineGenericParam
helpviewer_keywords:
- IMetaDataEmit2::DefineGenericParam method [.NET Framework metadata]
- DefineGenericParam method [.NET Framework metadata]
ms.assetid: 47b2a3b6-907d-43dc-858d-1ae7dca1316a
topic_type:
- apiref
ms.openlocfilehash: 1868d13a9dbb73dbdf64e49c395bdbff02ce89d4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177451"
---
# <a name="imetadataemit2definegenericparam-method"></a><span data-ttu-id="103fb-102">IMetaDataEmit2::DefineGenericParam メソッド</span><span class="sxs-lookup"><span data-stu-id="103fb-102">IMetaDataEmit2::DefineGenericParam Method</span></span>
<span data-ttu-id="103fb-103">ジェネリック型パラメーターの定義を作成し、そのジェネリック型パラメーターのトークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="103fb-103">Creates a definition for a generic type parameter, and gets a token to that generic type parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="103fb-104">構文</span><span class="sxs-lookup"><span data-stu-id="103fb-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineGenericParam (
    [in]  mdToken         tk,
    [in]  ULONG           ulParamSeq,
    [in]  DWORD           dwParamFlags,
    [in]  LPCWSTR         szname,
    [in]  DWORD           reserved,
    [in]  mdToken         rtkConstraints[],
    [out] mdGenericParam  *pgp  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="103fb-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="103fb-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="103fb-106">[in]ジェネリック`mdTypeDef``mdMethodDef`パラメーターを定義するメソッドまたはコンストラクターを表すトークン。</span><span class="sxs-lookup"><span data-stu-id="103fb-106">[in] An `mdTypeDef` or `mdMethodDef` token that represents the method or constructor for which to define a generic parameter.</span></span>  
  
 `ulParamSeq`  
 <span data-ttu-id="103fb-107">[in]ジェネリック パラメーターのインデックス。</span><span class="sxs-lookup"><span data-stu-id="103fb-107">[in] The index of the generic parameter.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="103fb-108">[in]ジェネリック パラメーターの型を記述する[CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md)列挙体の値。</span><span class="sxs-lookup"><span data-stu-id="103fb-108">[in] A value of the [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) enumeration that describes the type for the generic parameter.</span></span>  
  
 `szname`  
 <span data-ttu-id="103fb-109">[in]パラメーターの名前。</span><span class="sxs-lookup"><span data-stu-id="103fb-109">[in] The name of the parameter.</span></span>  
  
 `reserved`  
 <span data-ttu-id="103fb-110">[in]このパラメーターは、将来の拡張のために予約されています。</span><span class="sxs-lookup"><span data-stu-id="103fb-110">[in] This parameter is reserved for future extensibility.</span></span>  
  
 `rtkConstraints`  
 <span data-ttu-id="103fb-111">[in]型制約のゼロで終わる配列。</span><span class="sxs-lookup"><span data-stu-id="103fb-111">[in] A zero-terminated array of type constraints.</span></span> <span data-ttu-id="103fb-112">配列メンバーは`mdTypeDef`、 、`mdTypeRef`または`mdTypeSpec`メタデータ・トークンでなければなりません。</span><span class="sxs-lookup"><span data-stu-id="103fb-112">Array members must be an `mdTypeDef`, `mdTypeRef`, or `mdTypeSpec` metadata token.</span></span>  
  
 `pgp`  
 <span data-ttu-id="103fb-113">[アウト]ジェネリック パラメーターを表すトークン。</span><span class="sxs-lookup"><span data-stu-id="103fb-113">[out] A token that represents the generic parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="103fb-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="103fb-114">Requirements</span></span>  
 <span data-ttu-id="103fb-115">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="103fb-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="103fb-116">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="103fb-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="103fb-117">**ライブラリ:** MsCorEE.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="103fb-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="103fb-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="103fb-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="103fb-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="103fb-119">See also</span></span>

- [<span data-ttu-id="103fb-120">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="103fb-120">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="103fb-121">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="103fb-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
