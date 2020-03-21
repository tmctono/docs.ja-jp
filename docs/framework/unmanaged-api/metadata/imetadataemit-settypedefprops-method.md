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
ms.openlocfilehash: e59e7695246b2c83171e77352e16464258516f8d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177463"
---
# <a name="imetadataemitsettypedefprops-method"></a><span data-ttu-id="bc2cf-102">IMetaDataEmit::SetTypeDefProps メソッド</span><span class="sxs-lookup"><span data-stu-id="bc2cf-102">IMetaDataEmit::SetTypeDefProps Method</span></span>
<span data-ttu-id="bc2cf-103">[:D 以前](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md)の呼び出しで定義された型の機能を設定します。</span><span class="sxs-lookup"><span data-stu-id="bc2cf-103">Sets features of a type defined by a prior call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc2cf-104">構文</span><span class="sxs-lookup"><span data-stu-id="bc2cf-104">Syntax</span></span>  
  
```cpp  
HRESULT SetTypeDefProps (  
    [in]  mdTypeDef   td,
    [in]  DWORD       dwTypeDefFlags,
    [in]  mdToken     tkExtends,
    [in]  mdToken     rtkImplements[]
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bc2cf-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="bc2cf-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="bc2cf-106">[in]元`mdTypeDef`の呼び出しから取得したトークン[:D。](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md)</span><span class="sxs-lookup"><span data-stu-id="bc2cf-106">[in] An `mdTypeDef` token obtained from original call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="bc2cf-107">[in]`TypeDef`属性を指定します。</span><span class="sxs-lookup"><span data-stu-id="bc2cf-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="bc2cf-108">これは値の`CorTypeAttr`ビットマスクです。</span><span class="sxs-lookup"><span data-stu-id="bc2cf-108">This is a bitmask of `CorTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="bc2cf-109">[in]基本`mdToken`クラスの。</span><span class="sxs-lookup"><span data-stu-id="bc2cf-109">[in] The `mdToken` of the base class.</span></span> <span data-ttu-id="bc2cf-110">[:D 以前](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md)の呼び出しから取得しました`null`。</span><span class="sxs-lookup"><span data-stu-id="bc2cf-110">Obtained from a previous call to [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md), or `null`.</span></span>  
  
 `rtkImplements[]`  
 <span data-ttu-id="bc2cf-111">[in]この型が実装するインターフェイスのトークンの配列。</span><span class="sxs-lookup"><span data-stu-id="bc2cf-111">[in] An array of tokens for the interfaces that this type implements.</span></span> <span data-ttu-id="bc2cf-112">これらの`mdTypeRef`トークンは[、IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md)を使用して取得されます。</span><span class="sxs-lookup"><span data-stu-id="bc2cf-112">These `mdTypeRef` tokens are obtained using [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md).</span></span> <span data-ttu-id="bc2cf-113">配列の最後の要素は にする`mdTokenNil`必要があります。</span><span class="sxs-lookup"><span data-stu-id="bc2cf-113">The last element of the array is must be `mdTokenNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bc2cf-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="bc2cf-114">Requirements</span></span>  
 <span data-ttu-id="bc2cf-115">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bc2cf-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc2cf-116">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="bc2cf-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bc2cf-117">**ライブラリ:** MSCorEE.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="bc2cf-117">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bc2cf-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc2cf-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc2cf-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="bc2cf-119">See also</span></span>

- [<span data-ttu-id="bc2cf-120">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bc2cf-120">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="bc2cf-121">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bc2cf-121">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
