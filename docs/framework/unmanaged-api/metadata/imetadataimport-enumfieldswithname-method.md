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
ms.openlocfilehash: 68261b165847a5c3ee29adbc4908451fb00c5443
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84492266"
---
# <a name="imetadataimportenumfieldswithname-method"></a><span data-ttu-id="cf745-102">IMetaDataImport::EnumFieldsWithName メソッド</span><span class="sxs-lookup"><span data-stu-id="cf745-102">IMetaDataImport::EnumFieldsWithName Method</span></span>
<span data-ttu-id="cf745-103">指定した名前を持つ指定した型の FieldDef トークンを列挙します。</span><span class="sxs-lookup"><span data-stu-id="cf745-103">Enumerates FieldDef tokens of the specified type with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf745-104">構文</span><span class="sxs-lookup"><span data-stu-id="cf745-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="cf745-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="cf745-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="cf745-106">[入力、出力]列挙子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="cf745-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="cf745-107">からフィールドを列挙する型のトークン。</span><span class="sxs-lookup"><span data-stu-id="cf745-107">[in] The token of the type whose fields are to be enumerated.</span></span>  
  
 `szName`  
 <span data-ttu-id="cf745-108">から列挙型のスコープを制限するフィールド名。</span><span class="sxs-lookup"><span data-stu-id="cf745-108">[in] The field name that limits the scope of the enumeration.</span></span>  
  
 `rFields`  
 <span data-ttu-id="cf745-109">入出力FieldDef トークンを格納するために使用される配列。</span><span class="sxs-lookup"><span data-stu-id="cf745-109">[out] Array used to store the FieldDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="cf745-110">[in] `rFields` 配列の最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="cf745-110">[in] The maximum size of the `rFields` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="cf745-111">入出力で返された FieldDef トークンの実際の数 `rFields` 。</span><span class="sxs-lookup"><span data-stu-id="cf745-111">[out] The actual number of FieldDef tokens returned in `rFields`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cf745-112">解説</span><span class="sxs-lookup"><span data-stu-id="cf745-112">Remarks</span></span>  
 <span data-ttu-id="cf745-113">[IMetaDataImport:: EnumFields](imetadataimport-enumfields-method.md)とは異なり、は `EnumFieldsWithName` 指定された名前のないすべてのフィールドトークンを破棄します。</span><span class="sxs-lookup"><span data-stu-id="cf745-113">Unlike [IMetaDataImport::EnumFields](imetadataimport-enumfields-method.md), `EnumFieldsWithName` discards all field tokens that do not have the specified name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cf745-114">戻り値</span><span class="sxs-lookup"><span data-stu-id="cf745-114">Return Value</span></span>  
  
|<span data-ttu-id="cf745-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="cf745-115">HRESULT</span></span>|<span data-ttu-id="cf745-116">説明</span><span class="sxs-lookup"><span data-stu-id="cf745-116">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="cf745-117">`EnumFieldsWithName`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="cf745-117">`EnumFieldsWithName` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="cf745-118">列挙するフィールドがありません。</span><span class="sxs-lookup"><span data-stu-id="cf745-118">There are no fields to enumerate.</span></span> <span data-ttu-id="cf745-119">この場合、 `pcTokens` は0になります。</span><span class="sxs-lookup"><span data-stu-id="cf745-119">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cf745-120">要件</span><span class="sxs-lookup"><span data-stu-id="cf745-120">Requirements</span></span>  
 <span data-ttu-id="cf745-121">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cf745-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf745-122">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="cf745-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cf745-123">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="cf745-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="cf745-124">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf745-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf745-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="cf745-125">See also</span></span>

- [<span data-ttu-id="cf745-126">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cf745-126">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="cf745-127">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cf745-127">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
