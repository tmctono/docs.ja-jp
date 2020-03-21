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
ms.openlocfilehash: dc6375f3e2cff1a744a8ff2e6a6adab27bbf8af3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177473"
---
# <a name="imetadataemitsetpropertyprops-method"></a><span data-ttu-id="fb198-102">IMetaDataEmit::SetPropertyProps メソッド</span><span class="sxs-lookup"><span data-stu-id="fb198-102">IMetaDataEmit::SetPropertyProps Method</span></span>
<span data-ttu-id="fb198-103">[DefineProperty メソッド](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md)の前の呼び出しによって定義されたプロパティのメタデータに格納されているフィーチャを設定します。</span><span class="sxs-lookup"><span data-stu-id="fb198-103">Sets the features stored in metadata for a property defined by a prior call to [DefineProperty Method](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb198-104">構文</span><span class="sxs-lookup"><span data-stu-id="fb198-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="fb198-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="fb198-105">Parameters</span></span>  
 `pr`  
 <span data-ttu-id="fb198-106">[in]変更するプロパティのトークン</span><span class="sxs-lookup"><span data-stu-id="fb198-106">[in] The token for the property to be changed</span></span>  
  
 `dwPropFlags`  
 <span data-ttu-id="fb198-107">[in]プロパティ フラグ。</span><span class="sxs-lookup"><span data-stu-id="fb198-107">[in] Property flags.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="fb198-108">[in]プロパティの既定値の型。</span><span class="sxs-lookup"><span data-stu-id="fb198-108">[in] The type of the property's default value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="fb198-109">[in]プロパティの既定値。</span><span class="sxs-lookup"><span data-stu-id="fb198-109">[in] The default value for the property.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="fb198-110">[in]の (Unicode) 文字の`pValue`数。</span><span class="sxs-lookup"><span data-stu-id="fb198-110">[in] The count of (Unicode) characters in `pValue`.</span></span>  
  
 `mdSetter`  
 <span data-ttu-id="fb198-111">[in]プロパティ値を設定するメソッド。</span><span class="sxs-lookup"><span data-stu-id="fb198-111">[in] The method that sets the property value.</span></span>  
  
 `mdGetter`  
 <span data-ttu-id="fb198-112">[in]プロパティ値を取得するメソッド。</span><span class="sxs-lookup"><span data-stu-id="fb198-112">[in] The method that gets the property value.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="fb198-113">[in]プロパティに関連付けられている他のメソッドの配列。</span><span class="sxs-lookup"><span data-stu-id="fb198-113">[in] An array of other methods associated with the property.</span></span> <span data-ttu-id="fb198-114">この配列をトークンで`mdTokenNil`終了します。</span><span class="sxs-lookup"><span data-stu-id="fb198-114">Terminate this array with an `mdTokenNil` token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb198-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="fb198-115">Requirements</span></span>  
 <span data-ttu-id="fb198-116">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb198-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb198-117">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="fb198-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fb198-118">**ライブラリ:** MSCorEE.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="fb198-118">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fb198-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fb198-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb198-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="fb198-120">See also</span></span>

- [<span data-ttu-id="fb198-121">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fb198-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="fb198-122">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fb198-122">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
