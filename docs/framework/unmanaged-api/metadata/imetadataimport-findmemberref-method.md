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
ms.openlocfilehash: d8b8bfd0e70e75c702f32555c10f433a1ff4ae10
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175422"
---
# <a name="imetadataimportfindmemberref-method"></a><span data-ttu-id="c37ac-102">IMetaDataImport::FindMemberRef メソッド</span><span class="sxs-lookup"><span data-stu-id="c37ac-102">IMetaDataImport::FindMemberRef Method</span></span>
<span data-ttu-id="c37ac-103">指定した名前とメタデータ シグネチャを持つメンバー参照の MemberRef トークン<xref:System.Type>へのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="c37ac-103">Gets a pointer to the MemberRef token for the member reference that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c37ac-104">構文</span><span class="sxs-lookup"><span data-stu-id="c37ac-104">Syntax</span></span>  
  
```cpp  
HRESULT FindMemberRef (  
   [in]  mdTypeRef          td,  
   [in]  LPCWSTR            szName,
   [in]  PCCOR_SIGNATURE    pvSigBlob,
   [in]  ULONG              cbSigBlob,
   [out] mdMemberRef        *pmr  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c37ac-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c37ac-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="c37ac-106">[in]検索するメンバー参照を囲むクラスまたはインターフェイスの TypeRef トークン。</span><span class="sxs-lookup"><span data-stu-id="c37ac-106">[in] The TypeRef token for the class or interface that encloses the member reference to search for.</span></span> <span data-ttu-id="c37ac-107">この値が`mdTokenNil`の場合、グローバル変数またはグローバル関数参照の検索が行われます。</span><span class="sxs-lookup"><span data-stu-id="c37ac-107">If this value is `mdTokenNil`, the lookup is done for a global variable or a global-function reference.</span></span>  
  
 `szName`  
 <span data-ttu-id="c37ac-108">[in]検索するメンバー参照の名前。</span><span class="sxs-lookup"><span data-stu-id="c37ac-108">[in] The name of the member reference to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="c37ac-109">[in]メンバー参照のバイナリ メタデータ シグネチャへのポインター。</span><span class="sxs-lookup"><span data-stu-id="c37ac-109">[in] A pointer to the binary metadata signature of the member reference.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="c37ac-110">[in]のサイズ (バイト`pvSigBlob`単位)</span><span class="sxs-lookup"><span data-stu-id="c37ac-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmr`  
 <span data-ttu-id="c37ac-111">[アウト]一致する MemberRef トークンへのポインター。</span><span class="sxs-lookup"><span data-stu-id="c37ac-111">[out] A pointer to the matching MemberRef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c37ac-112">解説</span><span class="sxs-lookup"><span data-stu-id="c37ac-112">Remarks</span></span>  
 <span data-ttu-id="c37ac-113">メンバーを指定するには、外側のクラスまたはインターフェイス (`td`) 、`szName`その名前 ( )`pvSigBlob`、およびオプションでそのシグネチャ ( ) を使用します。</span><span class="sxs-lookup"><span data-stu-id="c37ac-113">You specify the member using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span>  
  
 <span data-ttu-id="c37ac-114">渡された署名は`FindMemberRef`、特定のスコープにバインドされているため、現在のスコープで生成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c37ac-114">The signature passed to `FindMemberRef` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="c37ac-115">シグネチャは、外側のクラスまたは値の型を識別するトークンを埋め込むことができます。</span><span class="sxs-lookup"><span data-stu-id="c37ac-115">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="c37ac-116">トークンは、ローカルの TypeDef テーブルへのインデックスです。</span><span class="sxs-lookup"><span data-stu-id="c37ac-116">The token is an index into the local TypeDef table.</span></span> <span data-ttu-id="c37ac-117">現在のスコープのコンテキストの外部でランタイム シグネチャを作成し、そのシグネチャを への`FindMemberRef`入力として使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="c37ac-117">You cannot build a run-time signature outside the context of the current scope and use that signature as input to `FindMemberRef`.</span></span>  
  
 <span data-ttu-id="c37ac-118">`FindMemberRef`は、クラスまたはインターフェイスで直接定義されたメンバー参照のみを検索します。継承されたメンバ参照は見つかりません。</span><span class="sxs-lookup"><span data-stu-id="c37ac-118">`FindMemberRef` finds only member references that were defined directly in the class or interface; it does not find inherited member references.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c37ac-119">必要条件</span><span class="sxs-lookup"><span data-stu-id="c37ac-119">Requirements</span></span>  
 <span data-ttu-id="c37ac-120">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c37ac-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c37ac-121">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="c37ac-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c37ac-122">**ライブラリ:** MsCorEE.dll にリソースとして含まれる</span><span class="sxs-lookup"><span data-stu-id="c37ac-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c37ac-123">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c37ac-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c37ac-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="c37ac-124">See also</span></span>

- [<span data-ttu-id="c37ac-125">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c37ac-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="c37ac-126">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c37ac-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
