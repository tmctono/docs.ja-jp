---
title: IMetaDataEmit::SetTypeDefProps メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetTypeDefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetTypeDefProps
helpviewer_keywords:
- SetTypeDefProps method [.NET Framework metadata]
- IMetaDataEmit::SetTypeDefProps method [.NET Framework metadata]
ms.assetid: 480d596a-759f-4d29-ac1a-3dbff8f3544d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 596888a8eb4a55c4cfe594b1911f17f6d32f56d2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61992434"
---
# <a name="imetadataemitsettypedefprops-method"></a><span data-ttu-id="7cb32-102">IMetaDataEmit::SetTypeDefProps メソッド</span><span class="sxs-lookup"><span data-stu-id="7cb32-102">IMetaDataEmit::SetTypeDefProps Method</span></span>
<span data-ttu-id="7cb32-103">前回の呼び出しによって定義された型の機能を設定[imetadataemit::definetypedef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="7cb32-103">Sets features of a type defined by a prior call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7cb32-104">構文</span><span class="sxs-lookup"><span data-stu-id="7cb32-104">Syntax</span></span>  
  
```  
HRESULT SetTypeDefProps (  
    [in]  mdTypeDef   td,   
    [in]  DWORD       dwTypeDefFlags,   
    [in]  mdToken     tkExtends,   
    [in]  mdToken     rtkImplements[]   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7cb32-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7cb32-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="7cb32-106">[in]`mdTypeDef`元の呼び出しから取得したトークン[imetadataemit::definetypedef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="7cb32-106">[in] An `mdTypeDef` token obtained from original call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="7cb32-107">[in]`TypeDef`属性。</span><span class="sxs-lookup"><span data-stu-id="7cb32-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="7cb32-108">これは、ビットマスクの`CorTypeAttr`値。</span><span class="sxs-lookup"><span data-stu-id="7cb32-108">This is a bitmask of `CorTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="7cb32-109">[in]`mdToken`の基本クラス。</span><span class="sxs-lookup"><span data-stu-id="7cb32-109">[in] The `mdToken` of the base class.</span></span> <span data-ttu-id="7cb32-110">以前の呼び出しから取得した[imetadataemit::defineimporttype](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md)、または`null`します。</span><span class="sxs-lookup"><span data-stu-id="7cb32-110">Obtained from a previous call to [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md), or `null`.</span></span>  
  
 `rtkImplements[]`  
 <span data-ttu-id="7cb32-111">[in]この型が実装するインターフェイスのためのトークンの配列。</span><span class="sxs-lookup"><span data-stu-id="7cb32-111">[in] An array of tokens for the interfaces that this type implements.</span></span> <span data-ttu-id="7cb32-112">これら`mdTypeRef`を使用してトークンの取得[imetadataemit::defineimporttype](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="7cb32-112">These `mdTypeRef` tokens are obtained using [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md).</span></span> <span data-ttu-id="7cb32-113">配列の最後の要素がある必要があります`mdTokenNil`します。</span><span class="sxs-lookup"><span data-stu-id="7cb32-113">The last element of the array is must be `mdTokenNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7cb32-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="7cb32-114">Requirements</span></span>  
 <span data-ttu-id="7cb32-115">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7cb32-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7cb32-116">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7cb32-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7cb32-117">**ライブラリ:** MSCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="7cb32-117">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7cb32-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7cb32-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cb32-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="7cb32-119">See also</span></span>

- [<span data-ttu-id="7cb32-120">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7cb32-120">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="7cb32-121">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7cb32-121">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
