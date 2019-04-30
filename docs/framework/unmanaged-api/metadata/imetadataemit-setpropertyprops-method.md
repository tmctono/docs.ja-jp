---
title: IMetaDataEmit::SetPropertyProps メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetPropertyProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetPropertyProps
helpviewer_keywords:
- SetPropertyProps method [.NET Framework metadata]
- IMetaDataEmit::SetPropertyProps method [.NET Framework metadata]
ms.assetid: e2501fc8-b2bc-4dcc-9205-e3acd5a53ffe
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fdee8491b22675fb8dd8fa89e77ebf8541185173
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62043746"
---
# <a name="imetadataemitsetpropertyprops-method"></a><span data-ttu-id="74ddb-102">IMetaDataEmit::SetPropertyProps メソッド</span><span class="sxs-lookup"><span data-stu-id="74ddb-102">IMetaDataEmit::SetPropertyProps Method</span></span>
<span data-ttu-id="74ddb-103">前回の呼び出しによって定義されるプロパティのメタデータに格納されている機能の設定[DefineProperty メソッド](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="74ddb-103">Sets the features stored in metadata for a property defined by a prior call to [DefineProperty Method](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74ddb-104">構文</span><span class="sxs-lookup"><span data-stu-id="74ddb-104">Syntax</span></span>  
  
```  
HRESULT SetPropertyProps (   
    [in]  mdProperty      pr,   
    [in]  DWORD           dwPropFlags,   
    [in]  DWORD           dwCPlusTypeFlag,   
    [in]  void const      *pValue,   
    [in]  ULONG           cchValue,   
    [in]  mdMethodDef     mdSetter,   
    [in]  mdMethodDef     mdGetter,   
    [in]  mdMethodDef     rmdOtherMethods[]   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="74ddb-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="74ddb-105">Parameters</span></span>  
 `pr`  
 <span data-ttu-id="74ddb-106">[in]変更するプロパティのトークン</span><span class="sxs-lookup"><span data-stu-id="74ddb-106">[in] The token for the property to be changed</span></span>  
  
 `dwPropFlags`  
 <span data-ttu-id="74ddb-107">[in]プロパティのフラグ。</span><span class="sxs-lookup"><span data-stu-id="74ddb-107">[in] Property flags.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="74ddb-108">[in]プロパティの既定値の型。</span><span class="sxs-lookup"><span data-stu-id="74ddb-108">[in] The type of the property's default value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="74ddb-109">[in]プロパティの既定値。</span><span class="sxs-lookup"><span data-stu-id="74ddb-109">[in] The default value for the property.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="74ddb-110">[in] \(Unicode) の数の文字について`pValue`です。</span><span class="sxs-lookup"><span data-stu-id="74ddb-110">[in] The count of (Unicode) characters in `pValue`.</span></span>  
  
 `mdSetter`  
 <span data-ttu-id="74ddb-111">[in]このメソッドは、プロパティ値を設定します。</span><span class="sxs-lookup"><span data-stu-id="74ddb-111">[in] The method that sets the property value.</span></span>  
  
 `mdGetter`  
 <span data-ttu-id="74ddb-112">[in]このメソッドは、プロパティ値を取得します。</span><span class="sxs-lookup"><span data-stu-id="74ddb-112">[in] The method that gets the property value.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="74ddb-113">[in]プロパティに関連付けられているその他のメソッドの配列。</span><span class="sxs-lookup"><span data-stu-id="74ddb-113">[in] An array of other methods associated with the property.</span></span> <span data-ttu-id="74ddb-114">この配列を`mdTokenNil`トークンです。</span><span class="sxs-lookup"><span data-stu-id="74ddb-114">Terminate this array with an `mdTokenNil` token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74ddb-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="74ddb-115">Requirements</span></span>  
 <span data-ttu-id="74ddb-116">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="74ddb-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74ddb-117">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="74ddb-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="74ddb-118">**ライブラリ:** MSCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="74ddb-118">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="74ddb-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74ddb-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74ddb-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="74ddb-120">See also</span></span>

- [<span data-ttu-id="74ddb-121">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="74ddb-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="74ddb-122">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="74ddb-122">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
