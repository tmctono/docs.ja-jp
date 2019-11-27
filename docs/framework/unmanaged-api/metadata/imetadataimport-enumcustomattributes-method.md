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
ms.openlocfilehash: a43c1883038e41cac1b58c78bc26f20d436ebbd1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440236"
---
# <a name="imetadataimportenumcustomattributes-method"></a><span data-ttu-id="21b3f-102">IMetaDataImport::EnumCustomAttributes メソッド</span><span class="sxs-lookup"><span data-stu-id="21b3f-102">IMetaDataImport::EnumCustomAttributes Method</span></span>
<span data-ttu-id="21b3f-103">指定した型またはメンバーに関連付けられているカスタム属性定義トークンを列挙します。</span><span class="sxs-lookup"><span data-stu-id="21b3f-103">Enumerates custom attribute-definition tokens associated with the specified type or member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21b3f-104">構文</span><span class="sxs-lookup"><span data-stu-id="21b3f-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="21b3f-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="21b3f-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="21b3f-106">[入力、出力]返された列挙子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="21b3f-106">[in, out] A pointer to the returned enumerator.</span></span>  
  
 `tk`  
 <span data-ttu-id="21b3f-107">から列挙体のスコープのトークン、またはすべてのカスタム属性の0。</span><span class="sxs-lookup"><span data-stu-id="21b3f-107">[in] A token for the scope of the enumeration, or zero for all custom attributes.</span></span>  
  
 `tkType`  
 <span data-ttu-id="21b3f-108">から列挙する属性の型のコンストラクターのトークン、またはすべての型の `null`。</span><span class="sxs-lookup"><span data-stu-id="21b3f-108">[in] A token for the constructor of the type of the attributes to be enumerated, or `null` for all types.</span></span>  
  
 `rCustomAttributes`  
 <span data-ttu-id="21b3f-109">入出力カスタム属性トークンの配列。</span><span class="sxs-lookup"><span data-stu-id="21b3f-109">[out] An array of custom attribute tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="21b3f-110">[in] `rCustomAttributes` 配列の最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="21b3f-110">[in] The maximum size of the `rCustomAttributes` array.</span></span>  
  
 `pcCustomAttributes`  
 <span data-ttu-id="21b3f-111">[out、省略可能]`rCustomAttributes`で返されるトークン値の実際の数。</span><span class="sxs-lookup"><span data-stu-id="21b3f-111">[out, optional] The actual number of token values returned in `rCustomAttributes`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="21b3f-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="21b3f-112">Return Value</span></span>  
  
|<span data-ttu-id="21b3f-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="21b3f-113">HRESULT</span></span>|<span data-ttu-id="21b3f-114">説明</span><span class="sxs-lookup"><span data-stu-id="21b3f-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="21b3f-115">`EnumCustomAttributes` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="21b3f-115">`EnumCustomAttributes` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="21b3f-116">列挙するカスタム属性はありません。</span><span class="sxs-lookup"><span data-stu-id="21b3f-116">There are no custom attributes to enumerate.</span></span> <span data-ttu-id="21b3f-117">この場合、`pcCustomAttributes` は0になります。</span><span class="sxs-lookup"><span data-stu-id="21b3f-117">In that case, `pcCustomAttributes` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="21b3f-118">要件</span><span class="sxs-lookup"><span data-stu-id="21b3f-118">Requirements</span></span>  
 <span data-ttu-id="21b3f-119">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="21b3f-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21b3f-120">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="21b3f-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="21b3f-121">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="21b3f-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="21b3f-122">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="21b3f-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21b3f-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="21b3f-123">See also</span></span>

- [<span data-ttu-id="21b3f-124">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="21b3f-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="21b3f-125">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="21b3f-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
