---
title: IMetaDataImport::FindMemberRef メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindMemberRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindMemberRef
helpviewer_keywords:
- IMetaDataImport::FindMemberRef method [.NET Framework metadata]
- FindMemberRef method [.NET Framework metadata]
ms.assetid: 1ccda329-d752-4d89-abe8-511af3c3f4c9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0d446e2b78f41d43aa70f429e23f1f4be22fd799
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782504"
---
# <a name="imetadataimportfindmemberref-method"></a><span data-ttu-id="bcdac-102">IMetaDataImport::FindMemberRef メソッド</span><span class="sxs-lookup"><span data-stu-id="bcdac-102">IMetaDataImport::FindMemberRef Method</span></span>
<span data-ttu-id="bcdac-103">メンバーの MemberRef トークンへのポインターの参照を取得しますが、指定したで囲まれた<xref:System.Type>指定した名前とメタデータ シグネチャを持つとします。</span><span class="sxs-lookup"><span data-stu-id="bcdac-103">Gets a pointer to the MemberRef token for the member reference that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bcdac-104">構文</span><span class="sxs-lookup"><span data-stu-id="bcdac-104">Syntax</span></span>  
  
```cpp  
HRESULT FindMemberRef (  
   [in]  mdTypeRef          td,  
   [in]  LPCWSTR            szName,   
   [in]  PCCOR_SIGNATURE    pvSigBlob,   
   [in]  ULONG              cbSigBlob,   
   [out] mdMemberRef        *pmr  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bcdac-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="bcdac-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="bcdac-106">[in]クラスまたはインターフェイスを検索するメンバーの参照を囲むの TypeRef トークンです。</span><span class="sxs-lookup"><span data-stu-id="bcdac-106">[in] The TypeRef token for the class or interface that encloses the member reference to search for.</span></span> <span data-ttu-id="bcdac-107">この値が場合`mdTokenNil`、グローバル変数またはグローバル関数の参照、検索を実行します。</span><span class="sxs-lookup"><span data-stu-id="bcdac-107">If this value is `mdTokenNil`, the lookup is done for a global variable or a global-function reference.</span></span>  
  
 `szName`  
 <span data-ttu-id="bcdac-108">[in]検索するメンバーの参照の名前。</span><span class="sxs-lookup"><span data-stu-id="bcdac-108">[in] The name of the member reference to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="bcdac-109">[in]メンバーの参照のバイナリ メタデータ シグネチャへのポインター。</span><span class="sxs-lookup"><span data-stu-id="bcdac-109">[in] A pointer to the binary metadata signature of the member reference.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="bcdac-110">[in]バイト サイズ`pvSigBlob`します。</span><span class="sxs-lookup"><span data-stu-id="bcdac-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmr`  
 <span data-ttu-id="bcdac-111">[out]一致する MemberRef トークンへのポインター。</span><span class="sxs-lookup"><span data-stu-id="bcdac-111">[out] A pointer to the matching MemberRef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bcdac-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="bcdac-112">Remarks</span></span>  
 <span data-ttu-id="bcdac-113">外側のクラスまたはインターフェイスを使用してメンバーを指定する (`td`)、その名前 (`szName`)、および必要に応じてその署名 (`pvSigBlob`)。</span><span class="sxs-lookup"><span data-stu-id="bcdac-113">You specify the member using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span>  
  
 <span data-ttu-id="bcdac-114">渡される署名`FindMemberRef`生成された現在のスコープで特定のスコープにバインドされるためです。</span><span class="sxs-lookup"><span data-stu-id="bcdac-114">The signature passed to `FindMemberRef` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="bcdac-115">署名は、外側のクラスまたは値の型を識別するトークンを埋め込むことができます。</span><span class="sxs-lookup"><span data-stu-id="bcdac-115">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="bcdac-116">トークンは、ローカルの TypeDef テーブルへのインデックスです。</span><span class="sxs-lookup"><span data-stu-id="bcdac-116">The token is an index into the local TypeDef table.</span></span> <span data-ttu-id="bcdac-117">現在のスコープのコンテキスト外にあるランタイムのシグネチャを作成してへの入力としてその署名を使用することはできません`FindMemberRef`します。</span><span class="sxs-lookup"><span data-stu-id="bcdac-117">You cannot build a run-time signature outside the context of the current scope and use that signature as input to `FindMemberRef`.</span></span>  
  
 <span data-ttu-id="bcdac-118">`FindMemberRef` クラスまたはインターフェイス内で直接定義されたメンバーの参照のみを検索します。継承されたメンバーの参照が見つかりません。</span><span class="sxs-lookup"><span data-stu-id="bcdac-118">`FindMemberRef` finds only member references that were defined directly in the class or interface; it does not find inherited member references.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bcdac-119">必要条件</span><span class="sxs-lookup"><span data-stu-id="bcdac-119">Requirements</span></span>  
 <span data-ttu-id="bcdac-120">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bcdac-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bcdac-121">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="bcdac-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bcdac-122">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="bcdac-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bcdac-123">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bcdac-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcdac-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="bcdac-124">See also</span></span>

- [<span data-ttu-id="bcdac-125">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bcdac-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="bcdac-126">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bcdac-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
