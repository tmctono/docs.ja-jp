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
ms.openlocfilehash: bb8b531a884c9d3c2f33aa4aec5c4dbeaafe2b66
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177349"
---
# <a name="imetadataimportenumfieldswithname-method"></a><span data-ttu-id="c238f-102">IMetaDataImport::EnumFieldsWithName メソッド</span><span class="sxs-lookup"><span data-stu-id="c238f-102">IMetaDataImport::EnumFieldsWithName Method</span></span>
<span data-ttu-id="c238f-103">指定した名前を持つ指定した型の FieldDef トークンを列挙します。</span><span class="sxs-lookup"><span data-stu-id="c238f-103">Enumerates FieldDef tokens of the specified type with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c238f-104">構文</span><span class="sxs-lookup"><span data-stu-id="c238f-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="c238f-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c238f-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="c238f-106">[イン、アウト]列挙子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="c238f-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="c238f-107">[in]列挙するフィールドを持つ型のトークン。</span><span class="sxs-lookup"><span data-stu-id="c238f-107">[in] The token of the type whose fields are to be enumerated.</span></span>  
  
 `szName`  
 <span data-ttu-id="c238f-108">[in]列挙のスコープを制限するフィールド名。</span><span class="sxs-lookup"><span data-stu-id="c238f-108">[in] The field name that limits the scope of the enumeration.</span></span>  
  
 `rFields`  
 <span data-ttu-id="c238f-109">[アウト]FieldDef トークンを格納するために使用される配列。</span><span class="sxs-lookup"><span data-stu-id="c238f-109">[out] Array used to store the FieldDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="c238f-110">[in] `rFields` 配列の最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="c238f-110">[in] The maximum size of the `rFields` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="c238f-111">[アウト]に返される FieldDef トークンの`rFields`実際の数。</span><span class="sxs-lookup"><span data-stu-id="c238f-111">[out] The actual number of FieldDef tokens returned in `rFields`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c238f-112">解説</span><span class="sxs-lookup"><span data-stu-id="c238f-112">Remarks</span></span>  
 <span data-ttu-id="c238f-113">[IMetaDataImport::EnumFields](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumfields-method.md)と`EnumFieldsWithName`は異なり、指定された名前を持たないすべてのフィールド トークンを破棄します。</span><span class="sxs-lookup"><span data-stu-id="c238f-113">Unlike [IMetaDataImport::EnumFields](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumfields-method.md), `EnumFieldsWithName` discards all field tokens that do not have the specified name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c238f-114">戻り値</span><span class="sxs-lookup"><span data-stu-id="c238f-114">Return Value</span></span>  
  
|<span data-ttu-id="c238f-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c238f-115">HRESULT</span></span>|<span data-ttu-id="c238f-116">説明</span><span class="sxs-lookup"><span data-stu-id="c238f-116">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="c238f-117">`EnumFieldsWithName`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="c238f-117">`EnumFieldsWithName` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="c238f-118">列挙するフィールドがありません。</span><span class="sxs-lookup"><span data-stu-id="c238f-118">There are no fields to enumerate.</span></span> <span data-ttu-id="c238f-119">その場合は、`pcTokens`ゼロです。</span><span class="sxs-lookup"><span data-stu-id="c238f-119">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c238f-120">必要条件</span><span class="sxs-lookup"><span data-stu-id="c238f-120">Requirements</span></span>  
 <span data-ttu-id="c238f-121">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c238f-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c238f-122">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="c238f-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c238f-123">**ライブラリ:** MsCorEE.dll にリソースとして含まれる</span><span class="sxs-lookup"><span data-stu-id="c238f-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c238f-124">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c238f-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c238f-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="c238f-125">See also</span></span>

- [<span data-ttu-id="c238f-126">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c238f-126">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="c238f-127">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c238f-127">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
