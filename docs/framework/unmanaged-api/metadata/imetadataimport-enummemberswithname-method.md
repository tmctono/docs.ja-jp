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
ms.openlocfilehash: ed193aab8beb0de1321aa1d52ec9f963b08b316c
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74441661"
---
# <a name="imetadataimportenummemberswithname-method"></a><span data-ttu-id="d178f-102">IMetaDataImport::EnumMembersWithName メソッド</span><span class="sxs-lookup"><span data-stu-id="d178f-102">IMetaDataImport::EnumMembersWithName Method</span></span>
<span data-ttu-id="d178f-103">指定した名前を持つ指定した型のメンバーを表す MemberDef トークンを列挙します。</span><span class="sxs-lookup"><span data-stu-id="d178f-103">Enumerates MemberDef tokens representing members of the specified type with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d178f-104">構文</span><span class="sxs-lookup"><span data-stu-id="d178f-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMembersWithName (  
   [in, out] HCORENUM    *phEnum,   
   [in]      mdTypeDef   cl,   
   [in]      LPCWSTR     szName,   
   [out]     mdToken     rMembers[],   
   [in]      ULONG       cMax,   
   [out]     ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d178f-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d178f-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="d178f-106">[in, out] A pointer to the enumerator.</span><span class="sxs-lookup"><span data-stu-id="d178f-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="d178f-107">[in] A TypeDef token representing the type with members to enumerate.</span><span class="sxs-lookup"><span data-stu-id="d178f-107">[in] A TypeDef token representing the type with members to enumerate.</span></span>  
  
 `szName`  
 <span data-ttu-id="d178f-108">[in] The member name that limits the scope of the enumerator.</span><span class="sxs-lookup"><span data-stu-id="d178f-108">[in] The member name that limits the scope of the enumerator.</span></span>  
  
 `rMembers`  
 <span data-ttu-id="d178f-109">[out] The array used to store the MemberDef tokens.</span><span class="sxs-lookup"><span data-stu-id="d178f-109">[out] The array used to store the MemberDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="d178f-110">[in] `rMembers` 配列の最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="d178f-110">[in] The maximum size of the `rMembers` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="d178f-111">[out] The actual number of MemberDef tokens returned in `rMembers`.</span><span class="sxs-lookup"><span data-stu-id="d178f-111">[out] The actual number of MemberDef tokens returned in `rMembers`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d178f-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="d178f-112">Remarks</span></span>  
 <span data-ttu-id="d178f-113">This method enumerates fields and methods, but not properties or events.</span><span class="sxs-lookup"><span data-stu-id="d178f-113">This method enumerates fields and methods, but not properties or events.</span></span> <span data-ttu-id="d178f-114">Unlike [IMetaDataImport::EnumMembers](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummembers-method.md), `EnumMembersWithName` discards all field and member tokens that do not have the specified name.</span><span class="sxs-lookup"><span data-stu-id="d178f-114">Unlike [IMetaDataImport::EnumMembers](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummembers-method.md), `EnumMembersWithName` discards all field and member tokens that do not have the specified name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d178f-115">戻り値</span><span class="sxs-lookup"><span data-stu-id="d178f-115">Return Value</span></span>  
  
|<span data-ttu-id="d178f-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d178f-116">HRESULT</span></span>|<span data-ttu-id="d178f-117">説明</span><span class="sxs-lookup"><span data-stu-id="d178f-117">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="d178f-118">`EnumTypeDefs` returned successfully.</span><span class="sxs-lookup"><span data-stu-id="d178f-118">`EnumTypeDefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="d178f-119">There are no MemberDef tokens to enumerate.</span><span class="sxs-lookup"><span data-stu-id="d178f-119">There are no MemberDef tokens to enumerate.</span></span> <span data-ttu-id="d178f-120">In that case, `pcTokens` is zero.</span><span class="sxs-lookup"><span data-stu-id="d178f-120">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d178f-121">［要件］</span><span class="sxs-lookup"><span data-stu-id="d178f-121">Requirements</span></span>  
 <span data-ttu-id="d178f-122">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d178f-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d178f-123">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d178f-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d178f-124">**Library:** Included as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d178f-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d178f-125">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d178f-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d178f-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="d178f-126">See also</span></span>

- [<span data-ttu-id="d178f-127">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d178f-127">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="d178f-128">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d178f-128">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
