---
title: IMetaDataImport::EnumFields メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumFields
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumFields
helpviewer_keywords:
- EnumFields method [.NET Framework metadata]
- IMetaDataImport::EnumFields method [.NET Framework metadata]
ms.assetid: 1d23247e-c58c-45db-afd8-83aa89cde18e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 313dbd11f1d033f0e15de651b9c130cc98c217e9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62049935"
---
# <a name="imetadataimportenumfields-method"></a><span data-ttu-id="670e2-102">IMetaDataImport::EnumFields メソッド</span><span class="sxs-lookup"><span data-stu-id="670e2-102">IMetaDataImport::EnumFields Method</span></span>
<span data-ttu-id="670e2-103">指定した TypeDef トークンによって参照される型の FieldDef トークンを列挙します。</span><span class="sxs-lookup"><span data-stu-id="670e2-103">Enumerates FieldDef tokens for the type referenced by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="670e2-104">構文</span><span class="sxs-lookup"><span data-stu-id="670e2-104">Syntax</span></span>  
  
```  
HRESULT EnumFields (   
   [in, out] HCORENUM    *phEnum,   
   [in]      mdTypeDef   cl,   
   [out]     mdFieldDef  rFields[],   
   [in]      ULONG       cMax,   
   [out]     ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="670e2-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="670e2-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="670e2-106">[入力、出力]列挙子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="670e2-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="670e2-107">[in]フィールドが列挙クラスの TypeDef トークンです。</span><span class="sxs-lookup"><span data-stu-id="670e2-107">[in] The TypeDef token of the class whose fields are to be enumerated.</span></span>  
  
 `rFields`  
 <span data-ttu-id="670e2-108">[out]FieldDef トークンの一覧。</span><span class="sxs-lookup"><span data-stu-id="670e2-108">[out] The list of FieldDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="670e2-109">[in] `rFields` 配列の最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="670e2-109">[in] The maximum size of the `rFields` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="670e2-110">[out]実際に返される FieldDef トークン数`rFields`します。</span><span class="sxs-lookup"><span data-stu-id="670e2-110">[out] The actual number of FieldDef tokens returned in `rFields`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="670e2-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="670e2-111">Return Value</span></span>  
  
|<span data-ttu-id="670e2-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="670e2-112">HRESULT</span></span>|<span data-ttu-id="670e2-113">説明</span><span class="sxs-lookup"><span data-stu-id="670e2-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="670e2-114">`EnumFields` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="670e2-114">`EnumFields` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="670e2-115">列挙するフィールドはありません。</span><span class="sxs-lookup"><span data-stu-id="670e2-115">There are no fields to enumerate.</span></span> <span data-ttu-id="670e2-116">その場合は、`pcTokens`は 0 です。</span><span class="sxs-lookup"><span data-stu-id="670e2-116">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="670e2-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="670e2-117">Requirements</span></span>  
 <span data-ttu-id="670e2-118">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="670e2-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="670e2-119">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="670e2-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="670e2-120">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="670e2-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="670e2-121">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="670e2-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="670e2-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="670e2-122">See also</span></span>

- [<span data-ttu-id="670e2-123">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="670e2-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="670e2-124">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="670e2-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
