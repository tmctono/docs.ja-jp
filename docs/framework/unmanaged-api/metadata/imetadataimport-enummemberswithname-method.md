---
title: IMetaDataImport::EnumMembersWithName メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMembersWithName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMembersWithName
helpviewer_keywords:
- IMetaDataImport::EnumMembersWithName method [.NET Framework metadata]
- EnumMembersWithName method [.NET Framework metadata]
ms.assetid: 7c9e9120-3104-42f0-86ce-19a025f20dcc
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c2509945d2799b81e036888d146a51cee87fda09
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59169846"
---
# <a name="imetadataimportenummemberswithname-method"></a><span data-ttu-id="19de4-102">IMetaDataImport::EnumMembersWithName メソッド</span><span class="sxs-lookup"><span data-stu-id="19de4-102">IMetaDataImport::EnumMembersWithName Method</span></span>
<span data-ttu-id="19de4-103">指定した名前を持つ指定した型のメンバーを表す MemberDef トークンを列挙します。</span><span class="sxs-lookup"><span data-stu-id="19de4-103">Enumerates MemberDef tokens representing members of the specified type with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19de4-104">構文</span><span class="sxs-lookup"><span data-stu-id="19de4-104">Syntax</span></span>  
  
```  
HRESULT EnumMembersWithName (  
   [in, out] HCORENUM    *phEnum,   
   [in]      mdTypeDef   cl,   
   [in]      LPCWSTR     szName,   
   [out]     mdToken     rMembers[],   
   [in]      ULONG       cMax,   
   [out]     ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="19de4-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="19de4-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="19de4-106">[入力、出力]列挙子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="19de4-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="19de4-107">[in]列挙のメンバーを持つ型を表す TypeDef トークンです。</span><span class="sxs-lookup"><span data-stu-id="19de4-107">[in] A TypeDef token representing the type with members to enumerate.</span></span>  
  
 `szName`  
 <span data-ttu-id="19de4-108">[in]列挙子のスコープを制限するメンバーの名前。</span><span class="sxs-lookup"><span data-stu-id="19de4-108">[in] The member name that limits the scope of the enumerator.</span></span>  
  
 `rMembers`  
 <span data-ttu-id="19de4-109">[out]MemberDef トークンを格納するために使用する配列。</span><span class="sxs-lookup"><span data-stu-id="19de4-109">[out] The array used to store the MemberDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="19de4-110">[in] `rMembers` 配列の最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="19de4-110">[in] The maximum size of the `rMembers` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="19de4-111">[out]実際に返される MemberDef トークン数`rMembers`します。</span><span class="sxs-lookup"><span data-stu-id="19de4-111">[out] The actual number of MemberDef tokens returned in `rMembers`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="19de4-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="19de4-112">Remarks</span></span>  
 <span data-ttu-id="19de4-113">このメソッドは、フィールドと、メソッドがないプロパティまたはイベントを列挙します。</span><span class="sxs-lookup"><span data-stu-id="19de4-113">This method enumerates fields and methods, but not properties or events.</span></span> <span data-ttu-id="19de4-114">異なり[imetadataimport::enummembers](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummembers-method.md)、`EnumMembersWithName`指定した名前がないすべてのフィールドとメンバーのトークンを破棄します。</span><span class="sxs-lookup"><span data-stu-id="19de4-114">Unlike [IMetaDataImport::EnumMembers](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummembers-method.md), `EnumMembersWithName` discards all field and member tokens that do not have the specified name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="19de4-115">戻り値</span><span class="sxs-lookup"><span data-stu-id="19de4-115">Return Value</span></span>  
  
|<span data-ttu-id="19de4-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="19de4-116">HRESULT</span></span>|<span data-ttu-id="19de4-117">説明</span><span class="sxs-lookup"><span data-stu-id="19de4-117">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|`EnumTypeDefs` <span data-ttu-id="19de4-118">正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="19de4-118">returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="19de4-119">MemberDef トークンを列挙することはありません。</span><span class="sxs-lookup"><span data-stu-id="19de4-119">There are no MemberDef tokens to enumerate.</span></span> <span data-ttu-id="19de4-120">その場合は、`pcTokens`は 0 です。</span><span class="sxs-lookup"><span data-stu-id="19de4-120">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="19de4-121">必要条件</span><span class="sxs-lookup"><span data-stu-id="19de4-121">Requirements</span></span>  
 <span data-ttu-id="19de4-122">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="19de4-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19de4-123">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="19de4-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="19de4-124">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="19de4-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="19de4-125">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="19de4-125">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="19de4-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="19de4-126">See also</span></span>

- [<span data-ttu-id="19de4-127">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="19de4-127">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="19de4-128">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="19de4-128">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
