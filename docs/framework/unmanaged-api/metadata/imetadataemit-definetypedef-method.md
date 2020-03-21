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
ms.openlocfilehash: 4f1c3e823b35fcf7d5935eee111e042b2291d216
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175760"
---
# <a name="imetadataemitdefinetypedef-method"></a><span data-ttu-id="ef8f7-102">IMetaDataEmit::DefineTypeDef メソッド</span><span class="sxs-lookup"><span data-stu-id="ef8f7-102">IMetaDataEmit::DefineTypeDef Method</span></span>
<span data-ttu-id="ef8f7-103">共通言語ランタイム型の型定義を作成し、その型定義のメタデータ トークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="ef8f7-103">Creates a type definition for a common language runtime type, and gets a metadata token for that type definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef8f7-104">構文</span><span class="sxs-lookup"><span data-stu-id="ef8f7-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineTypeDef (
    [in]  LPCWSTR     szTypeDef,
    [in]  DWORD       dwTypeDefFlags,
    [in]  mdToken     tkExtends,
    [in]  mdToken     rtkImplements[],
    [out] mdTypeDef   *ptd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ef8f7-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ef8f7-105">Parameters</span></span>  
 `szTypeDef`  
 <span data-ttu-id="ef8f7-106">[in]ユニコードの型の名前。</span><span class="sxs-lookup"><span data-stu-id="ef8f7-106">[in] The name of the type in Unicode.</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="ef8f7-107">[in]`TypeDef`属性を指定します。</span><span class="sxs-lookup"><span data-stu-id="ef8f7-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="ef8f7-108">これは値の`CoreTypeAttr`ビットマスクです。</span><span class="sxs-lookup"><span data-stu-id="ef8f7-108">This is a bitmask of `CoreTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="ef8f7-109">[in]基本クラスのトークン。</span><span class="sxs-lookup"><span data-stu-id="ef8f7-109">[in] The token of the base class.</span></span> <span data-ttu-id="ef8f7-110">トークンまたはトークン`mdTypeDef`のいずれか`mdTypeRef`である必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef8f7-110">It must be either an `mdTypeDef` or an `mdTypeRef` token.</span></span>  
  
 `rtkImplements`  
 <span data-ttu-id="ef8f7-111">[in]このクラスまたはインターフェイスが実装するインターフェイスを指定するトークンの配列。</span><span class="sxs-lookup"><span data-stu-id="ef8f7-111">[in] An array of tokens specifying the interfaces that this class or interface implements.</span></span>  
  
 `ptd`  
 <span data-ttu-id="ef8f7-112">[アウト]割`mdTypeDef`り当てられたトークン。</span><span class="sxs-lookup"><span data-stu-id="ef8f7-112">[out] The `mdTypeDef` token assigned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ef8f7-113">解説</span><span class="sxs-lookup"><span data-stu-id="ef8f7-113">Remarks</span></span>  
 <span data-ttu-id="ef8f7-114">フラグを指定`dwTypeDefFlags`する型は、作成する型が共通型システム参照型 (クラスまたはインターフェイス) であるか、または共通の型システム値型であるかを指定します。</span><span class="sxs-lookup"><span data-stu-id="ef8f7-114">A flag in `dwTypeDefFlags` specifies whether the type being created is a common type system reference type (class or interface) or a common type system value type.</span></span>  
  
 <span data-ttu-id="ef8f7-115">指定されたパラメーターによっては、このメソッドは、副作用として、この型によって継承または実装`mdInterfaceImpl`される各インターフェイスのレコードを作成することもあります。</span><span class="sxs-lookup"><span data-stu-id="ef8f7-115">Depending on the parameters supplied, this method, as a side effect, may also create an `mdInterfaceImpl` record for each interface that is inherited or implemented by this type.</span></span> <span data-ttu-id="ef8f7-116">ただし、このメソッドは、これらの`mdInterfaceImpl`トークンを返しません。</span><span class="sxs-lookup"><span data-stu-id="ef8f7-116">However, this method does not return any of these `mdInterfaceImpl` tokens.</span></span> <span data-ttu-id="ef8f7-117">クライアントが後でトークンを追加または変更する`mdInterfaceImpl`場合は、インターフェイスを使用`IMetaDataImport`してトークンを列挙する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef8f7-117">If a client wants to later add or modify an `mdInterfaceImpl` token, it must use the `IMetaDataImport` interface to enumerate them.</span></span> <span data-ttu-id="ef8f7-118">`[default]`インターフェイスの COM セマンティクスを使用する場合は、既定のインターフェイスを の最初の要素として`rtkImplements`指定する必要があります。クラスに設定されたカスタム属性は、クラスに既定のインターフェイスがあることを示します (これは常にクラスに対して`mdInterfaceImpl`宣言された最初のトークンであると想定されます)。</span><span class="sxs-lookup"><span data-stu-id="ef8f7-118">If you want to use COM semantics of the `[default]` interface, you should supply the default interface as the first element in `rtkImplements`; a custom attribute set on the class will indicate that the class has a default interface (which is always assumed to be the first `mdInterfaceImpl` token declared for the class).</span></span>  
  
 <span data-ttu-id="ef8f7-119">配列の各要素`rtkImplements`は、`mdTypeDef`または`mdTypeRef`トークンを保持します。</span><span class="sxs-lookup"><span data-stu-id="ef8f7-119">Each element of the `rtkImplements` array holds an `mdTypeDef` or `mdTypeRef` token.</span></span> <span data-ttu-id="ef8f7-120">配列の最後の要素は`mdTokenNil`.</span><span class="sxs-lookup"><span data-stu-id="ef8f7-120">The last element in the array must be `mdTokenNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef8f7-121">必要条件</span><span class="sxs-lookup"><span data-stu-id="ef8f7-121">Requirements</span></span>  
 <span data-ttu-id="ef8f7-122">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ef8f7-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef8f7-123">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="ef8f7-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ef8f7-124">**ライブラリ:** MSCorEE.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="ef8f7-124">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ef8f7-125">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef8f7-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef8f7-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="ef8f7-126">See also</span></span>

- [<span data-ttu-id="ef8f7-127">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ef8f7-127">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="ef8f7-128">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ef8f7-128">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
