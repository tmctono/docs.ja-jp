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
ms.openlocfilehash: be2845d1d660d86447cfbb6f2845a8e68b727e66
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175513"
---
# <a name="imetadataimportenumfields-method"></a><span data-ttu-id="471eb-102">IMetaDataImport::EnumFields メソッド</span><span class="sxs-lookup"><span data-stu-id="471eb-102">IMetaDataImport::EnumFields Method</span></span>
<span data-ttu-id="471eb-103">指定した TypeDef トークンによって参照される型の FieldDef トークンを列挙します。</span><span class="sxs-lookup"><span data-stu-id="471eb-103">Enumerates FieldDef tokens for the type referenced by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="471eb-104">構文</span><span class="sxs-lookup"><span data-stu-id="471eb-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumFields (
   [in, out] HCORENUM    *phEnum,
   [in]      mdTypeDef   cl,
   [out]     mdFieldDef  rFields[],
   [in]      ULONG       cMax,
   [out]     ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="471eb-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="471eb-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="471eb-106">[イン、アウト]列挙子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="471eb-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="471eb-107">[in]列挙されるフィールドを持つクラスの TypeDef トークン。</span><span class="sxs-lookup"><span data-stu-id="471eb-107">[in] The TypeDef token of the class whose fields are to be enumerated.</span></span>  
  
 `rFields`  
 <span data-ttu-id="471eb-108">[アウト]フィールド定義トークンのリスト。</span><span class="sxs-lookup"><span data-stu-id="471eb-108">[out] The list of FieldDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="471eb-109">[in] `rFields` 配列の最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="471eb-109">[in] The maximum size of the `rFields` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="471eb-110">[アウト]に返される FieldDef トークンの`rFields`実際の数。</span><span class="sxs-lookup"><span data-stu-id="471eb-110">[out] The actual number of FieldDef tokens returned in `rFields`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="471eb-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="471eb-111">Return Value</span></span>  
  
|<span data-ttu-id="471eb-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="471eb-112">HRESULT</span></span>|<span data-ttu-id="471eb-113">説明</span><span class="sxs-lookup"><span data-stu-id="471eb-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="471eb-114">`EnumFields`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="471eb-114">`EnumFields` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="471eb-115">列挙するフィールドがありません。</span><span class="sxs-lookup"><span data-stu-id="471eb-115">There are no fields to enumerate.</span></span> <span data-ttu-id="471eb-116">その場合は、`pcTokens`ゼロです。</span><span class="sxs-lookup"><span data-stu-id="471eb-116">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="471eb-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="471eb-117">Requirements</span></span>  
 <span data-ttu-id="471eb-118">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="471eb-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="471eb-119">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="471eb-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="471eb-120">**ライブラリ:** MsCorEE.dll にリソースとして含まれる</span><span class="sxs-lookup"><span data-stu-id="471eb-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="471eb-121">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="471eb-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="471eb-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="471eb-122">See also</span></span>

- [<span data-ttu-id="471eb-123">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="471eb-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="471eb-124">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="471eb-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
