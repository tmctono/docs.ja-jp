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
ms.openlocfilehash: 7a46fa5319a1badc0cf28dcdbf535a6ed017c9c9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437917"
---
# <a name="imetadataimportfindmember-method"></a><span data-ttu-id="d417d-102">IMetaDataImport::FindMember メソッド</span><span class="sxs-lookup"><span data-stu-id="d417d-102">IMetaDataImport::FindMember Method</span></span>
<span data-ttu-id="d417d-103">指定した <xref:System.Type> で囲まれ、指定された名前とメタデータシグネチャを持つフィールドまたはメソッドの MemberDef トークンへのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="d417d-103">Gets a pointer to the MemberDef token for field or method that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d417d-104">構文</span><span class="sxs-lookup"><span data-stu-id="d417d-104">Syntax</span></span>  
  
```cpp  
HRESULT FindMember (  
   [in]  mdTypeDef         td,  
   [in]  LPCWSTR           szName,   
   [in]  PCCOR_SIGNATURE   pvSigBlob,   
   [in]  ULONG             cbSigBlob,   
   [out] mdToken           *pmb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d417d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d417d-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="d417d-106">から検索対象のメンバーを囲むクラスまたはインターフェイスの TypeDef トークン。</span><span class="sxs-lookup"><span data-stu-id="d417d-106">[in] The TypeDef token for the class or interface that encloses the member to search for.</span></span> <span data-ttu-id="d417d-107">この値が `mdTokenNil`場合は、グローバル変数またはグローバル関数の参照が行われます。</span><span class="sxs-lookup"><span data-stu-id="d417d-107">If this value is `mdTokenNil`, the lookup is done for a global-variable or global-function.</span></span>  
  
 `szName`  
 <span data-ttu-id="d417d-108">から検索対象のメンバーの名前。</span><span class="sxs-lookup"><span data-stu-id="d417d-108">[in] The name of the member to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="d417d-109">からメンバーのバイナリメタデータシグネチャへのポインター。</span><span class="sxs-lookup"><span data-stu-id="d417d-109">[in] A pointer to the binary metadata signature of the member.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="d417d-110">から`pvSigBlob`のサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="d417d-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmb`  
 <span data-ttu-id="d417d-111">入出力一致する MemberDef トークンへのポインター。</span><span class="sxs-lookup"><span data-stu-id="d417d-111">[out] A pointer to the matching MemberDef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d417d-112">コメント</span><span class="sxs-lookup"><span data-stu-id="d417d-112">Remarks</span></span>  
 <span data-ttu-id="d417d-113">メンバーは、外側のクラスまたはインターフェイス (`td`)、その名前 (`szName`)、および必要に応じてシグネチャ (`pvSigBlob`) を使用して指定します。</span><span class="sxs-lookup"><span data-stu-id="d417d-113">You specify the member using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span> <span data-ttu-id="d417d-114">クラスまたはインターフェイスに同じ名前のメンバーが複数存在する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d417d-114">There might be multiple members with the same name in a class or interface.</span></span> <span data-ttu-id="d417d-115">その場合は、メンバーのシグネチャを渡して、一意の一致を検索します。</span><span class="sxs-lookup"><span data-stu-id="d417d-115">In that case, pass the member's signature to find the unique match.</span></span>  
  
 <span data-ttu-id="d417d-116">シグネチャは特定のスコープにバインドされているため、`FindMember` に渡される署名は、現在のスコープで生成される必要があります。</span><span class="sxs-lookup"><span data-stu-id="d417d-116">The signature passed to `FindMember` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="d417d-117">署名には、外側のクラスまたは値の型を識別するトークンを埋め込むことができます。</span><span class="sxs-lookup"><span data-stu-id="d417d-117">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="d417d-118">トークンは、ローカルの TypeDef テーブルのインデックスです。</span><span class="sxs-lookup"><span data-stu-id="d417d-118">The token is an index into the local TypeDef table.</span></span> <span data-ttu-id="d417d-119">現在のスコープのコンテキスト外でランタイムシグネチャを作成し、その署名を入力として使用して `FindMember`することはできません。</span><span class="sxs-lookup"><span data-stu-id="d417d-119">You cannot build a run-time signature outside the context of the current scope and use that signature as input to input to `FindMember`.</span></span>  
  
 <span data-ttu-id="d417d-120">`FindMember` は、クラスまたはインターフェイスで直接定義されたメンバーのみを検索します。継承されたメンバーは見つかりません。</span><span class="sxs-lookup"><span data-stu-id="d417d-120">`FindMember` finds only members that were defined directly in the class or interface; it does not find inherited members.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d417d-121">`FindMember` はヘルパーメソッドです。</span><span class="sxs-lookup"><span data-stu-id="d417d-121">`FindMember` is a helper method.</span></span> <span data-ttu-id="d417d-122">[IMetaDataImport:: FindMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findmethod-method.md); を呼び出します。この呼び出しで一致するものが見つからない場合は、`FindMember` [IMetaDataImport:: FindField](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findfield-method.md)を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="d417d-122">It calls [IMetaDataImport::FindMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findmethod-method.md); if that call does not find a match, `FindMember` then calls [IMetaDataImport::FindField](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findfield-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d417d-123">要件</span><span class="sxs-lookup"><span data-stu-id="d417d-123">Requirements</span></span>  
 <span data-ttu-id="d417d-124">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d417d-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d417d-125">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="d417d-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d417d-126">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="d417d-126">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d417d-127">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d417d-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d417d-128">参照</span><span class="sxs-lookup"><span data-stu-id="d417d-128">See also</span></span>

- [<span data-ttu-id="d417d-129">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d417d-129">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="d417d-130">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d417d-130">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
