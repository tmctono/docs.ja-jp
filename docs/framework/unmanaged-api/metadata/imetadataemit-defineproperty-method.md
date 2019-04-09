---
title: IMetaDataEmit::DefineProperty メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineProperty
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineProperty
helpviewer_keywords:
- IMetaDataEmit::DefineProperty method [.NET Framework metadata]
- DefineProperty method [.NET Framework metadata]
ms.assetid: 5c4c1dc2-d40d-4173-bbe6-7058fb21c98f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1b80833892fc1c0290e94f5de7d9b081529c6a37
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59085026"
---
# <a name="imetadataemitdefineproperty-method"></a><span data-ttu-id="3742d-102">IMetaDataEmit::DefineProperty メソッド</span><span class="sxs-lookup"><span data-stu-id="3742d-102">IMetaDataEmit::DefineProperty Method</span></span>
<span data-ttu-id="3742d-103">指定して、指定した型のプロパティの定義を作成します。`get`と`set`メソッド アクセサー、およびそのプロパティの定義にトークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="3742d-103">Creates a property definition for the specified type, with the specified `get` and `set` method accessors, and gets a token to that property definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3742d-104">構文</span><span class="sxs-lookup"><span data-stu-id="3742d-104">Syntax</span></span>  
  
```  
HRESULT DefineProperty (   
    [in]  mdTypeDef          td,   
    [in]  LPCWSTR            szProperty,   
    [in]  DWORD              dwPropFlags,   
    [in]  PCCOR_SIGNATURE    pvSig,   
    [in]  ULONG              cbSig,   
    [in]  DWORD              dwCPlusTypeFlag,   
    [in]  void const         *pValue,   
    [in]  ULONG              cchValue,   
    [in]  mdMethodDef        mdSetter,   
    [in]  mdMethodDef        mdGetter,   
    [in]  mdMethodDef        rmdOtherMethods[],   
    [out] mdProperty         *pmdProp   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3742d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3742d-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="3742d-106">[in]クラスまたはインターフェイスのプロパティを定義するトークンです。</span><span class="sxs-lookup"><span data-stu-id="3742d-106">[in] The token for class or interface on which the property is being defined.</span></span>  
  
 `szProperty`  
 <span data-ttu-id="3742d-107">[in]プロパティの名前。</span><span class="sxs-lookup"><span data-stu-id="3742d-107">[in] The name of the property.</span></span>  
  
 `dwPropFlags`  
 <span data-ttu-id="3742d-108">[in]プロパティのフラグ。</span><span class="sxs-lookup"><span data-stu-id="3742d-108">[in] The property flags.</span></span>  
  
 `pvSig`  
 <span data-ttu-id="3742d-109">[in]プロパティ シグネチャ。</span><span class="sxs-lookup"><span data-stu-id="3742d-109">[in] The property signature.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="3742d-110">[in]内のバイト数`pvSig`します。</span><span class="sxs-lookup"><span data-stu-id="3742d-110">[in] The count of bytes in `pvSig`.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="3742d-111">[in]プロパティの既定値の型。</span><span class="sxs-lookup"><span data-stu-id="3742d-111">[in] The type of the property's default value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="3742d-112">[in]プロパティの既定値。</span><span class="sxs-lookup"><span data-stu-id="3742d-112">[in] The default value for the property.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="3742d-113">[in] \(Unicode) の数の文字について`pValue`です。</span><span class="sxs-lookup"><span data-stu-id="3742d-113">[in] The count of (Unicode) characters in `pValue`.</span></span>  
  
 `mdSetter`  
 <span data-ttu-id="3742d-114">[in]このメソッドは、プロパティ値を設定します。</span><span class="sxs-lookup"><span data-stu-id="3742d-114">[in] The method that sets the property value.</span></span>  
  
 `mdGetter`  
 <span data-ttu-id="3742d-115">[in]このメソッドは、プロパティ値を取得します。</span><span class="sxs-lookup"><span data-stu-id="3742d-115">[in] The method that gets the property value.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="3742d-116">[in]プロパティに関連付けられているその他のメソッドの配列。</span><span class="sxs-lookup"><span data-stu-id="3742d-116">[in] An array of other methods associated with the property.</span></span> <span data-ttu-id="3742d-117">終了、配列、`mdTokenNil`します。</span><span class="sxs-lookup"><span data-stu-id="3742d-117">Terminate the array with an `mdTokenNil`.</span></span>  
  
 `pmdProp`  
 <span data-ttu-id="3742d-118">[out]`mdProperty`に割り当てられたトークン。</span><span class="sxs-lookup"><span data-stu-id="3742d-118">[out] The `mdProperty` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3742d-119">必要条件</span><span class="sxs-lookup"><span data-stu-id="3742d-119">Requirements</span></span>  
 <span data-ttu-id="3742d-120">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3742d-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3742d-121">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="3742d-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3742d-122">**ライブラリ:** MSCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="3742d-122">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="3742d-123">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="3742d-123">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3742d-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="3742d-124">See also</span></span>

- [<span data-ttu-id="3742d-125">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3742d-125">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="3742d-126">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3742d-126">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
