---
title: IMetaDataImport::EnumFieldsWithName メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumFieldsWithName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumFieldsWithName
helpviewer_keywords:
- IMetaDataImport::EnumFieldsWithName method [.NET Framework metadata]
- EnumFieldsWithName method [.NET Framework metadata]
ms.assetid: 42145e8d-000f-4d0b-ae43-c08201190fa2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 71a2c7a61d573c1e17d0e8fefcd34d60e05ed3c5
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780478"
---
# <a name="imetadataimportenumfieldswithname-method"></a><span data-ttu-id="b125d-102">IMetaDataImport::EnumFieldsWithName メソッド</span><span class="sxs-lookup"><span data-stu-id="b125d-102">IMetaDataImport::EnumFieldsWithName Method</span></span>
<span data-ttu-id="b125d-103">指定した名前を持つ指定した型の FieldDef トークンを列挙します。</span><span class="sxs-lookup"><span data-stu-id="b125d-103">Enumerates FieldDef tokens of the specified type with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b125d-104">構文</span><span class="sxs-lookup"><span data-stu-id="b125d-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumFieldsWithName (  
   [in, out] HCORENUM    *phEnum,   
   [in]  mdTypeDef       cl,   
   [in]  LPCWSTR         szName,   
   [out] mdFieldDef      rFields[],   
   [in]  ULONG           cMax,   
   [out] ULONG           *pcTokens   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b125d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b125d-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="b125d-106">[入力、出力]列挙子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="b125d-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="b125d-107">[in]フィールドが列挙型のトークンです。</span><span class="sxs-lookup"><span data-stu-id="b125d-107">[in] The token of the type whose fields are to be enumerated.</span></span>  
  
 `szName`  
 <span data-ttu-id="b125d-108">[in]列挙体のスコープを制限するフィールド名です。</span><span class="sxs-lookup"><span data-stu-id="b125d-108">[in] The field name that limits the scope of the enumeration.</span></span>  
  
 `rFields`  
 <span data-ttu-id="b125d-109">[out]配列の FieldDef トークンを格納するために使用します。</span><span class="sxs-lookup"><span data-stu-id="b125d-109">[out] Array used to store the FieldDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="b125d-110">[in] `rFields` 配列の最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="b125d-110">[in] The maximum size of the `rFields` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="b125d-111">[out]実際に返される FieldDef トークン数`rFields`します。</span><span class="sxs-lookup"><span data-stu-id="b125d-111">[out] The actual number of FieldDef tokens returned in `rFields`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b125d-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="b125d-112">Remarks</span></span>  
 <span data-ttu-id="b125d-113">異なり[imetadataimport::enumfields](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumfields-method.md)、`EnumFieldsWithName`を指定した名前を持たないすべてのフィールドのトークンを破棄します。</span><span class="sxs-lookup"><span data-stu-id="b125d-113">Unlike [IMetaDataImport::EnumFields](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumfields-method.md), `EnumFieldsWithName` discards all field tokens that do not have the specified name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b125d-114">戻り値</span><span class="sxs-lookup"><span data-stu-id="b125d-114">Return Value</span></span>  
  
|<span data-ttu-id="b125d-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b125d-115">HRESULT</span></span>|<span data-ttu-id="b125d-116">説明</span><span class="sxs-lookup"><span data-stu-id="b125d-116">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="b125d-117">`EnumFieldsWithName` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="b125d-117">`EnumFieldsWithName` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="b125d-118">列挙するフィールドはありません。</span><span class="sxs-lookup"><span data-stu-id="b125d-118">There are no fields to enumerate.</span></span> <span data-ttu-id="b125d-119">その場合は、`pcTokens`は 0 です。</span><span class="sxs-lookup"><span data-stu-id="b125d-119">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b125d-120">必要条件</span><span class="sxs-lookup"><span data-stu-id="b125d-120">Requirements</span></span>  
 <span data-ttu-id="b125d-121">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b125d-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b125d-122">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b125d-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b125d-123">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="b125d-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b125d-124">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b125d-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b125d-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="b125d-125">See also</span></span>

- [<span data-ttu-id="b125d-126">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b125d-126">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="b125d-127">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b125d-127">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
