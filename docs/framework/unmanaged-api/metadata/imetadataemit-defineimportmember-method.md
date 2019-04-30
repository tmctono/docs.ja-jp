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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 81acda4d395563fc8e0000e38036d1aaa0f14471
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62043220"
---
# <a name="imetadataemitdefineimportmember-method"></a><span data-ttu-id="4d329-102">IMetaDataEmit::DefineImportMember メソッド</span><span class="sxs-lookup"><span data-stu-id="4d329-102">IMetaDataEmit::DefineImportMember Method</span></span>
<span data-ttu-id="4d329-103">型または現在のスコープ外に定義され、その参照のトークンを定義するモジュールの指定されたメンバーへの参照を作成します。</span><span class="sxs-lookup"><span data-stu-id="4d329-103">Creates a reference to the specified member of a type or module that is defined outside the current scope, and defines a token for that reference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d329-104">構文</span><span class="sxs-lookup"><span data-stu-id="4d329-104">Syntax</span></span>  
  
```  
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
  
## <a name="parameters"></a><span data-ttu-id="4d329-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4d329-105">Parameters</span></span>  
 `pAssemImport`  
 <span data-ttu-id="4d329-106">[in][IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)対象メンバーのインポート元となるアセンブリを表すインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="4d329-106">[in] An [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interface that represents the assembly from which the target member is imported.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="4d329-107">[in]指定されたアセンブリのハッシュを格納する配列`pAssemImport`します。</span><span class="sxs-lookup"><span data-stu-id="4d329-107">[in] An array that contains the hash for the assembly specified by `pAssemImport`.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="4d329-108">[in] `pbHashValue` 配列のバイト数。</span><span class="sxs-lookup"><span data-stu-id="4d329-108">[in] The number of bytes in the `pbHashValue` array.</span></span>  
  
 `pImport`  
 <span data-ttu-id="4d329-109">[in][IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)対象メンバーのインポート元のメタデータ スコープを表すインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="4d329-109">[in] An [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface that represents the metadata scope from which the target member is imported.</span></span>  
  
 `mbMember`  
 <span data-ttu-id="4d329-110">[in]ターゲット メンバーを指定するメタデータ トークンです。</span><span class="sxs-lookup"><span data-stu-id="4d329-110">[in] The metadata token that specifies the target member.</span></span> <span data-ttu-id="4d329-111">トークンを指定できます、 `mdMethodDef` (メンバー メソッドの場合) の`mdProperty`(のメンバー プロパティの場合) または`mdFieldDef`(メンバー フィールド) のトークン。</span><span class="sxs-lookup"><span data-stu-id="4d329-111">The token can be an `mdMethodDef` (for a member method), `mdProperty` (for a member property), or `mdFieldDef` (for a member field) token.</span></span>  
  
 `pAssemEmit`  
 <span data-ttu-id="4d329-112">[in][IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)対象メンバーのインポート先のアセンブリを表すインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="4d329-112">[in] An [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) interface that represents the assembly into which the target member is imported.</span></span>  
  
 `tkParent`  
 <span data-ttu-id="4d329-113">[in]`mdTypeRef`または`mdModuleRef`型またはモジュールのトークンを所有する対象のメンバー。</span><span class="sxs-lookup"><span data-stu-id="4d329-113">[in] The `mdTypeRef` or `mdModuleRef` token for the type or module, respectively, that owns the target member.</span></span>  
  
 `pmr`  
 <span data-ttu-id="4d329-114">[out]`mdMemberRef`メンバー参照の現在のスコープで定義されているトークンです。</span><span class="sxs-lookup"><span data-stu-id="4d329-114">[out] The `mdMemberRef` token that is defined in the current scope for the member reference.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4d329-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="4d329-115">Remarks</span></span>  
 <span data-ttu-id="4d329-116">`DefineImportMember`メソッドで指定されたメンバーを検索`mbMember`がで指定された別のスコープで定義されている`pImport`、そのプロパティを取得します。</span><span class="sxs-lookup"><span data-stu-id="4d329-116">The `DefineImportMember` method looks up the member, specified by `mbMember`, that is defined in another scope, specified by `pImport`, and retrieves its properties.</span></span> <span data-ttu-id="4d329-117">呼び出しにこの情報を使用して、 [imetadataemit::definememberref](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md)メンバー参照を作成する現在のスコープ内のメソッド。</span><span class="sxs-lookup"><span data-stu-id="4d329-117">It uses this information to call the [IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md) method in the current scope to create the member reference.</span></span>  
  
 <span data-ttu-id="4d329-118">使用する前に、一般に、`DefineImportMember`メソッドを作成する必要が、現在のスコープは、型参照またはターゲット メンバーの親クラス、インターフェイス、またはモジュールのモジュール参照。</span><span class="sxs-lookup"><span data-stu-id="4d329-118">Generally, before you use the `DefineImportMember` method, you must create, in the current scope, a type reference or module reference for the target member's parent class, interface, or module.</span></span> <span data-ttu-id="4d329-119">この参照のメタデータ トークンが渡されたし、`tkParent`引数。</span><span class="sxs-lookup"><span data-stu-id="4d329-119">The metadata token for this reference is then passed in the `tkParent` argument.</span></span> <span data-ttu-id="4d329-120">コンパイラまたはリンカーによって後で解決する場合は、ターゲット メンバーの親への参照を作成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="4d329-120">You do not need to create a reference to the target member's parent if it will be resolved later by the compiler or linker.</span></span> <span data-ttu-id="4d329-121">まとめ</span><span class="sxs-lookup"><span data-stu-id="4d329-121">To summarize:</span></span>  
  
- <span data-ttu-id="4d329-122">対象のメンバーがフィールドまたはメソッドの場合は、いずれかを使用、 [imetadataemit::definetyperefbyname](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md)または[imetadataemit::defineimporttype](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md)の現在のスコープ内の型参照を作成する方法、メンバーの親クラスまたはインターフェイスの親。</span><span class="sxs-lookup"><span data-stu-id="4d329-122">If the target member is a field or method, use either the [IMetaDataEmit::DefineTypeRefByName](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) or the [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md) method to create a type reference, in the current scope, for the member's parent class or parent interface.</span></span>  
  
- <span data-ttu-id="4d329-123">グローバル変数またはグローバル関数 (つまり、いないメンバー クラスまたはインターフェイスの) の場合は、対象のメンバーを使用して、 [imetadataemit::definemoduleref](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md)メソッド メンバーの親の現在のスコープ内のモジュール参照を作成するにはモジュール。</span><span class="sxs-lookup"><span data-stu-id="4d329-123">If the target member is a global variable or global function (that is, not a member of a class or interface), use the [IMetaDataEmit::DefineModuleRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md) method to create a module reference, in the current scope, for the member's parent module.</span></span>  
  
- <span data-ttu-id="4d329-124">ターゲット メンバーの親はコンパイラまたはリンカーで後で解決される、その渡す`mdTokenNil`で`tkParent`します。</span><span class="sxs-lookup"><span data-stu-id="4d329-124">If the target member's parent will be resolved later by the compiler or linker, then pass `mdTokenNil` in `tkParent`.</span></span> <span data-ttu-id="4d329-125">これが適用される唯一のシナリオは、グローバル関数またはグローバル変数が最終的には、現在のモジュールにリンクされる .obj ファイルからインポートされると、メタデータのマージします。</span><span class="sxs-lookup"><span data-stu-id="4d329-125">The only scenario in which this applies is when a global function or global variable is being imported from a .obj file that will ultimately be linked into the current module and the metadata merged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d329-126">必要条件</span><span class="sxs-lookup"><span data-stu-id="4d329-126">Requirements</span></span>  
 <span data-ttu-id="4d329-127">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4d329-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4d329-128">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="4d329-128">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4d329-129">**ライブラリ:** MSCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="4d329-129">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4d329-130">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4d329-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d329-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="4d329-131">See also</span></span>

- [<span data-ttu-id="4d329-132">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4d329-132">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="4d329-133">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4d329-133">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
