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
ms.openlocfilehash: ccc4843864f375c167acdb12575c282dbe3a49e1
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "84004817"
---
# <a name="imetadataemitdefinefield-method"></a><span data-ttu-id="4e043-102">IMetaDataEmit::DefineField メソッド</span><span class="sxs-lookup"><span data-stu-id="4e043-102">IMetaDataEmit::DefineField Method</span></span>
<span data-ttu-id="4e043-103">指定したメタデータシグネチャを持つフィールドの定義を作成し、そのフィールド定義へのトークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="4e043-103">Creates a definition for a field with the specified metadata signature, and gets a token to that field definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e043-104">構文</span><span class="sxs-lookup"><span data-stu-id="4e043-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="4e043-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4e043-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="4e043-106">から`mdTypeDef`外側のクラスまたはインターフェイスのトークン。</span><span class="sxs-lookup"><span data-stu-id="4e043-106">[in] The `mdTypeDef` token for the enclosing class or interface.</span></span>  
  
 `szName`  
 <span data-ttu-id="4e043-107">からUnicode でのフィールド名。</span><span class="sxs-lookup"><span data-stu-id="4e043-107">[in] The field name in Unicode.</span></span>  
  
 `dwFieldFlags`  
 <span data-ttu-id="4e043-108">からフィールド属性。</span><span class="sxs-lookup"><span data-stu-id="4e043-108">[in] The field attributes.</span></span> <span data-ttu-id="4e043-109">これは、値のビットマスクです `CorFieldAttr` 。</span><span class="sxs-lookup"><span data-stu-id="4e043-109">This is a bitmask of `CorFieldAttr` values.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="4e043-110">からBLOB としてのフィールドシグネチャ。</span><span class="sxs-lookup"><span data-stu-id="4e043-110">[in] The field signature as a BLOB.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="4e043-111">からのバイト数 `pvSigBlob` 。</span><span class="sxs-lookup"><span data-stu-id="4e043-111">[in] The count of bytes in `pvSigBlob`.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="4e043-112">から`ELEMENT_TYPE_` *\** 定数値の。</span><span class="sxs-lookup"><span data-stu-id="4e043-112">[in] The `ELEMENT_TYPE_`*\** for the constant value.</span></span> <span data-ttu-id="4e043-113">これは `CorElementType` 値です。</span><span class="sxs-lookup"><span data-stu-id="4e043-113">This is a `CorElementType` value.</span></span> <span data-ttu-id="4e043-114">フィールドの定数値を定義していない場合は、を使用し `ELEMENT_TYPE_END` ます。</span><span class="sxs-lookup"><span data-stu-id="4e043-114">If not defining a constant value for the field, use `ELEMENT_TYPE_END`.</span></span>  
  
 `pValue`  
 <span data-ttu-id="4e043-115">からフィールドの定数値。</span><span class="sxs-lookup"><span data-stu-id="4e043-115">[in] The constant value for the field.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="4e043-116">からの (Unicode) 文字のサイズ `pValue` 。</span><span class="sxs-lookup"><span data-stu-id="4e043-116">[in] The size in (Unicode) characters of `pValue`.</span></span>  
  
 `pmd`  
 <span data-ttu-id="4e043-117">入出力`mdFieldDef`割り当てられたトークン。</span><span class="sxs-lookup"><span data-stu-id="4e043-117">[out] The `mdFieldDef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e043-118">必要条件</span><span class="sxs-lookup"><span data-stu-id="4e043-118">Requirements</span></span>  
 <span data-ttu-id="4e043-119">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4e043-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e043-120">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="4e043-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4e043-121">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="4e043-121">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4e043-122">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e043-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e043-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="4e043-123">See also</span></span>

- [<span data-ttu-id="4e043-124">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4e043-124">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="4e043-125">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4e043-125">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
