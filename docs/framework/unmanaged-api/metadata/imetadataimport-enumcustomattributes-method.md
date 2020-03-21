---
title: IMetaDataImport::EnumCustomAttributes メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumCustomAttributes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumCustomAttributes
helpviewer_keywords:
- EnumCustomAttributes method [.NET Framework metadata]
- IMetaDataImport::EnumCustomAttributes method [.NET Framework metadata]
ms.assetid: 798513a0-68b1-4d04-bc5b-782a4445ea68
topic_type:
- apiref
ms.openlocfilehash: 61b5678a546bdbadbcc6d8ee86447cb17ce72b99
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175526"
---
# <a name="imetadataimportenumcustomattributes-method"></a><span data-ttu-id="7735b-102">IMetaDataImport::EnumCustomAttributes メソッド</span><span class="sxs-lookup"><span data-stu-id="7735b-102">IMetaDataImport::EnumCustomAttributes Method</span></span>
<span data-ttu-id="7735b-103">指定した型またはメンバーに関連付けられているカスタム属性定義トークンを列挙します。</span><span class="sxs-lookup"><span data-stu-id="7735b-103">Enumerates custom attribute-definition tokens associated with the specified type or member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7735b-104">構文</span><span class="sxs-lookup"><span data-stu-id="7735b-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumCustomAttributes (
   [in, out] HCORENUM      *phEnum,  
   [in]  mdToken            tk,
   [in]  mdToken            tkType,
   [out] mdCustomAttribute  rCustomAttributes[],
   [in]  ULONG              cMax,  
   [out, optional] ULONG   *pcCustomAttributes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7735b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7735b-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="7735b-106">[イン、アウト]返された列挙子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="7735b-106">[in, out] A pointer to the returned enumerator.</span></span>  
  
 `tk`  
 <span data-ttu-id="7735b-107">[in]列挙のスコープのトークン、またはすべてのカスタム属性の場合は 0。</span><span class="sxs-lookup"><span data-stu-id="7735b-107">[in] A token for the scope of the enumeration, or zero for all custom attributes.</span></span>  
  
 `tkType`  
 <span data-ttu-id="7735b-108">[in]列挙する属性の型のコンストラクター、または`null`すべての型のトークン。</span><span class="sxs-lookup"><span data-stu-id="7735b-108">[in] A token for the constructor of the type of the attributes to be enumerated, or `null` for all types.</span></span>  
  
 `rCustomAttributes`  
 <span data-ttu-id="7735b-109">[アウト]カスタム属性トークンの配列。</span><span class="sxs-lookup"><span data-stu-id="7735b-109">[out] An array of custom attribute tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="7735b-110">[in] `rCustomAttributes` 配列の最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="7735b-110">[in] The maximum size of the `rCustomAttributes` array.</span></span>  
  
 `pcCustomAttributes`  
 <span data-ttu-id="7735b-111">[アウト、オプション]に返されるトークン値の実際の`rCustomAttributes`数。</span><span class="sxs-lookup"><span data-stu-id="7735b-111">[out, optional] The actual number of token values returned in `rCustomAttributes`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7735b-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="7735b-112">Return Value</span></span>  
  
|<span data-ttu-id="7735b-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7735b-113">HRESULT</span></span>|<span data-ttu-id="7735b-114">説明</span><span class="sxs-lookup"><span data-stu-id="7735b-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="7735b-115">`EnumCustomAttributes`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="7735b-115">`EnumCustomAttributes` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="7735b-116">列挙するカスタム属性はありません。</span><span class="sxs-lookup"><span data-stu-id="7735b-116">There are no custom attributes to enumerate.</span></span> <span data-ttu-id="7735b-117">その場合は、`pcCustomAttributes`ゼロです。</span><span class="sxs-lookup"><span data-stu-id="7735b-117">In that case, `pcCustomAttributes` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7735b-118">必要条件</span><span class="sxs-lookup"><span data-stu-id="7735b-118">Requirements</span></span>  
 <span data-ttu-id="7735b-119">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7735b-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7735b-120">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="7735b-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7735b-121">**ライブラリ:** MsCorEE.dll にリソースとして含まれる</span><span class="sxs-lookup"><span data-stu-id="7735b-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7735b-122">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7735b-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7735b-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="7735b-123">See also</span></span>

- [<span data-ttu-id="7735b-124">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7735b-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="7735b-125">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7735b-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
