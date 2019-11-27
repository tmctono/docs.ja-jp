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
ms.openlocfilehash: 4fed7dbe4ec8343a3854d1f277e3228b14c0bf21
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450026"
---
# <a name="imetadataimportenumproperties-method"></a><span data-ttu-id="6121b-102">IMetaDataImport::EnumProperties メソッド</span><span class="sxs-lookup"><span data-stu-id="6121b-102">IMetaDataImport::EnumProperties Method</span></span>
<span data-ttu-id="6121b-103">指定した TypeDef トークンによって参照される型のプロパティを表す PropertyDef トークンを列挙します。</span><span class="sxs-lookup"><span data-stu-id="6121b-103">Enumerates PropertyDef tokens representing the properties of the type referenced by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6121b-104">構文</span><span class="sxs-lookup"><span data-stu-id="6121b-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumProperties (  
   [in, out] HCORENUM    *phEnum,  
   [in]      mdTypeDef   td,  
   [out]     mdProperty  rProperties[],  
   [in]      ULONG       cMax,  
   [out]     ULONG       *pcProperties  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6121b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6121b-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="6121b-106">[入力、出力]列挙子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="6121b-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="6121b-107">このメソッドの最初の呼び出しでは、この値は NULL である必要があります。</span><span class="sxs-lookup"><span data-stu-id="6121b-107">This must be NULL for the first call of this method.</span></span>  
  
 `td`  
 <span data-ttu-id="6121b-108">から列挙するプロパティを持つ型を表す TypeDef トークン。</span><span class="sxs-lookup"><span data-stu-id="6121b-108">[in] A TypeDef token representing the type with properties to enumerate.</span></span>  
  
 `rProperties`  
 <span data-ttu-id="6121b-109">入出力PropertyDef トークンを格納するために使用される配列。</span><span class="sxs-lookup"><span data-stu-id="6121b-109">[out] The array used to store the PropertyDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="6121b-110">[in] `rProperties` 配列の最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="6121b-110">[in] The maximum size of the `rProperties` array.</span></span>  
  
 `pcProperties`  
 <span data-ttu-id="6121b-111">入出力`rProperties`で返された PropertyDef トークンの数。</span><span class="sxs-lookup"><span data-stu-id="6121b-111">[out] The number of PropertyDef tokens returned in `rProperties`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6121b-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="6121b-112">Return Value</span></span>  
  
|<span data-ttu-id="6121b-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6121b-113">HRESULT</span></span>|<span data-ttu-id="6121b-114">説明</span><span class="sxs-lookup"><span data-stu-id="6121b-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="6121b-115">`EnumProperties` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="6121b-115">`EnumProperties` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="6121b-116">列挙するトークンがありません。</span><span class="sxs-lookup"><span data-stu-id="6121b-116">There are no tokens to enumerate.</span></span> <span data-ttu-id="6121b-117">この場合、`pcProperties` は0になります。</span><span class="sxs-lookup"><span data-stu-id="6121b-117">In that case, `pcProperties` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6121b-118">要件</span><span class="sxs-lookup"><span data-stu-id="6121b-118">Requirements</span></span>  
 <span data-ttu-id="6121b-119">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6121b-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6121b-120">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="6121b-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6121b-121">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="6121b-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6121b-122">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6121b-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6121b-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="6121b-123">See also</span></span>

- [<span data-ttu-id="6121b-124">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6121b-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="6121b-125">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6121b-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
