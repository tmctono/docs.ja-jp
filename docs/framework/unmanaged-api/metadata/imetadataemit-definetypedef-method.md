---
title: IMetaDataEmit::DefineTypeDef メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineTypeDef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineTypeDef
helpviewer_keywords:
- IMetaDataEmit::DefineTypeDef method [.NET Framework metadata]
- DefineTypeDef method [.NET Framework metadata]
ms.assetid: dd11c485-be95-4b97-9cd8-68679a4fb432
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0777151d10149ec7311a7761bc7f6bff5ba98e0e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777489"
---
# <a name="imetadataemitdefinetypedef-method"></a><span data-ttu-id="9136b-102">IMetaDataEmit::DefineTypeDef メソッド</span><span class="sxs-lookup"><span data-stu-id="9136b-102">IMetaDataEmit::DefineTypeDef Method</span></span>
<span data-ttu-id="9136b-103">共通言語ランタイム型では、型定義を作成し、その種類の定義のメタデータ トークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="9136b-103">Creates a type definition for a common language runtime type, and gets a metadata token for that type definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9136b-104">構文</span><span class="sxs-lookup"><span data-stu-id="9136b-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineTypeDef (   
    [in]  LPCWSTR     szTypeDef,   
    [in]  DWORD       dwTypeDefFlags,   
    [in]  mdToken     tkExtends,   
    [in]  mdToken     rtkImplements[],   
    [out] mdTypeDef   *ptd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9136b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9136b-105">Parameters</span></span>  
 `szTypeDef`  
 <span data-ttu-id="9136b-106">[in]Unicode での型の名前。</span><span class="sxs-lookup"><span data-stu-id="9136b-106">[in] The name of the type in Unicode.</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="9136b-107">[in]`TypeDef`属性。</span><span class="sxs-lookup"><span data-stu-id="9136b-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="9136b-108">これは、ビットマスクの`CoreTypeAttr`値。</span><span class="sxs-lookup"><span data-stu-id="9136b-108">This is a bitmask of `CoreTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="9136b-109">[in]基底クラスのトークンです。</span><span class="sxs-lookup"><span data-stu-id="9136b-109">[in] The token of the base class.</span></span> <span data-ttu-id="9136b-110">いずれかする必要があります、`mdTypeDef`または`mdTypeRef`トークンです。</span><span class="sxs-lookup"><span data-stu-id="9136b-110">It must be either an `mdTypeDef` or an `mdTypeRef` token.</span></span>  
  
 `rtkImplements`  
 <span data-ttu-id="9136b-111">[in]このクラスまたはインターフェイスを実装するインターフェイスを指定するトークンの配列。</span><span class="sxs-lookup"><span data-stu-id="9136b-111">[in] An array of tokens specifying the interfaces that this class or interface implements.</span></span>  
  
 `ptd`  
 <span data-ttu-id="9136b-112">[out]`mdTypeDef`に割り当てられたトークン。</span><span class="sxs-lookup"><span data-stu-id="9136b-112">[out] The `mdTypeDef` token assigned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9136b-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="9136b-113">Remarks</span></span>  
 <span data-ttu-id="9136b-114">フラグ`dwTypeDefFlags`作成される型が共通型システム参照型 (クラスまたはインターフェイス) または共通型システム値型があるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="9136b-114">A flag in `dwTypeDefFlags` specifies whether the type being created is a common type system reference type (class or interface) or a common type system value type.</span></span>  
  
 <span data-ttu-id="9136b-115">によって指定されたパラメーター、このメソッドは、副作用として可能性がありますも作成、`mdInterfaceImpl`継承またはこの型によって実装されるインターフェイスごとに記録します。</span><span class="sxs-lookup"><span data-stu-id="9136b-115">Depending on the parameters supplied, this method, as a side effect, may also create an `mdInterfaceImpl` record for each interface that is inherited or implemented by this type.</span></span> <span data-ttu-id="9136b-116">ただし、このメソッドが返さないいずれ`mdInterfaceImpl`トークンです。</span><span class="sxs-lookup"><span data-stu-id="9136b-116">However, this method does not return any of these `mdInterfaceImpl` tokens.</span></span> <span data-ttu-id="9136b-117">クライアントが後で追加または変更する場合、`mdInterfaceImpl`トークンを使用してがあります、`IMetaDataImport`それらを列挙するインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="9136b-117">If a client wants to later add or modify an `mdInterfaceImpl` token, it must use the `IMetaDataImport` interface to enumerate them.</span></span> <span data-ttu-id="9136b-118">COM のセマンティクスを使用する場合、`[default]`インターフェイスの最初の要素として、既定のインターフェイスを指定する必要があります`rtkImplements`; クラスに既定のインターフェイスをクラスに設定するカスタム属性が示されます (常にあると見なされますが、まず`mdInterfaceImpl`クラスの宣言されたトークン)。</span><span class="sxs-lookup"><span data-stu-id="9136b-118">If you want to use COM semantics of the `[default]` interface, you should supply the default interface as the first element in `rtkImplements`; a custom attribute set on the class will indicate that the class has a default interface (which is always assumed to be the first `mdInterfaceImpl` token declared for the class).</span></span>  
  
 <span data-ttu-id="9136b-119">各要素、`rtkImplements`配列を保持する`mdTypeDef`または`mdTypeRef`トークンです。</span><span class="sxs-lookup"><span data-stu-id="9136b-119">Each element of the `rtkImplements` array holds an `mdTypeDef` or `mdTypeRef` token.</span></span> <span data-ttu-id="9136b-120">配列内の最後の要素である必要があります`mdTokenNil`します。</span><span class="sxs-lookup"><span data-stu-id="9136b-120">The last element in the array must be `mdTokenNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9136b-121">必要条件</span><span class="sxs-lookup"><span data-stu-id="9136b-121">Requirements</span></span>  
 <span data-ttu-id="9136b-122">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9136b-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9136b-123">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="9136b-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9136b-124">**ライブラリ:** MSCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="9136b-124">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9136b-125">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9136b-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9136b-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="9136b-126">See also</span></span>

- [<span data-ttu-id="9136b-127">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9136b-127">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="9136b-128">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9136b-128">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
