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
ms.openlocfilehash: b8cd086a86d104fdfebf1a8298a22b795cb2389b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782643"
---
# <a name="imetadataimport2enummethodspecs-method"></a><span data-ttu-id="d6108-102">IMetaDataImport2::EnumMethodSpecs メソッド</span><span class="sxs-lookup"><span data-stu-id="d6108-102">IMetaDataImport2::EnumMethodSpecs Method</span></span>
<span data-ttu-id="d6108-103">トークンに関連付けられた、指定した MethodDef または MemberRef MethodSpec トークンの配列の列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="d6108-103">Gets an enumerator for an array of MethodSpec tokens associated with the specified MethodDef or MemberRef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6108-104">構文</span><span class="sxs-lookup"><span data-stu-id="d6108-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMethodSpecs (  
    [in, out] HCORENUM      *phEnum,   
    [in]      mdToken       tk,  
    [out]     mdMethodSpec  rMethodSpecs[],  
    [in]      ULONG         cMax,  
    [out]     ULONG         *pcMethodSpecs  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="d6108-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d6108-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="d6108-106">[入力、出力]列挙子へのポインター`rMethodSpecs`します。</span><span class="sxs-lookup"><span data-stu-id="d6108-106">[in, out] A pointer to the enumerator for `rMethodSpecs`.</span></span>  
  
 `tk`  
 <span data-ttu-id="d6108-107">[in]MethodSpec トークンが列挙メソッドを表す MemberRef または MethodDef トークンです。</span><span class="sxs-lookup"><span data-stu-id="d6108-107">[in] The MemberRef or MethodDef token that represents the method whose MethodSpec tokens are to be enumerated.</span></span> <span data-ttu-id="d6108-108">場合の値`tk`0 (ゼロ) には、スコープ内のすべての MethodSpec トークンが列挙されます。</span><span class="sxs-lookup"><span data-stu-id="d6108-108">If the value of `tk` is 0 (zero), all MethodSpec tokens in the scope will be enumerated.</span></span>  
  
 `rMethodSpecs`  
 <span data-ttu-id="d6108-109">[out]列挙する MethodSpec トークンの配列。</span><span class="sxs-lookup"><span data-stu-id="d6108-109">[out] The array of MethodSpec tokens to enumerate.</span></span>  
  
 `cMax`  
 <span data-ttu-id="d6108-110">[in]配置するトークンの要求の最大数`rMethodSpecs`します。</span><span class="sxs-lookup"><span data-stu-id="d6108-110">[in] The requested maximum number of tokens to place in `rMethodSpecs`.</span></span>  
  
 `pcMethodSpecs`  
 <span data-ttu-id="d6108-111">[out]返されたトークンの数に配置`rMethodSpecs`します。</span><span class="sxs-lookup"><span data-stu-id="d6108-111">[out] The returned number of tokens placed in `rMethodSpecs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d6108-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="d6108-112">Return Value</span></span>  
  
|<span data-ttu-id="d6108-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d6108-113">HRESULT</span></span>|<span data-ttu-id="d6108-114">説明</span><span class="sxs-lookup"><span data-stu-id="d6108-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="d6108-115">`EnumMethodSpecs` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="d6108-115">`EnumMethodSpecs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="d6108-116">`phEnum` メンバーの要素がありません。</span><span class="sxs-lookup"><span data-stu-id="d6108-116">`phEnum` has no member elements.</span></span> <span data-ttu-id="d6108-117">この場合、 `pcMethodSpecs` 0 (ゼロ) に設定されます。</span><span class="sxs-lookup"><span data-stu-id="d6108-117">In this case, `pcMethodSpecs` is set to 0 (zero).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d6108-118">必要条件</span><span class="sxs-lookup"><span data-stu-id="d6108-118">Requirements</span></span>  
 <span data-ttu-id="d6108-119">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d6108-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6108-120">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d6108-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d6108-121">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="d6108-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d6108-122">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d6108-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6108-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="d6108-123">See also</span></span>

- [<span data-ttu-id="d6108-124">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d6108-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [<span data-ttu-id="d6108-125">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d6108-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
