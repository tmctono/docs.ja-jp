---
title: IMetaDataImport2::EnumGenericParams メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.EnumGenericParams
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::EnumGenericParams
helpviewer_keywords:
- EnumGenericParams method [.NET Framework metadata]
- IMetaDataImport2::EnumGenericParams method [.NET Framework metadata]
ms.assetid: b50488a5-3cf0-483c-82dc-2892a3ec61ac
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 44e1dc93580c6c4190ca04826824b519c67ee4e0
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57494930"
---
# <a name="imetadataimport2enumgenericparams-method"></a><span data-ttu-id="0f128-102">IMetaDataImport2::EnumGenericParams メソッド</span><span class="sxs-lookup"><span data-stu-id="0f128-102">IMetaDataImport2::EnumGenericParams Method</span></span>
<span data-ttu-id="0f128-103">トークンのジェネリック パラメーター トークンを指定した TypeDef または MethodDef に関連付けられた配列の列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="0f128-103">Gets an enumerator for an array of generic parameter tokens associated with the specified TypeDef or MethodDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f128-104">構文</span><span class="sxs-lookup"><span data-stu-id="0f128-104">Syntax</span></span>  
  
```  
HRESULT EnumGenericParams (  
   [in, out] HCORENUM     *phEnum,   
   [in]  mdToken          tk,  
   [out] mdGenericParam   rGenericParams[],   
   [in]  ULONG            cMax,   
   [out] ULONG            *pcGenericParams  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0f128-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0f128-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="0f128-106">[入力、出力]列挙子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="0f128-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `tk`  
 <span data-ttu-id="0f128-107">[in]ジェネリック パラメーターを持つが列挙する TypeDef または MethodDef トークンです。</span><span class="sxs-lookup"><span data-stu-id="0f128-107">[in] The TypeDef or MethodDef token whose generic parameters are to be enumerated.</span></span>  
  
 `rGenericParams`  
 <span data-ttu-id="0f128-108">[out]列挙するために、ジェネリック パラメーターの配列。</span><span class="sxs-lookup"><span data-stu-id="0f128-108">[out] The array of generic parameters to enumerate.</span></span>  
  
 `cMax`  
 <span data-ttu-id="0f128-109">[in]配置するトークンの要求の最大数`rGenericParams`します。</span><span class="sxs-lookup"><span data-stu-id="0f128-109">[in] The requested maximum number of tokens to place in `rGenericParams`.</span></span>  
  
 `pcGenericParams`  
 <span data-ttu-id="0f128-110">[out]返されたトークンの数に配置`rGenericParams`します。</span><span class="sxs-lookup"><span data-stu-id="0f128-110">[out] The returned number of tokens placed in `rGenericParams`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0f128-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="0f128-111">Return Value</span></span>  
  
|<span data-ttu-id="0f128-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0f128-112">HRESULT</span></span>|<span data-ttu-id="0f128-113">説明</span><span class="sxs-lookup"><span data-stu-id="0f128-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="0f128-114">`EnumGenericParams` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="0f128-114">`EnumGenericParams` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="0f128-115">`phEnum` メンバーの要素がありません。</span><span class="sxs-lookup"><span data-stu-id="0f128-115">`phEnum` has no member elements.</span></span> <span data-ttu-id="0f128-116">この場合、 `pcGenericParams` 0 (ゼロ) に設定されます。</span><span class="sxs-lookup"><span data-stu-id="0f128-116">In this case, `pcGenericParams` is set to 0 (zero).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0f128-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="0f128-117">Requirements</span></span>  
 <span data-ttu-id="0f128-118">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f128-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f128-119">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0f128-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0f128-120">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="0f128-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0f128-121">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f128-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f128-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="0f128-122">See also</span></span>
- [<span data-ttu-id="0f128-123">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0f128-123">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [<span data-ttu-id="0f128-124">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0f128-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
