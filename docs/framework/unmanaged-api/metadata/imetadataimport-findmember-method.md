---
title: IMetaDataImport::FindMember メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindMember
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindMember
helpviewer_keywords:
- IMetaDataImport::FindMember method [.NET Framework metadata]
- FindMember method [.NET Framework metadata]
ms.assetid: ad32fb84-c2b6-41cd-888d-787ff3a90449
topic_type:
- apiref
ms.openlocfilehash: dab155b82d87609b3d3f390133e6490502a43518
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177279"
---
# <a name="imetadataimportfindmember-method"></a><span data-ttu-id="e5766-102">IMetaDataImport::FindMember メソッド</span><span class="sxs-lookup"><span data-stu-id="e5766-102">IMetaDataImport::FindMember Method</span></span>
<span data-ttu-id="e5766-103">指定した名前とメタデータ シグネチャを持つフィールドまたはメソッドの MemberDef<xref:System.Type>トークンへのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="e5766-103">Gets a pointer to the MemberDef token for field or method that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5766-104">構文</span><span class="sxs-lookup"><span data-stu-id="e5766-104">Syntax</span></span>  
  
```cpp  
HRESULT FindMember (  
   [in]  mdTypeDef         td,  
   [in]  LPCWSTR           szName,
   [in]  PCCOR_SIGNATURE   pvSigBlob,
   [in]  ULONG             cbSigBlob,
   [out] mdToken           *pmb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e5766-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e5766-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="e5766-106">[in]検索するメンバーを囲むクラスまたはインターフェイスの TypeDef トークン。</span><span class="sxs-lookup"><span data-stu-id="e5766-106">[in] The TypeDef token for the class or interface that encloses the member to search for.</span></span> <span data-ttu-id="e5766-107">この値が`mdTokenNil`の場合、グローバル変数またはグローバル関数の検索が行われます。</span><span class="sxs-lookup"><span data-stu-id="e5766-107">If this value is `mdTokenNil`, the lookup is done for a global-variable or global-function.</span></span>  
  
 `szName`  
 <span data-ttu-id="e5766-108">[in]検索するメンバーの名前。</span><span class="sxs-lookup"><span data-stu-id="e5766-108">[in] The name of the member to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="e5766-109">[in]メンバーのバイナリ メタデータ シグネチャへのポインター。</span><span class="sxs-lookup"><span data-stu-id="e5766-109">[in] A pointer to the binary metadata signature of the member.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="e5766-110">[in]のサイズ (バイト`pvSigBlob`単位)</span><span class="sxs-lookup"><span data-stu-id="e5766-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmb`  
 <span data-ttu-id="e5766-111">[アウト]一致する MemberDef トークンへのポインター。</span><span class="sxs-lookup"><span data-stu-id="e5766-111">[out] A pointer to the matching MemberDef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e5766-112">解説</span><span class="sxs-lookup"><span data-stu-id="e5766-112">Remarks</span></span>  
 <span data-ttu-id="e5766-113">メンバーを指定するには、外側のクラスまたはインターフェイス (`td`) 、`szName`その名前 ( )`pvSigBlob`、およびオプションでそのシグネチャ ( ) を使用します。</span><span class="sxs-lookup"><span data-stu-id="e5766-113">You specify the member using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span> <span data-ttu-id="e5766-114">クラスまたはインターフェイス内に同じ名前のメンバーが複数存在する場合があります。</span><span class="sxs-lookup"><span data-stu-id="e5766-114">There might be multiple members with the same name in a class or interface.</span></span> <span data-ttu-id="e5766-115">その場合は、メンバーの署名を渡して一意の一致を見つけます。</span><span class="sxs-lookup"><span data-stu-id="e5766-115">In that case, pass the member's signature to find the unique match.</span></span>  
  
 <span data-ttu-id="e5766-116">渡された署名は`FindMember`、特定のスコープにバインドされているため、現在のスコープで生成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5766-116">The signature passed to `FindMember` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="e5766-117">シグネチャは、外側のクラスまたは値の型を識別するトークンを埋め込むことができます。</span><span class="sxs-lookup"><span data-stu-id="e5766-117">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="e5766-118">トークンは、ローカルの TypeDef テーブルへのインデックスです。</span><span class="sxs-lookup"><span data-stu-id="e5766-118">The token is an index into the local TypeDef table.</span></span> <span data-ttu-id="e5766-119">現在のスコープのコンテキストの外部でランタイム シグネチャを作成し、そのシグネチャを`FindMember`入力として使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="e5766-119">You cannot build a run-time signature outside the context of the current scope and use that signature as input to input to `FindMember`.</span></span>  
  
 <span data-ttu-id="e5766-120">`FindMember`は、クラスまたはインターフェイスで直接定義されたメンバーのみを検索します。継承されたメンバーは見つかりません。</span><span class="sxs-lookup"><span data-stu-id="e5766-120">`FindMember` finds only members that were defined directly in the class or interface; it does not find inherited members.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e5766-121">`FindMember`はヘルパー メソッドです。</span><span class="sxs-lookup"><span data-stu-id="e5766-121">`FindMember` is a helper method.</span></span> <span data-ttu-id="e5766-122">を呼[び](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findmethod-method.md)出します。その呼び出しが一致を`FindMember`見つけられない場合は[、IMetaDataImport::FindField](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findfield-method.md)を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="e5766-122">It calls [IMetaDataImport::FindMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findmethod-method.md); if that call does not find a match, `FindMember` then calls [IMetaDataImport::FindField](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findfield-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5766-123">必要条件</span><span class="sxs-lookup"><span data-stu-id="e5766-123">Requirements</span></span>  
 <span data-ttu-id="e5766-124">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5766-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5766-125">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="e5766-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e5766-126">**ライブラリ:** MsCorEE.dll にリソースとして含まれる</span><span class="sxs-lookup"><span data-stu-id="e5766-126">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e5766-127">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5766-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5766-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="e5766-128">See also</span></span>

- [<span data-ttu-id="e5766-129">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e5766-129">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="e5766-130">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e5766-130">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
