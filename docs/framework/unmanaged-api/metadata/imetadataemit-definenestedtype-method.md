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
ms.openlocfilehash: 5d985e22ba77053127610445374b8c13ca6b97f1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431707"
---
# <a name="imetadataemitdefinenestedtype-method"></a><span data-ttu-id="3be7f-102">IMetaDataEmit::DefineNestedType メソッド</span><span class="sxs-lookup"><span data-stu-id="3be7f-102">IMetaDataEmit::DefineNestedType Method</span></span>
<span data-ttu-id="3be7f-103">型定義のメタデータシグネチャを作成し、その型の `mdTypeDef` トークンを返し、`tdEncloser` パラメーターによって参照される型のメンバーであることを指定します。</span><span class="sxs-lookup"><span data-stu-id="3be7f-103">Creates the metadata signature of a type definition, returns an `mdTypeDef` token for that type, and specifies that the defined type is a member of the type referenced by the `tdEncloser` parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3be7f-104">構文</span><span class="sxs-lookup"><span data-stu-id="3be7f-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="3be7f-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3be7f-105">Parameters</span></span>  
 `szTypeDef`  
 <span data-ttu-id="3be7f-106">からUnicode での型の名前。</span><span class="sxs-lookup"><span data-stu-id="3be7f-106">[in] The name of the type in Unicode.</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="3be7f-107">[in] 属性 `TypeDef` ます。</span><span class="sxs-lookup"><span data-stu-id="3be7f-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="3be7f-108">これは `CorTypeAttr` 値のビットマスクです。</span><span class="sxs-lookup"><span data-stu-id="3be7f-108">This is a bitmask of `CorTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="3be7f-109">から基本クラスのトークン。</span><span class="sxs-lookup"><span data-stu-id="3be7f-109">[in] The token of the base class.</span></span> <span data-ttu-id="3be7f-110">これは、`mdTypeDef` または `mdTypeRef` トークンのいずれかです。</span><span class="sxs-lookup"><span data-stu-id="3be7f-110">This is either a `mdTypeDef` or a `mdTypeRef` token.</span></span>  
  
 <span data-ttu-id="3be7f-111">`rtkImplements`[]</span><span class="sxs-lookup"><span data-stu-id="3be7f-111">`rtkImplements`[]</span></span>  
 <span data-ttu-id="3be7f-112">からこのクラスまたはインターフェイスが実装するインターフェイスを指定するトークンの配列。</span><span class="sxs-lookup"><span data-stu-id="3be7f-112">[in] An array of tokens that specify the interfaces that this class or interface implements.</span></span>  
  
 `tdEncloser`  
 <span data-ttu-id="3be7f-113">から外側の型のトークン。</span><span class="sxs-lookup"><span data-stu-id="3be7f-113">[in] The token of the enclosing type.</span></span> <span data-ttu-id="3be7f-114">配列の最後の要素は `mdTokenNil`である必要があります。</span><span class="sxs-lookup"><span data-stu-id="3be7f-114">The last element of the array must be `mdTokenNil`.</span></span>  
  
 `ptd`  
 <span data-ttu-id="3be7f-115">入出力割り当てられた `mdTypeDef` トークン。</span><span class="sxs-lookup"><span data-stu-id="3be7f-115">[out] The `mdTypeDef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3be7f-116">要件</span><span class="sxs-lookup"><span data-stu-id="3be7f-116">Requirements</span></span>  
 <span data-ttu-id="3be7f-117">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3be7f-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3be7f-118">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="3be7f-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3be7f-119">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="3be7f-119">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3be7f-120">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3be7f-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3be7f-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="3be7f-121">See also</span></span>

- [<span data-ttu-id="3be7f-122">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3be7f-122">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="3be7f-123">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3be7f-123">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
