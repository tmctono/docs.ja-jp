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
ms.openlocfilehash: baee8566e923f9cb31868f8aa0e379ff1dfa42fc
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777229"
---
# <a name="imetadataemitsettypedefprops-method"></a><span data-ttu-id="b0301-102">IMetaDataEmit::SetTypeDefProps メソッド</span><span class="sxs-lookup"><span data-stu-id="b0301-102">IMetaDataEmit::SetTypeDefProps Method</span></span>
<span data-ttu-id="b0301-103">前回の呼び出しによって定義された型の機能を設定[imetadataemit::definetypedef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="b0301-103">Sets features of a type defined by a prior call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0301-104">構文</span><span class="sxs-lookup"><span data-stu-id="b0301-104">Syntax</span></span>  
  
```cpp  
HRESULT SetTypeDefProps (  
    [in]  mdTypeDef   td,   
    [in]  DWORD       dwTypeDefFlags,   
    [in]  mdToken     tkExtends,   
    [in]  mdToken     rtkImplements[]   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b0301-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b0301-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="b0301-106">[in]`mdTypeDef`元の呼び出しから取得したトークン[imetadataemit::definetypedef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="b0301-106">[in] An `mdTypeDef` token obtained from original call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="b0301-107">[in]`TypeDef`属性。</span><span class="sxs-lookup"><span data-stu-id="b0301-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="b0301-108">これは、ビットマスクの`CorTypeAttr`値。</span><span class="sxs-lookup"><span data-stu-id="b0301-108">This is a bitmask of `CorTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="b0301-109">[in]`mdToken`の基本クラス。</span><span class="sxs-lookup"><span data-stu-id="b0301-109">[in] The `mdToken` of the base class.</span></span> <span data-ttu-id="b0301-110">以前の呼び出しから取得した[imetadataemit::defineimporttype](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md)、または`null`します。</span><span class="sxs-lookup"><span data-stu-id="b0301-110">Obtained from a previous call to [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md), or `null`.</span></span>  
  
 `rtkImplements[]`  
 <span data-ttu-id="b0301-111">[in]この型が実装するインターフェイスのためのトークンの配列。</span><span class="sxs-lookup"><span data-stu-id="b0301-111">[in] An array of tokens for the interfaces that this type implements.</span></span> <span data-ttu-id="b0301-112">これら`mdTypeRef`を使用してトークンの取得[imetadataemit::defineimporttype](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="b0301-112">These `mdTypeRef` tokens are obtained using [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md).</span></span> <span data-ttu-id="b0301-113">配列の最後の要素がある必要があります`mdTokenNil`します。</span><span class="sxs-lookup"><span data-stu-id="b0301-113">The last element of the array is must be `mdTokenNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0301-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="b0301-114">Requirements</span></span>  
 <span data-ttu-id="b0301-115">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0301-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0301-116">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b0301-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b0301-117">**ライブラリ:** MSCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="b0301-117">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b0301-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0301-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0301-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="b0301-119">See also</span></span>

- [<span data-ttu-id="b0301-120">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b0301-120">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="b0301-121">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b0301-121">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
