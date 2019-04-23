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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 63afd82ca88e1a7c61913ec7fcc4d77d03ae9927
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59183171"
---
# <a name="imetadataimportfindmember-method"></a><span data-ttu-id="5047b-102">IMetaDataImport::FindMember メソッド</span><span class="sxs-lookup"><span data-stu-id="5047b-102">IMetaDataImport::FindMember Method</span></span>
<span data-ttu-id="5047b-103">フィールドまたは囲まれたメソッドの memberdef にポインターをトークン取得を指定した<xref:System.Type>指定した名前とメタデータ シグネチャを持つとします。</span><span class="sxs-lookup"><span data-stu-id="5047b-103">Gets a pointer to the MemberDef token for field or method that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5047b-104">構文</span><span class="sxs-lookup"><span data-stu-id="5047b-104">Syntax</span></span>  
  
```  
HRESULT FindMember (  
   [in]  mdTypeDef         td,  
   [in]  LPCWSTR           szName,   
   [in]  PCCOR_SIGNATURE   pvSigBlob,   
   [in]  ULONG             cbSigBlob,   
   [out] mdToken           *pmb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5047b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5047b-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="5047b-106">[in]クラスまたはインターフェイスを検索するメンバーを囲む TypeDef トークンです。</span><span class="sxs-lookup"><span data-stu-id="5047b-106">[in] The TypeDef token for the class or interface that encloses the member to search for.</span></span> <span data-ttu-id="5047b-107">この値が場合`mdTokenNil`、グローバル変数またはグローバル関数、検索を実行します。</span><span class="sxs-lookup"><span data-stu-id="5047b-107">If this value is `mdTokenNil`, the lookup is done for a global-variable or global-function.</span></span>  
  
 `szName`  
 <span data-ttu-id="5047b-108">[in]検索するメンバーの名前。</span><span class="sxs-lookup"><span data-stu-id="5047b-108">[in] The name of the member to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="5047b-109">[in]メンバーのバイナリ メタデータ シグネチャへのポインター。</span><span class="sxs-lookup"><span data-stu-id="5047b-109">[in] A pointer to the binary metadata signature of the member.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="5047b-110">[in]バイト サイズ`pvSigBlob`します。</span><span class="sxs-lookup"><span data-stu-id="5047b-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmb`  
 <span data-ttu-id="5047b-111">[out]一致する MemberDef トークンへのポインター。</span><span class="sxs-lookup"><span data-stu-id="5047b-111">[out] A pointer to the matching MemberDef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5047b-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="5047b-112">Remarks</span></span>  
 <span data-ttu-id="5047b-113">外側のクラスまたはインターフェイスを使用してメンバーを指定する (`td`)、その名前 (`szName`)、および必要に応じてその署名 (`pvSigBlob`)。</span><span class="sxs-lookup"><span data-stu-id="5047b-113">You specify the member using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span> <span data-ttu-id="5047b-114">クラスまたはインターフェイスで同じ名前の複数のメンバーである可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5047b-114">There might be multiple members with the same name in a class or interface.</span></span> <span data-ttu-id="5047b-115">その場合は、一意の一致を検索するメンバーのシグネチャを渡します。</span><span class="sxs-lookup"><span data-stu-id="5047b-115">In that case, pass the member's signature to find the unique match.</span></span>  
  
 <span data-ttu-id="5047b-116">渡される署名`FindMember`生成された現在のスコープで特定のスコープにバインドされるためです。</span><span class="sxs-lookup"><span data-stu-id="5047b-116">The signature passed to `FindMember` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="5047b-117">署名は、外側のクラスまたは値の型を識別するトークンを埋め込むことができます。</span><span class="sxs-lookup"><span data-stu-id="5047b-117">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="5047b-118">トークンは、ローカルの TypeDef テーブルへのインデックスです。</span><span class="sxs-lookup"><span data-stu-id="5047b-118">The token is an index into the local TypeDef table.</span></span> <span data-ttu-id="5047b-119">現在のスコープのコンテキスト外にある実行時シグネチャを作成してを入力としてその署名を使用することはできません`FindMember`します。</span><span class="sxs-lookup"><span data-stu-id="5047b-119">You cannot build a run-time signature outside the context of the current scope and use that signature as input to input to `FindMember`.</span></span>  
  
 <span data-ttu-id="5047b-120">`FindMember` クラスまたはインターフェイス内で直接定義されたメンバーのみを検索します継承されたメンバーは検索しません。</span><span class="sxs-lookup"><span data-stu-id="5047b-120">`FindMember` finds only members that were defined directly in the class or interface; it does not find inherited members.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5047b-121">`FindMember` ヘルパー メソッドです。</span><span class="sxs-lookup"><span data-stu-id="5047b-121">`FindMember` is a helper method.</span></span> <span data-ttu-id="5047b-122">呼び出す[imetadataimport::findmethod](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findmethod-method.md)その呼び出しには、一致が見つからない場合は`FindMember`呼び出して[imetadataimport::findfield](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findfield-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="5047b-122">It calls [IMetaDataImport::FindMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findmethod-method.md); if that call does not find a match, `FindMember` then calls [IMetaDataImport::FindField](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findfield-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5047b-123">必要条件</span><span class="sxs-lookup"><span data-stu-id="5047b-123">Requirements</span></span>  
 <span data-ttu-id="5047b-124">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5047b-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5047b-125">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5047b-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5047b-126">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="5047b-126">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5047b-127">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5047b-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5047b-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="5047b-128">See also</span></span>

- [<span data-ttu-id="5047b-129">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5047b-129">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="5047b-130">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5047b-130">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
