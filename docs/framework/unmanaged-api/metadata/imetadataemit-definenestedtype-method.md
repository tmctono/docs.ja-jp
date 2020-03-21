---
title: IMetaDataEmit::DefineNestedType メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineNestedType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineNestedType
helpviewer_keywords:
- IMetaDataEmit::DefineNestedType method [.NET Framework metadata]
- DefineNestedType method [.NET Framework metadata]
ms.assetid: 1e994de6-4628-459c-b967-b34be1e9fe4f
topic_type:
- apiref
ms.openlocfilehash: 3b8fd9876563bace52a6088747d1ca4ed26ea872
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175812"
---
# <a name="imetadataemitdefinenestedtype-method"></a><span data-ttu-id="d36c5-102">IMetaDataEmit::DefineNestedType メソッド</span><span class="sxs-lookup"><span data-stu-id="d36c5-102">IMetaDataEmit::DefineNestedType Method</span></span>
<span data-ttu-id="d36c5-103">型定義のメタデータ シグネチャを作成し、その型`mdTypeDef`のトークンを返し、定義された型が`tdEncloser`パラメーターによって参照される型のメンバーであることを指定します。</span><span class="sxs-lookup"><span data-stu-id="d36c5-103">Creates the metadata signature of a type definition, returns an `mdTypeDef` token for that type, and specifies that the defined type is a member of the type referenced by the `tdEncloser` parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d36c5-104">構文</span><span class="sxs-lookup"><span data-stu-id="d36c5-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineNestedType (
    [in]  LPCWSTR     szTypeDef,  
    [in]  DWORD       dwTypeDefFlags,
    [in]  mdToken     tkExtends,
    [in]  mdToken     rtkImplements[],
    [in]  mdTypeDef   tdEncloser,
    [out] mdTypeDef   *ptd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d36c5-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d36c5-105">Parameters</span></span>  
 `szTypeDef`  
 <span data-ttu-id="d36c5-106">[in]ユニコードの型の名前。</span><span class="sxs-lookup"><span data-stu-id="d36c5-106">[in] The name of the type in Unicode.</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="d36c5-107">[in]`TypeDef`属性を指定します。</span><span class="sxs-lookup"><span data-stu-id="d36c5-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="d36c5-108">これは値の`CorTypeAttr`ビットマスクです。</span><span class="sxs-lookup"><span data-stu-id="d36c5-108">This is a bitmask of `CorTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="d36c5-109">[in]基本クラスのトークン。</span><span class="sxs-lookup"><span data-stu-id="d36c5-109">[in] The token of the base class.</span></span> <span data-ttu-id="d36c5-110">これは、トークン`mdTypeDef`またはトークンのいずれか`mdTypeRef`です。</span><span class="sxs-lookup"><span data-stu-id="d36c5-110">This is either a `mdTypeDef` or a `mdTypeRef` token.</span></span>  
  
 <span data-ttu-id="d36c5-111">`rtkImplements`[]</span><span class="sxs-lookup"><span data-stu-id="d36c5-111">`rtkImplements`[]</span></span>  
 <span data-ttu-id="d36c5-112">[in]このクラスまたはインターフェイスが実装するインターフェイスを指定するトークンの配列。</span><span class="sxs-lookup"><span data-stu-id="d36c5-112">[in] An array of tokens that specify the interfaces that this class or interface implements.</span></span>  
  
 `tdEncloser`  
 <span data-ttu-id="d36c5-113">[in]外側の型のトークン。</span><span class="sxs-lookup"><span data-stu-id="d36c5-113">[in] The token of the enclosing type.</span></span> <span data-ttu-id="d36c5-114">配列の最後の要素は`mdTokenNil`.</span><span class="sxs-lookup"><span data-stu-id="d36c5-114">The last element of the array must be `mdTokenNil`.</span></span>  
  
 `ptd`  
 <span data-ttu-id="d36c5-115">[アウト]割`mdTypeDef`り当てられたトークン。</span><span class="sxs-lookup"><span data-stu-id="d36c5-115">[out] The `mdTypeDef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d36c5-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="d36c5-116">Requirements</span></span>  
 <span data-ttu-id="d36c5-117">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d36c5-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d36c5-118">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="d36c5-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d36c5-119">**ライブラリ:** MSCorEE.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="d36c5-119">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d36c5-120">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d36c5-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d36c5-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="d36c5-121">See also</span></span>

- [<span data-ttu-id="d36c5-122">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d36c5-122">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="d36c5-123">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d36c5-123">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
