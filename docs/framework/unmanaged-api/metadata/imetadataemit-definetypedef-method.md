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
ms.openlocfilehash: 031996813718a074eebab62ff54a2de52b898c22
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450215"
---
# <a name="imetadataemitdefinetypedef-method"></a><span data-ttu-id="11004-102">IMetaDataEmit::DefineTypeDef メソッド</span><span class="sxs-lookup"><span data-stu-id="11004-102">IMetaDataEmit::DefineTypeDef Method</span></span>
<span data-ttu-id="11004-103">共通言語ランタイム型の型定義を作成し、その型定義のメタデータトークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="11004-103">Creates a type definition for a common language runtime type, and gets a metadata token for that type definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11004-104">構文</span><span class="sxs-lookup"><span data-stu-id="11004-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineTypeDef (   
    [in]  LPCWSTR     szTypeDef,   
    [in]  DWORD       dwTypeDefFlags,   
    [in]  mdToken     tkExtends,   
    [in]  mdToken     rtkImplements[],   
    [out] mdTypeDef   *ptd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="11004-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="11004-105">Parameters</span></span>  
 `szTypeDef`  
 <span data-ttu-id="11004-106">からUnicode での型の名前。</span><span class="sxs-lookup"><span data-stu-id="11004-106">[in] The name of the type in Unicode.</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="11004-107">[in] 属性 `TypeDef` ます。</span><span class="sxs-lookup"><span data-stu-id="11004-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="11004-108">これは `CoreTypeAttr` 値のビットマスクです。</span><span class="sxs-lookup"><span data-stu-id="11004-108">This is a bitmask of `CoreTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="11004-109">から基本クラスのトークン。</span><span class="sxs-lookup"><span data-stu-id="11004-109">[in] The token of the base class.</span></span> <span data-ttu-id="11004-110">`mdTypeDef` または `mdTypeRef` トークンのいずれかである必要があります。</span><span class="sxs-lookup"><span data-stu-id="11004-110">It must be either an `mdTypeDef` or an `mdTypeRef` token.</span></span>  
  
 `rtkImplements`  
 <span data-ttu-id="11004-111">からこのクラスまたはインターフェイスが実装するインターフェイスを指定するトークンの配列。</span><span class="sxs-lookup"><span data-stu-id="11004-111">[in] An array of tokens specifying the interfaces that this class or interface implements.</span></span>  
  
 `ptd`  
 <span data-ttu-id="11004-112">入出力割り当てられた `mdTypeDef` トークン。</span><span class="sxs-lookup"><span data-stu-id="11004-112">[out] The `mdTypeDef` token assigned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="11004-113">コメント</span><span class="sxs-lookup"><span data-stu-id="11004-113">Remarks</span></span>  
 <span data-ttu-id="11004-114">`dwTypeDefFlags` のフラグは、作成される型が共通型システム参照型 (クラスまたはインターフェイス) であるか、共通型システム値型であるかを指定します。</span><span class="sxs-lookup"><span data-stu-id="11004-114">A flag in `dwTypeDefFlags` specifies whether the type being created is a common type system reference type (class or interface) or a common type system value type.</span></span>  
  
 <span data-ttu-id="11004-115">このメソッドは、指定されたパラメーターに応じて、この型によって継承または実装されるインターフェイスごとに `mdInterfaceImpl` レコードを作成する場合もあります。</span><span class="sxs-lookup"><span data-stu-id="11004-115">Depending on the parameters supplied, this method, as a side effect, may also create an `mdInterfaceImpl` record for each interface that is inherited or implemented by this type.</span></span> <span data-ttu-id="11004-116">ただし、このメソッドはこれらの `mdInterfaceImpl` トークンを返しません。</span><span class="sxs-lookup"><span data-stu-id="11004-116">However, this method does not return any of these `mdInterfaceImpl` tokens.</span></span> <span data-ttu-id="11004-117">クライアントが後で `mdInterfaceImpl` トークンを追加または変更する場合は、`IMetaDataImport` インターフェイスを使用してそれらを列挙する必要があります。</span><span class="sxs-lookup"><span data-stu-id="11004-117">If a client wants to later add or modify an `mdInterfaceImpl` token, it must use the `IMetaDataImport` interface to enumerate them.</span></span> <span data-ttu-id="11004-118">`[default]` インターフェイスの COM セマンティクスを使用する場合は、`rtkImplements`の最初の要素として既定のインターフェイスを指定する必要があります。クラスに設定されたカスタム属性は、クラスに既定のインターフェイスがあることを示します (これは常に、クラスに対して宣言された最初の `mdInterfaceImpl` トークンと見なされます)。</span><span class="sxs-lookup"><span data-stu-id="11004-118">If you want to use COM semantics of the `[default]` interface, you should supply the default interface as the first element in `rtkImplements`; a custom attribute set on the class will indicate that the class has a default interface (which is always assumed to be the first `mdInterfaceImpl` token declared for the class).</span></span>  
  
 <span data-ttu-id="11004-119">`rtkImplements` 配列の各要素は、`mdTypeDef` または `mdTypeRef` トークンを保持します。</span><span class="sxs-lookup"><span data-stu-id="11004-119">Each element of the `rtkImplements` array holds an `mdTypeDef` or `mdTypeRef` token.</span></span> <span data-ttu-id="11004-120">配列の最後の要素は `mdTokenNil`である必要があります。</span><span class="sxs-lookup"><span data-stu-id="11004-120">The last element in the array must be `mdTokenNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11004-121">要件</span><span class="sxs-lookup"><span data-stu-id="11004-121">Requirements</span></span>  
 <span data-ttu-id="11004-122">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="11004-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11004-123">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="11004-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="11004-124">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="11004-124">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="11004-125">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11004-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11004-126">参照</span><span class="sxs-lookup"><span data-stu-id="11004-126">See also</span></span>

- [<span data-ttu-id="11004-127">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="11004-127">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="11004-128">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="11004-128">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
