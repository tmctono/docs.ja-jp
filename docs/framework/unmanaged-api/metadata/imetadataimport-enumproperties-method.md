---
title: IMetaDataImport::EnumProperties メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumProperties
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumProperties
helpviewer_keywords:
- IMetaDataImport::EnumProperties method [.NET Framework metadata]
- EnumProperties method [.NET Framework metadata]
ms.assetid: 60573ad7-8821-4721-a068-3f7a6d25926a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 410fd7a702d3aa3812b4ea053c43fdaa507a474a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62042511"
---
# <a name="imetadataimportenumproperties-method"></a><span data-ttu-id="cf7f4-102">IMetaDataImport::EnumProperties メソッド</span><span class="sxs-lookup"><span data-stu-id="cf7f4-102">IMetaDataImport::EnumProperties Method</span></span>
<span data-ttu-id="cf7f4-103">指定した TypeDef トークンによって参照される型のプロパティを表す PropertyDef トークンを列挙します。</span><span class="sxs-lookup"><span data-stu-id="cf7f4-103">Enumerates PropertyDef tokens representing the properties of the type referenced by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf7f4-104">構文</span><span class="sxs-lookup"><span data-stu-id="cf7f4-104">Syntax</span></span>  
  
```  
HRESULT EnumProperties (  
   [in, out] HCORENUM    *phEnum,  
   [in]      mdTypeDef   td,  
   [out]     mdProperty  rProperties[],  
   [in]      ULONG       cMax,  
   [out]     ULONG       *pcProperties  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cf7f4-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="cf7f4-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="cf7f4-106">[入力、出力]列挙子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="cf7f4-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="cf7f4-107">このメソッドの最初の呼び出しで NULL があります。</span><span class="sxs-lookup"><span data-stu-id="cf7f4-107">This must be NULL for the first call of this method.</span></span>  
  
 `td`  
 <span data-ttu-id="cf7f4-108">[in]プロパティを持つ列挙型を表す TypeDef トークンです。</span><span class="sxs-lookup"><span data-stu-id="cf7f4-108">[in] A TypeDef token representing the type with properties to enumerate.</span></span>  
  
 `rProperties`  
 <span data-ttu-id="cf7f4-109">[out]PropertyDef トークンを格納するために使用する配列。</span><span class="sxs-lookup"><span data-stu-id="cf7f4-109">[out] The array used to store the PropertyDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="cf7f4-110">[in] `rProperties` 配列の最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="cf7f4-110">[in] The maximum size of the `rProperties` array.</span></span>  
  
 `pcProperties`  
 <span data-ttu-id="cf7f4-111">[out]返される PropertyDef トークン数`rProperties`します。</span><span class="sxs-lookup"><span data-stu-id="cf7f4-111">[out] The number of PropertyDef tokens returned in `rProperties`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cf7f4-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="cf7f4-112">Return Value</span></span>  
  
|<span data-ttu-id="cf7f4-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="cf7f4-113">HRESULT</span></span>|<span data-ttu-id="cf7f4-114">説明</span><span class="sxs-lookup"><span data-stu-id="cf7f4-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="cf7f4-115">`EnumProperties` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="cf7f4-115">`EnumProperties` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="cf7f4-116">トークンを列挙することはありません。</span><span class="sxs-lookup"><span data-stu-id="cf7f4-116">There are no tokens to enumerate.</span></span> <span data-ttu-id="cf7f4-117">その場合は、`pcProperties`は 0 です。</span><span class="sxs-lookup"><span data-stu-id="cf7f4-117">In that case, `pcProperties` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cf7f4-118">必要条件</span><span class="sxs-lookup"><span data-stu-id="cf7f4-118">Requirements</span></span>  
 <span data-ttu-id="cf7f4-119">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cf7f4-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf7f4-120">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="cf7f4-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cf7f4-121">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="cf7f4-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="cf7f4-122">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf7f4-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf7f4-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="cf7f4-123">See also</span></span>

- [<span data-ttu-id="cf7f4-124">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cf7f4-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="cf7f4-125">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cf7f4-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
