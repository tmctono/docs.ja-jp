---
title: IMetaDataImport2::EnumMethodSpecs メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.EnumMethodSpecs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::EnumMethodSpecs
helpviewer_keywords:
- IMetaDataImport2::EnumMethodSpecs method [.NET Framework metadata]
- EnumMethodSpecs method [.NET Framework metadata]
ms.assetid: b3fc1e6c-bcb6-4915-baf8-7dc0a31b8724
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a3641fcda33a497293dbf87b419c8606847dc296
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59130950"
---
# <a name="imetadataimport2enummethodspecs-method"></a><span data-ttu-id="72254-102">IMetaDataImport2::EnumMethodSpecs メソッド</span><span class="sxs-lookup"><span data-stu-id="72254-102">IMetaDataImport2::EnumMethodSpecs Method</span></span>
<span data-ttu-id="72254-103">トークンに関連付けられた、指定した MethodDef または MemberRef MethodSpec トークンの配列の列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="72254-103">Gets an enumerator for an array of MethodSpec tokens associated with the specified MethodDef or MemberRef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72254-104">構文</span><span class="sxs-lookup"><span data-stu-id="72254-104">Syntax</span></span>  
  
```  
HRESULT EnumMethodSpecs (  
    [in, out] HCORENUM      *phEnum,   
    [in]      mdToken       tk,  
    [out]     mdMethodSpec  rMethodSpecs[],  
    [in]      ULONG         cMax,  
    [out]     ULONG         *pcMethodSpecs  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="72254-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="72254-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="72254-106">[入力、出力]列挙子へのポインター`rMethodSpecs`します。</span><span class="sxs-lookup"><span data-stu-id="72254-106">[in, out] A pointer to the enumerator for `rMethodSpecs`.</span></span>  
  
 `tk`  
 <span data-ttu-id="72254-107">[in]MethodSpec トークンが列挙メソッドを表す MemberRef または MethodDef トークンです。</span><span class="sxs-lookup"><span data-stu-id="72254-107">[in] The MemberRef or MethodDef token that represents the method whose MethodSpec tokens are to be enumerated.</span></span> <span data-ttu-id="72254-108">場合の値`tk`0 (ゼロ) には、スコープ内のすべての MethodSpec トークンが列挙されます。</span><span class="sxs-lookup"><span data-stu-id="72254-108">If the value of `tk` is 0 (zero), all MethodSpec tokens in the scope will be enumerated.</span></span>  
  
 `rMethodSpecs`  
 <span data-ttu-id="72254-109">[out]列挙する MethodSpec トークンの配列。</span><span class="sxs-lookup"><span data-stu-id="72254-109">[out] The array of MethodSpec tokens to enumerate.</span></span>  
  
 `cMax`  
 <span data-ttu-id="72254-110">[in]配置するトークンの要求の最大数`rMethodSpecs`します。</span><span class="sxs-lookup"><span data-stu-id="72254-110">[in] The requested maximum number of tokens to place in `rMethodSpecs`.</span></span>  
  
 `pcMethodSpecs`  
 <span data-ttu-id="72254-111">[out]返されたトークンの数に配置`rMethodSpecs`します。</span><span class="sxs-lookup"><span data-stu-id="72254-111">[out] The returned number of tokens placed in `rMethodSpecs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="72254-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="72254-112">Return Value</span></span>  
  
|<span data-ttu-id="72254-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="72254-113">HRESULT</span></span>|<span data-ttu-id="72254-114">説明</span><span class="sxs-lookup"><span data-stu-id="72254-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|`EnumMethodSpecs` <span data-ttu-id="72254-115">正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="72254-115">returned successfully.</span></span>|  
|`S_FALSE`|`phEnum` <span data-ttu-id="72254-116">メンバーの要素がありません。</span><span class="sxs-lookup"><span data-stu-id="72254-116">has no member elements.</span></span> <span data-ttu-id="72254-117">この場合、 `pcMethodSpecs` 0 (ゼロ) に設定されます。</span><span class="sxs-lookup"><span data-stu-id="72254-117">In this case, `pcMethodSpecs` is set to 0 (zero).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="72254-118">必要条件</span><span class="sxs-lookup"><span data-stu-id="72254-118">Requirements</span></span>  
 <span data-ttu-id="72254-119">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="72254-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72254-120">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="72254-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="72254-121">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="72254-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="72254-122">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="72254-122">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="72254-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="72254-123">See also</span></span>

- [<span data-ttu-id="72254-124">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="72254-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [<span data-ttu-id="72254-125">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="72254-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
