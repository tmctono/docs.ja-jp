---
title: IMetaDataEmit::DefineImportMember メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineImportMember
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineImportMember
helpviewer_keywords:
- DefineImportMember method [.NET Framework metadata]
- IMetaDataEmit::DefineImportMember method [.NET Framework metadata]
ms.assetid: c7dd94c6-335b-46ff-9dfe-505056db5673
topic_type:
- apiref
ms.openlocfilehash: a7449ffc8a8ccf2db62ab3cff2f9cfaffd0c72a9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175864"
---
# <a name="imetadataemitdefineimportmember-method"></a><span data-ttu-id="756c2-102">IMetaDataEmit::DefineImportMember メソッド</span><span class="sxs-lookup"><span data-stu-id="756c2-102">IMetaDataEmit::DefineImportMember Method</span></span>
<span data-ttu-id="756c2-103">現在のスコープの外部で定義されている型またはモジュールの指定されたメンバーへの参照を作成し、その参照のトークンを定義します。</span><span class="sxs-lookup"><span data-stu-id="756c2-103">Creates a reference to the specified member of a type or module that is defined outside the current scope, and defines a token for that reference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="756c2-104">構文</span><span class="sxs-lookup"><span data-stu-id="756c2-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineImportMember (
    [in]  IMetaDataAssemblyImport  *pAssemImport,
    [in]  const void               *pbHashValue,
    [in]  ULONG                    cbHashValue,  
    [in]  IMetaDataImport          *pImport,
    [in]  mdToken                  mbMember,
    [in]  IMetaDataAssemblyEmit    *pAssemEmit,
    [in]  mdToken                  tkParent,
    [out] mdMemberRef              *pmr
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="756c2-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="756c2-105">Parameters</span></span>  
 `pAssemImport`  
 <span data-ttu-id="756c2-106">[in]ターゲット メンバーのインポート元のアセンブリを表す[IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="756c2-106">[in] An [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interface that represents the assembly from which the target member is imported.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="756c2-107">[in]で指定されたアセンブリのハッシュを格納する`pAssemImport`配列。</span><span class="sxs-lookup"><span data-stu-id="756c2-107">[in] An array that contains the hash for the assembly specified by `pAssemImport`.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="756c2-108">[in] `pbHashValue` 配列のバイト数。</span><span class="sxs-lookup"><span data-stu-id="756c2-108">[in] The number of bytes in the `pbHashValue` array.</span></span>  
  
 `pImport`  
 <span data-ttu-id="756c2-109">[in]ターゲット メンバーのインポート元のメタデータ スコープを表す[IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="756c2-109">[in] An [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface that represents the metadata scope from which the target member is imported.</span></span>  
  
 `mbMember`  
 <span data-ttu-id="756c2-110">[in]ターゲット メンバーを指定するメタデータ トークン。</span><span class="sxs-lookup"><span data-stu-id="756c2-110">[in] The metadata token that specifies the target member.</span></span> <span data-ttu-id="756c2-111">トークンは`mdMethodDef`、(メンバー メソッドの場合)、(`mdProperty`メンバー プロパティの場合)、または`mdFieldDef`(メンバー フィールドの場合) トークンです。</span><span class="sxs-lookup"><span data-stu-id="756c2-111">The token can be an `mdMethodDef` (for a member method), `mdProperty` (for a member property), or `mdFieldDef` (for a member field) token.</span></span>  
  
 `pAssemEmit`  
 <span data-ttu-id="756c2-112">[in]ターゲット メンバーのインポート先のアセンブリを表す[IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="756c2-112">[in] An [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) interface that represents the assembly into which the target member is imported.</span></span>  
  
 `tkParent`  
 <span data-ttu-id="756c2-113">[in]`mdTypeRef`ターゲット メンバーを所有する型またはモジュールのトークンまたは`mdModuleRef`トークン。</span><span class="sxs-lookup"><span data-stu-id="756c2-113">[in] The `mdTypeRef` or `mdModuleRef` token for the type or module, respectively, that owns the target member.</span></span>  
  
 `pmr`  
 <span data-ttu-id="756c2-114">[アウト]メンバー`mdMemberRef`参照の現在のスコープで定義されているトークン。</span><span class="sxs-lookup"><span data-stu-id="756c2-114">[out] The `mdMemberRef` token that is defined in the current scope for the member reference.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="756c2-115">解説</span><span class="sxs-lookup"><span data-stu-id="756c2-115">Remarks</span></span>  
 <span data-ttu-id="756c2-116">この`DefineImportMember`メソッドは、 で`mbMember`指定された別のスコープで定義されている メンバーを検索し`pImport`、そのプロパティを取得します。</span><span class="sxs-lookup"><span data-stu-id="756c2-116">The `DefineImportMember` method looks up the member, specified by `mbMember`, that is defined in another scope, specified by `pImport`, and retrieves its properties.</span></span> <span data-ttu-id="756c2-117">この情報を使用して、現在のスコープの[IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md)メソッドを呼び出してメンバー参照を作成します。</span><span class="sxs-lookup"><span data-stu-id="756c2-117">It uses this information to call the [IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md) method in the current scope to create the member reference.</span></span>  
  
 <span data-ttu-id="756c2-118">通常、メソッドを`DefineImportMember`使用する前に、現在のスコープで、ターゲット メンバーの親クラス、インターフェイス、またはモジュールの型参照またはモジュール参照を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="756c2-118">Generally, before you use the `DefineImportMember` method, you must create, in the current scope, a type reference or module reference for the target member's parent class, interface, or module.</span></span> <span data-ttu-id="756c2-119">この参照のメタデータ トークンは`tkParent`、引数に渡されます。</span><span class="sxs-lookup"><span data-stu-id="756c2-119">The metadata token for this reference is then passed in the `tkParent` argument.</span></span> <span data-ttu-id="756c2-120">後でコンパイラまたはリンカーによって解決される場合は、ターゲット メンバーの親への参照を作成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="756c2-120">You do not need to create a reference to the target member's parent if it will be resolved later by the compiler or linker.</span></span> <span data-ttu-id="756c2-121">まとめると次のようになります。</span><span class="sxs-lookup"><span data-stu-id="756c2-121">To summarize:</span></span>  
  
- <span data-ttu-id="756c2-122">ターゲット メンバーがフィールドまたはメソッドの場合は[、IMetaDataEmit::DefineTypeRefByName](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md)または[IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md)メソッドを使用して、メンバーの親クラスまたは親インターフェイスの型参照を現在のスコープ内に作成します。</span><span class="sxs-lookup"><span data-stu-id="756c2-122">If the target member is a field or method, use either the [IMetaDataEmit::DefineTypeRefByName](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) or the [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md) method to create a type reference, in the current scope, for the member's parent class or parent interface.</span></span>  
  
- <span data-ttu-id="756c2-123">対象のメンバーがグローバル変数またはグローバル関数 (つまり、クラスまたはインターフェイスのメンバーではない) である場合は[、IMetaDataEmit::DefineModuleRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md)メソッドを使用して、メンバーの親モジュールの現在のスコープ内にモジュール参照を作成します。</span><span class="sxs-lookup"><span data-stu-id="756c2-123">If the target member is a global variable or global function (that is, not a member of a class or interface), use the [IMetaDataEmit::DefineModuleRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md) method to create a module reference, in the current scope, for the member's parent module.</span></span>  
  
- <span data-ttu-id="756c2-124">ターゲット メンバーの親が後でコンパイラまたはリンカーによって解決される場合は、`mdTokenNil``tkParent`を渡します。</span><span class="sxs-lookup"><span data-stu-id="756c2-124">If the target member's parent will be resolved later by the compiler or linker, then pass `mdTokenNil` in `tkParent`.</span></span> <span data-ttu-id="756c2-125">この場合、グローバル関数またはグローバル変数が .obj ファイルからインポートされ、最終的に現在のモジュールにリンクされ、メタデータがマージされる場合があります。</span><span class="sxs-lookup"><span data-stu-id="756c2-125">The only scenario in which this applies is when a global function or global variable is being imported from a .obj file that will ultimately be linked into the current module and the metadata merged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="756c2-126">必要条件</span><span class="sxs-lookup"><span data-stu-id="756c2-126">Requirements</span></span>  
 <span data-ttu-id="756c2-127">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="756c2-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="756c2-128">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="756c2-128">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="756c2-129">**ライブラリ:** MSCorEE.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="756c2-129">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="756c2-130">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="756c2-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="756c2-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="756c2-131">See also</span></span>

- [<span data-ttu-id="756c2-132">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="756c2-132">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="756c2-133">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="756c2-133">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
