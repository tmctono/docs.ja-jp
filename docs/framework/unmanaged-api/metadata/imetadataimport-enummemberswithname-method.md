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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62042719"
---
# <a name="imetadataimportenummemberswithname-method"></a><span data-ttu-id="46ace-102">IMetaDataImport::EnumMembersWithName メソッド</span><span class="sxs-lookup"><span data-stu-id="46ace-102">IMetaDataImport::EnumMembersWithName Method</span></span>
<span data-ttu-id="46ace-103">指定した名前を持つ指定した型のメンバーを表す MemberDef トークンを列挙します。</span><span class="sxs-lookup"><span data-stu-id="46ace-103">Enumerates MemberDef tokens representing members of the specified type with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46ace-104">構文</span><span class="sxs-lookup"><span data-stu-id="46ace-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="46ace-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="46ace-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="46ace-106">[入力、出力]列挙子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="46ace-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="46ace-107">[in]列挙のメンバーを持つ型を表す TypeDef トークンです。</span><span class="sxs-lookup"><span data-stu-id="46ace-107">[in] A TypeDef token representing the type with members to enumerate.</span></span>  
  
 `szName`  
 <span data-ttu-id="46ace-108">[in]列挙子のスコープを制限するメンバーの名前。</span><span class="sxs-lookup"><span data-stu-id="46ace-108">[in] The member name that limits the scope of the enumerator.</span></span>  
  
 `rMembers`  
 <span data-ttu-id="46ace-109">[out]MemberDef トークンを格納するために使用する配列。</span><span class="sxs-lookup"><span data-stu-id="46ace-109">[out] The array used to store the MemberDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="46ace-110">[in] `rMembers` 配列の最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="46ace-110">[in] The maximum size of the `rMembers` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="46ace-111">[out]実際に返される MemberDef トークン数`rMembers`します。</span><span class="sxs-lookup"><span data-stu-id="46ace-111">[out] The actual number of MemberDef tokens returned in `rMembers`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="46ace-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="46ace-112">Remarks</span></span>  
 <span data-ttu-id="46ace-113">このメソッドは、フィールドと、メソッドがないプロパティまたはイベントを列挙します。</span><span class="sxs-lookup"><span data-stu-id="46ace-113">This method enumerates fields and methods, but not properties or events.</span></span> <span data-ttu-id="46ace-114">異なり[imetadataimport::enummembers](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummembers-method.md)、`EnumMembersWithName`指定した名前がないすべてのフィールドとメンバーのトークンを破棄します。</span><span class="sxs-lookup"><span data-stu-id="46ace-114">Unlike [IMetaDataImport::EnumMembers](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummembers-method.md), `EnumMembersWithName` discards all field and member tokens that do not have the specified name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="46ace-115">戻り値</span><span class="sxs-lookup"><span data-stu-id="46ace-115">Return Value</span></span>  
  
|<span data-ttu-id="46ace-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="46ace-116">HRESULT</span></span>|<span data-ttu-id="46ace-117">説明</span><span class="sxs-lookup"><span data-stu-id="46ace-117">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="46ace-118">`EnumTypeDefs` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="46ace-118">`EnumTypeDefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="46ace-119">MemberDef トークンを列挙することはありません。</span><span class="sxs-lookup"><span data-stu-id="46ace-119">There are no MemberDef tokens to enumerate.</span></span> <span data-ttu-id="46ace-120">その場合は、`pcTokens`は 0 です。</span><span class="sxs-lookup"><span data-stu-id="46ace-120">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="46ace-121">必要条件</span><span class="sxs-lookup"><span data-stu-id="46ace-121">Requirements</span></span>  
 <span data-ttu-id="46ace-122">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="46ace-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46ace-123">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="46ace-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="46ace-124">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="46ace-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="46ace-125">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="46ace-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46ace-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="46ace-126">See also</span></span>

- [<span data-ttu-id="46ace-127">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="46ace-127">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="46ace-128">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="46ace-128">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
