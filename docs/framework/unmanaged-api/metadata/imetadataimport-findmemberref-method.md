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
ms.openlocfilehash: 068014732cee91147edaec29fa0f954a741d8b5c
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84491655"
---
# <a name="imetadataimportfindmemberref-method"></a><span data-ttu-id="c7def-102">IMetaDataImport::FindMemberRef メソッド</span><span class="sxs-lookup"><span data-stu-id="c7def-102">IMetaDataImport::FindMemberRef Method</span></span>
<span data-ttu-id="c7def-103">指定した <xref:System.Type> と指定した名前とメタデータシグネチャを持つメンバー参照の MemberRef トークンへのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="c7def-103">Gets a pointer to the MemberRef token for the member reference that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7def-104">構文</span><span class="sxs-lookup"><span data-stu-id="c7def-104">Syntax</span></span>  
  
```cpp  
HRESULT FindMemberRef (  
   [in]  mdTypeRef          td,  
   [in]  LPCWSTR            szName,
   [in]  PCCOR_SIGNATURE    pvSigBlob,
   [in]  ULONG              cbSigBlob,
   [out] mdMemberRef        *pmr  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c7def-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c7def-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="c7def-106">から検索対象のメンバー参照を囲むクラスまたはインターフェイスの TypeRef トークン。</span><span class="sxs-lookup"><span data-stu-id="c7def-106">[in] The TypeRef token for the class or interface that encloses the member reference to search for.</span></span> <span data-ttu-id="c7def-107">この値がの場合 `mdTokenNil` 、グローバル変数またはグローバル関数参照に対して参照が行われます。</span><span class="sxs-lookup"><span data-stu-id="c7def-107">If this value is `mdTokenNil`, the lookup is done for a global variable or a global-function reference.</span></span>  
  
 `szName`  
 <span data-ttu-id="c7def-108">から検索対象のメンバー参照の名前。</span><span class="sxs-lookup"><span data-stu-id="c7def-108">[in] The name of the member reference to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="c7def-109">からメンバー参照のバイナリメタデータシグネチャへのポインター。</span><span class="sxs-lookup"><span data-stu-id="c7def-109">[in] A pointer to the binary metadata signature of the member reference.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="c7def-110">からのサイズ (バイト単位) `pvSigBlob` 。</span><span class="sxs-lookup"><span data-stu-id="c7def-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmr`  
 <span data-ttu-id="c7def-111">入出力一致する MemberRef トークンへのポインター。</span><span class="sxs-lookup"><span data-stu-id="c7def-111">[out] A pointer to the matching MemberRef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c7def-112">解説</span><span class="sxs-lookup"><span data-stu-id="c7def-112">Remarks</span></span>  
 <span data-ttu-id="c7def-113">メンバーは、外側のクラスまたはインターフェイス ( `td` )、その名前 ( `szName` )、および必要に応じてシグネチャ () を使用して指定し `pvSigBlob` ます。</span><span class="sxs-lookup"><span data-stu-id="c7def-113">You specify the member using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span>  
  
 <span data-ttu-id="c7def-114">署名は特定のスコープにバインドされるため、に渡されるシグネチャは、 `FindMemberRef` 現在のスコープで生成される必要があります。</span><span class="sxs-lookup"><span data-stu-id="c7def-114">The signature passed to `FindMemberRef` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="c7def-115">署名には、外側のクラスまたは値の型を識別するトークンを埋め込むことができます。</span><span class="sxs-lookup"><span data-stu-id="c7def-115">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="c7def-116">トークンは、ローカルの TypeDef テーブルのインデックスです。</span><span class="sxs-lookup"><span data-stu-id="c7def-116">The token is an index into the local TypeDef table.</span></span> <span data-ttu-id="c7def-117">現在のスコープのコンテキスト外でランタイムシグネチャを作成し、その署名をへの入力として使用することはできません `FindMemberRef` 。</span><span class="sxs-lookup"><span data-stu-id="c7def-117">You cannot build a run-time signature outside the context of the current scope and use that signature as input to `FindMemberRef`.</span></span>  
  
 <span data-ttu-id="c7def-118">`FindMemberRef`クラスまたはインターフェイスで直接定義されたメンバー参照だけを検索します。継承されたメンバー参照は見つかりません。</span><span class="sxs-lookup"><span data-stu-id="c7def-118">`FindMemberRef` finds only member references that were defined directly in the class or interface; it does not find inherited member references.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7def-119">要件</span><span class="sxs-lookup"><span data-stu-id="c7def-119">Requirements</span></span>  
 <span data-ttu-id="c7def-120">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c7def-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7def-121">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="c7def-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c7def-122">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="c7def-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c7def-123">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7def-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7def-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="c7def-124">See also</span></span>

- [<span data-ttu-id="c7def-125">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c7def-125">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="c7def-126">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c7def-126">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
