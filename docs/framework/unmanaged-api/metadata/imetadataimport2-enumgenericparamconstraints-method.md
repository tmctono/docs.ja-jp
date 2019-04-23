---
title: IMetaDataImport2::EnumGenericParamConstraints メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.EnumGenericParamConstraints
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::EnumGenericParamConstraints
helpviewer_keywords:
- EnumGenericParamConstraints method [.NET Framework metadata]
- IMetaDataImport2::EnumGenericParamConstraints method [.NET Framework metadata]
ms.assetid: 8a7d4e40-28fe-4e14-b801-4049880130e7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f66b0145dbaece7292d2ccad169a97fbb10b6d11
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59186682"
---
# <a name="imetadataimport2enumgenericparamconstraints-method"></a><span data-ttu-id="fbf45-102">IMetaDataImport2::EnumGenericParamConstraints メソッド</span><span class="sxs-lookup"><span data-stu-id="fbf45-102">IMetaDataImport2::EnumGenericParamConstraints Method</span></span>
<span data-ttu-id="fbf45-103">指定したトークンによって表されるジェネリック パラメーターに関連付けられているジェネリック パラメーターの制約の配列の列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="fbf45-103">Gets an enumerator for an array of generic parameter constraints associated with the generic parameter represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fbf45-104">構文</span><span class="sxs-lookup"><span data-stu-id="fbf45-104">Syntax</span></span>  
  
```  
HRESULT EnumGenericParamConstraints (  
    [in, out] HCORENUM                *phEnum,  
    [in]  mdGenericParam              tk,  
    [out] mdGenericParamConstraint    rGenericParamConstraints[],  
    [in]  ULONG                       cMax,  
    [out] ULONG                       *pcGenericParamConstraints  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fbf45-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="fbf45-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="fbf45-106">[入力、出力]列挙子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="fbf45-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `tk`  
 <span data-ttu-id="fbf45-107">[in]  ジェネリック パラメーターの制約が列挙を表すトークンです。</span><span class="sxs-lookup"><span data-stu-id="fbf45-107">[in]   A token that represents the generic parameter whose constraints are to be enumerated.</span></span>  
  
 `rGenericParamConstraints`  
 <span data-ttu-id="fbf45-108">[out]列挙するために、ジェネリック パラメーターの制約の配列。</span><span class="sxs-lookup"><span data-stu-id="fbf45-108">[out] The array of generic parameter constraints to enumerate.</span></span>  
  
 `cMax`  
 <span data-ttu-id="fbf45-109">[in]  配置するトークンの要求の最大数`rGenericParamConstraints`します。</span><span class="sxs-lookup"><span data-stu-id="fbf45-109">[in]   The requested maximum number of tokens to place in `rGenericParamConstraints`.</span></span>  
  
 `pcGenericParamConstraints`  
 <span data-ttu-id="fbf45-110">[out]トークンの数へのポインターに配置`rGenericParamConstraints`します。</span><span class="sxs-lookup"><span data-stu-id="fbf45-110">[out] A pointer to the number of tokens placed in `rGenericParamConstraints`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fbf45-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="fbf45-111">Return Value</span></span>  
  
|<span data-ttu-id="fbf45-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fbf45-112">HRESULT</span></span>|<span data-ttu-id="fbf45-113">説明</span><span class="sxs-lookup"><span data-stu-id="fbf45-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="fbf45-114">`EnumGenericParameterConstraints` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="fbf45-114">`EnumGenericParameterConstraints` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="fbf45-115">`phEnum` メンバーの要素がありません。</span><span class="sxs-lookup"><span data-stu-id="fbf45-115">`phEnum` has no member elements.</span></span> <span data-ttu-id="fbf45-116">この場合、 `pcGenericParameterConstraints` 0 (ゼロ) に設定されます。</span><span class="sxs-lookup"><span data-stu-id="fbf45-116">In this case, `pcGenericParameterConstraints` is set to 0 (zero).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fbf45-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="fbf45-117">Requirements</span></span>  
 <span data-ttu-id="fbf45-118">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fbf45-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fbf45-119">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="fbf45-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fbf45-120">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="fbf45-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fbf45-121">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fbf45-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbf45-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="fbf45-122">See also</span></span>

- [<span data-ttu-id="fbf45-123">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fbf45-123">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [<span data-ttu-id="fbf45-124">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fbf45-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
