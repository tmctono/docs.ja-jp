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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59186682"
---
# <a name="imetadataimport2enumgenericparamconstraints-method"></a><span data-ttu-id="8f269-102">IMetaDataImport2::EnumGenericParamConstraints メソッド</span><span class="sxs-lookup"><span data-stu-id="8f269-102">IMetaDataImport2::EnumGenericParamConstraints Method</span></span>
<span data-ttu-id="8f269-103">指定したトークンによって表されるジェネリック パラメーターに関連付けられているジェネリック パラメーターの制約の配列の列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="8f269-103">Gets an enumerator for an array of generic parameter constraints associated with the generic parameter represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f269-104">構文</span><span class="sxs-lookup"><span data-stu-id="8f269-104">Syntax</span></span>  
  
```  
HRESULT EnumGenericParamConstraints (  
    [in, out] HCORENUM                *phEnum,  
    [in]  mdGenericParam              tk,  
    [out] mdGenericParamConstraint    rGenericParamConstraints[],  
    [in]  ULONG                       cMax,  
    [out] ULONG                       *pcGenericParamConstraints  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8f269-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8f269-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="8f269-106">[入力、出力]列挙子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="8f269-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `tk`  
 <span data-ttu-id="8f269-107">[in]  ジェネリック パラメーターの制約が列挙を表すトークンです。</span><span class="sxs-lookup"><span data-stu-id="8f269-107">[in]   A token that represents the generic parameter whose constraints are to be enumerated.</span></span>  
  
 `rGenericParamConstraints`  
 <span data-ttu-id="8f269-108">[out]列挙するために、ジェネリック パラメーターの制約の配列。</span><span class="sxs-lookup"><span data-stu-id="8f269-108">[out] The array of generic parameter constraints to enumerate.</span></span>  
  
 `cMax`  
 <span data-ttu-id="8f269-109">[in]  配置するトークンの要求の最大数`rGenericParamConstraints`します。</span><span class="sxs-lookup"><span data-stu-id="8f269-109">[in]   The requested maximum number of tokens to place in `rGenericParamConstraints`.</span></span>  
  
 `pcGenericParamConstraints`  
 <span data-ttu-id="8f269-110">[out]トークンの数へのポインターに配置`rGenericParamConstraints`します。</span><span class="sxs-lookup"><span data-stu-id="8f269-110">[out] A pointer to the number of tokens placed in `rGenericParamConstraints`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8f269-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="8f269-111">Return Value</span></span>  
  
|<span data-ttu-id="8f269-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8f269-112">HRESULT</span></span>|<span data-ttu-id="8f269-113">説明</span><span class="sxs-lookup"><span data-stu-id="8f269-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|`EnumGenericParameterConstraints` <span data-ttu-id="8f269-114">正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="8f269-114">returned successfully.</span></span>|  
|`S_FALSE`|`phEnum` <span data-ttu-id="8f269-115">メンバーの要素がありません。</span><span class="sxs-lookup"><span data-stu-id="8f269-115">has no member elements.</span></span> <span data-ttu-id="8f269-116">この場合、 `pcGenericParameterConstraints` 0 (ゼロ) に設定されます。</span><span class="sxs-lookup"><span data-stu-id="8f269-116">In this case, `pcGenericParameterConstraints` is set to 0 (zero).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8f269-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="8f269-117">Requirements</span></span>  
 <span data-ttu-id="8f269-118">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f269-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f269-119">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="8f269-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8f269-120">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="8f269-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="8f269-121">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="8f269-121">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8f269-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="8f269-122">See also</span></span>

- [<span data-ttu-id="8f269-123">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8f269-123">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [<span data-ttu-id="8f269-124">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8f269-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
