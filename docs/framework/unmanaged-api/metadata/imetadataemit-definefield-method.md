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
ms.openlocfilehash: 40f24a4ea628ce92a27ab1bfe97fc87a57dfa4f0
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74432548"
---
# <a name="imetadataemitdefinefield-method"></a><span data-ttu-id="ce30d-102">IMetaDataEmit::DefineField メソッド</span><span class="sxs-lookup"><span data-stu-id="ce30d-102">IMetaDataEmit::DefineField Method</span></span>
<span data-ttu-id="ce30d-103">指定したメタデータシグネチャを持つフィールドの定義を作成し、そのフィールド定義へのトークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="ce30d-103">Creates a definition for a field with the specified metadata signature, and gets a token to that field definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce30d-104">構文</span><span class="sxs-lookup"><span data-stu-id="ce30d-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="ce30d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ce30d-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="ce30d-106">から外側のクラスまたはインターフェイスの `mdTypeDef` トークン。</span><span class="sxs-lookup"><span data-stu-id="ce30d-106">[in] The `mdTypeDef` token for the enclosing class or interface.</span></span>  
  
 `szName`  
 <span data-ttu-id="ce30d-107">からUnicode でのフィールド名。</span><span class="sxs-lookup"><span data-stu-id="ce30d-107">[in] The field name in Unicode.</span></span>  
  
 `dwFieldFlags`  
 <span data-ttu-id="ce30d-108">からフィールド属性。</span><span class="sxs-lookup"><span data-stu-id="ce30d-108">[in] The field attributes.</span></span> <span data-ttu-id="ce30d-109">これは `CorFieldAttr` 値のビットマスクです。</span><span class="sxs-lookup"><span data-stu-id="ce30d-109">This is a bitmask of `CorFieldAttr` values.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="ce30d-110">からBLOB としてのフィールドシグネチャ。</span><span class="sxs-lookup"><span data-stu-id="ce30d-110">[in] The field signature as a BLOB.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="ce30d-111">から`pvSigBlob`内のバイト数。</span><span class="sxs-lookup"><span data-stu-id="ce30d-111">[in] The count of bytes in `pvSigBlob`.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="ce30d-112">から定数値の `ELEMENT_TYPE_` *\** 。</span><span class="sxs-lookup"><span data-stu-id="ce30d-112">[in] The `ELEMENT_TYPE_`*\** for the constant value.</span></span> <span data-ttu-id="ce30d-113">これは `CorElementType` の値です。</span><span class="sxs-lookup"><span data-stu-id="ce30d-113">This is a `CorElementType` value.</span></span> <span data-ttu-id="ce30d-114">フィールドの定数値を定義していない場合は、`ELEMENT_TYPE_END`を使用します。</span><span class="sxs-lookup"><span data-stu-id="ce30d-114">If not defining a constant value for the field, use `ELEMENT_TYPE_END`.</span></span>  
  
 `pValue`  
 <span data-ttu-id="ce30d-115">からフィールドの定数値。</span><span class="sxs-lookup"><span data-stu-id="ce30d-115">[in] The constant value for the field.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="ce30d-116">から`pValue`の (Unicode) 文字のサイズ。</span><span class="sxs-lookup"><span data-stu-id="ce30d-116">[in] The size in (Unicode) characters of `pValue`.</span></span>  
  
 `pmd`  
 <span data-ttu-id="ce30d-117">入出力割り当てられた `mdFieldDef` トークン。</span><span class="sxs-lookup"><span data-stu-id="ce30d-117">[out] The `mdFieldDef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce30d-118">要件</span><span class="sxs-lookup"><span data-stu-id="ce30d-118">Requirements</span></span>  
 <span data-ttu-id="ce30d-119">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ce30d-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce30d-120">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="ce30d-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ce30d-121">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="ce30d-121">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ce30d-122">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce30d-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce30d-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="ce30d-123">See also</span></span>

- [<span data-ttu-id="ce30d-124">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ce30d-124">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="ce30d-125">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ce30d-125">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
