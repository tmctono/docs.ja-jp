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
ms.openlocfilehash: 55709e79cd8bdb36fe1e32ee8a699fccb1b1bbc8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175305"
---
# <a name="imetadataimport2enumgenericparams-method"></a><span data-ttu-id="f6f04-102">IMetaDataImport2::EnumGenericParams メソッド</span><span class="sxs-lookup"><span data-stu-id="f6f04-102">IMetaDataImport2::EnumGenericParams Method</span></span>
<span data-ttu-id="f6f04-103">指定した TypeDef トークンまたは MethodDef トークンに関連付けられているジェネリック パラメーター トークンの配列の列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="f6f04-103">Gets an enumerator for an array of generic parameter tokens associated with the specified TypeDef or MethodDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6f04-104">構文</span><span class="sxs-lookup"><span data-stu-id="f6f04-104">Syntax</span></span>  
  
```cpp
HRESULT EnumGenericParams (  
   [in, out] HCORENUM     *phEnum,
   [in]  mdToken          tk,  
   [out] mdGenericParam   rGenericParams[],
   [in]  ULONG            cMax,
   [out] ULONG            *pcGenericParams  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f6f04-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f6f04-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="f6f04-106">[イン、アウト]列挙子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="f6f04-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `tk`  
 <span data-ttu-id="f6f04-107">[in]ジェネリック パラメーターを列挙する TypeDef トークンまたは MethodDef トークン。</span><span class="sxs-lookup"><span data-stu-id="f6f04-107">[in] The TypeDef or MethodDef token whose generic parameters are to be enumerated.</span></span>  
  
 `rGenericParams`  
 <span data-ttu-id="f6f04-108">[アウト]列挙するジェネリック パラメーターの配列。</span><span class="sxs-lookup"><span data-stu-id="f6f04-108">[out] The array of generic parameters to enumerate.</span></span>  
  
 `cMax`  
 <span data-ttu-id="f6f04-109">[in]に配置するトークンの要求最大数`rGenericParams`。</span><span class="sxs-lookup"><span data-stu-id="f6f04-109">[in] The requested maximum number of tokens to place in `rGenericParams`.</span></span>  
  
 `pcGenericParams`  
 <span data-ttu-id="f6f04-110">[アウト]に格納されたトークンの数が`rGenericParams`返されます。</span><span class="sxs-lookup"><span data-stu-id="f6f04-110">[out] The returned number of tokens placed in `rGenericParams`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f6f04-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="f6f04-111">Return Value</span></span>  
  
|<span data-ttu-id="f6f04-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f6f04-112">HRESULT</span></span>|<span data-ttu-id="f6f04-113">説明</span><span class="sxs-lookup"><span data-stu-id="f6f04-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="f6f04-114">`EnumGenericParams`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="f6f04-114">`EnumGenericParams` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="f6f04-115">`phEnum`メンバー要素がありません。</span><span class="sxs-lookup"><span data-stu-id="f6f04-115">`phEnum` has no member elements.</span></span> <span data-ttu-id="f6f04-116">この場合、0(`pcGenericParams`ゼロ)に設定されます。</span><span class="sxs-lookup"><span data-stu-id="f6f04-116">In this case, `pcGenericParams` is set to 0 (zero).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f6f04-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="f6f04-117">Requirements</span></span>  
 <span data-ttu-id="f6f04-118">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f6f04-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6f04-119">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="f6f04-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f6f04-120">**ライブラリ:** MsCorEE.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="f6f04-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f6f04-121">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f6f04-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6f04-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="f6f04-122">See also</span></span>

- [<span data-ttu-id="f6f04-123">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f6f04-123">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [<span data-ttu-id="f6f04-124">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f6f04-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
