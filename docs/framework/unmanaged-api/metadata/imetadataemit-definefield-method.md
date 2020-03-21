---
title: IMetaDataEmit::DefineField メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineField
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineField
helpviewer_keywords:
- IMetaDataEmit::DefineField method [.NET Framework metadata]
- DefineField method, IMetaDataEmit interface [.NET Framework metadata
ms.assetid: 6b5be4fc-2e86-499c-8b09-833160bca767
topic_type:
- apiref
ms.openlocfilehash: 8ca5ab70f60de4d783800fb18612a8f04cb9cee1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177715"
---
# <a name="imetadataemitdefinefield-method"></a><span data-ttu-id="3b4a4-102">IMetaDataEmit::DefineField メソッド</span><span class="sxs-lookup"><span data-stu-id="3b4a4-102">IMetaDataEmit::DefineField Method</span></span>
<span data-ttu-id="3b4a4-103">指定したメタデータ シグネチャを持つフィールドの定義を作成し、そのフィールド定義へのトークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="3b4a4-103">Creates a definition for a field with the specified metadata signature, and gets a token to that field definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b4a4-104">構文</span><span class="sxs-lookup"><span data-stu-id="3b4a4-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineField (
    [in]  mdTypeDef   td,
    [in]  LPCWSTR     szName,
    [in]  DWORD       dwFieldFlags,
    [in]  PCCOR_SIGNATURE pvSigBlob,
    [in]  ULONG       cbSigBlob,
    [in]  DWORD       dwCPlusTypeFlag,
    [in]  void const  *pValue,
    [in]  ULONG       cchValue,
    [out] mdFieldDef  *pmd
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3b4a4-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3b4a4-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="3b4a4-106">[in]外側`mdTypeDef`のクラスまたはインターフェイスのトークン。</span><span class="sxs-lookup"><span data-stu-id="3b4a4-106">[in] The `mdTypeDef` token for the enclosing class or interface.</span></span>  
  
 `szName`  
 <span data-ttu-id="3b4a4-107">[in]ユニコードのフィールド名。</span><span class="sxs-lookup"><span data-stu-id="3b4a4-107">[in] The field name in Unicode.</span></span>  
  
 `dwFieldFlags`  
 <span data-ttu-id="3b4a4-108">[in]フィールド属性。</span><span class="sxs-lookup"><span data-stu-id="3b4a4-108">[in] The field attributes.</span></span> <span data-ttu-id="3b4a4-109">これは値の`CorFieldAttr`ビットマスクです。</span><span class="sxs-lookup"><span data-stu-id="3b4a4-109">This is a bitmask of `CorFieldAttr` values.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="3b4a4-110">[in]BLOB としてのフィールド シグネチャ。</span><span class="sxs-lookup"><span data-stu-id="3b4a4-110">[in] The field signature as a BLOB.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="3b4a4-111">[in]のバイト数`pvSigBlob`。</span><span class="sxs-lookup"><span data-stu-id="3b4a4-111">[in] The count of bytes in `pvSigBlob`.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="3b4a4-112">[in]`ELEMENT_TYPE_`*\** 定数値の場合。</span><span class="sxs-lookup"><span data-stu-id="3b4a4-112">[in] The `ELEMENT_TYPE_`*\** for the constant value.</span></span> <span data-ttu-id="3b4a4-113">これは値です`CorElementType`。</span><span class="sxs-lookup"><span data-stu-id="3b4a4-113">This is a `CorElementType` value.</span></span> <span data-ttu-id="3b4a4-114">フィールドの定数値を定義しない場合は、 を`ELEMENT_TYPE_END`使用します。</span><span class="sxs-lookup"><span data-stu-id="3b4a4-114">If not defining a constant value for the field, use `ELEMENT_TYPE_END`.</span></span>  
  
 `pValue`  
 <span data-ttu-id="3b4a4-115">[in]フィールドの定数値。</span><span class="sxs-lookup"><span data-stu-id="3b4a4-115">[in] The constant value for the field.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="3b4a4-116">[in]のサイズ (Unicode) 文字`pValue`</span><span class="sxs-lookup"><span data-stu-id="3b4a4-116">[in] The size in (Unicode) characters of `pValue`.</span></span>  
  
 `pmd`  
 <span data-ttu-id="3b4a4-117">[アウト]割`mdFieldDef`り当てられたトークン。</span><span class="sxs-lookup"><span data-stu-id="3b4a4-117">[out] The `mdFieldDef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b4a4-118">必要条件</span><span class="sxs-lookup"><span data-stu-id="3b4a4-118">Requirements</span></span>  
 <span data-ttu-id="3b4a4-119">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3b4a4-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b4a4-120">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="3b4a4-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3b4a4-121">**ライブラリ:** MSCorEE.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="3b4a4-121">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3b4a4-122">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3b4a4-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b4a4-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="3b4a4-123">See also</span></span>

- [<span data-ttu-id="3b4a4-124">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3b4a4-124">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="3b4a4-125">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3b4a4-125">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
