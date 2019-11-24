---
title: IMetaDataImport::EnumUnresolvedMethods メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumUnresolvedMethods
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumUnresolvedMethods
helpviewer_keywords:
- EnumUnresolvedMethods method [.NET Framework metadata]
- IMetaDataImport::EnumUnresolvedMethods method [.NET Framework metadata]
ms.assetid: eb3187d7-74cf-44b1-aeeb-7a8d2b60e3b7
topic_type:
- apiref
ms.openlocfilehash: ff9827174e43fd62f3a995e9f477c6fff66b227a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449958"
---
# <a name="imetadataimportenumunresolvedmethods-method"></a><span data-ttu-id="2fb5c-102">IMetaDataImport::EnumUnresolvedMethods メソッド</span><span class="sxs-lookup"><span data-stu-id="2fb5c-102">IMetaDataImport::EnumUnresolvedMethods Method</span></span>
<span data-ttu-id="2fb5c-103">現在のメタデータ スコープ内の未解決のメソッドを表す MemberDef トークンを列挙します。</span><span class="sxs-lookup"><span data-stu-id="2fb5c-103">Enumerates MemberDef tokens representing the unresolved methods in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2fb5c-104">構文</span><span class="sxs-lookup"><span data-stu-id="2fb5c-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumUnresolvedMethods (  
   [in, out] HCORENUM    *phEnum,  
   [out]     mdToken     rMethods[],  
   [in]      ULONG       cMax,  
   [out]     ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2fb5c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2fb5c-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="2fb5c-106">[in, out] A pointer to the enumerator.</span><span class="sxs-lookup"><span data-stu-id="2fb5c-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="2fb5c-107">This must be NULL for the first call of this method.</span><span class="sxs-lookup"><span data-stu-id="2fb5c-107">This must be NULL for the first call of this method.</span></span>  
  
 `rMethods`  
 <span data-ttu-id="2fb5c-108">[out] The array used to store the MemberDef tokens.</span><span class="sxs-lookup"><span data-stu-id="2fb5c-108">[out] The array used to store the MemberDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="2fb5c-109">[in] `rMethods` 配列の最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="2fb5c-109">[in] The maximum size of the `rMethods` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="2fb5c-110">[out] The number of MemberDef tokens returned in `rMethods`.</span><span class="sxs-lookup"><span data-stu-id="2fb5c-110">[out] The number of MemberDef tokens returned in `rMethods`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2fb5c-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="2fb5c-111">Return Value</span></span>  
  
|<span data-ttu-id="2fb5c-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2fb5c-112">HRESULT</span></span>|<span data-ttu-id="2fb5c-113">説明</span><span class="sxs-lookup"><span data-stu-id="2fb5c-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="2fb5c-114">`EnumUnresolvedMethods` returned successfully.</span><span class="sxs-lookup"><span data-stu-id="2fb5c-114">`EnumUnresolvedMethods` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="2fb5c-115">There are no tokens to enumerate.</span><span class="sxs-lookup"><span data-stu-id="2fb5c-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="2fb5c-116">In that case, `pcTokens` is zero.</span><span class="sxs-lookup"><span data-stu-id="2fb5c-116">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2fb5c-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="2fb5c-117">Remarks</span></span>  
 <span data-ttu-id="2fb5c-118">An unresolved method is one that has been declared but not implemented.</span><span class="sxs-lookup"><span data-stu-id="2fb5c-118">An unresolved method is one that has been declared but not implemented.</span></span> <span data-ttu-id="2fb5c-119">A method is included in the enumeration if the method is marked `miForwardRef` and either `mdPinvokeImpl` or `miRuntime` is set to zero.</span><span class="sxs-lookup"><span data-stu-id="2fb5c-119">A method is included in the enumeration if the method is marked `miForwardRef` and either `mdPinvokeImpl` or `miRuntime` is set to zero.</span></span> <span data-ttu-id="2fb5c-120">In other words, an unresolved method is a class method that is marked `miForwardRef` but which is not implemented in unmanaged code (reached via PInvoke) nor implemented internally by the runtime itself</span><span class="sxs-lookup"><span data-stu-id="2fb5c-120">In other words, an unresolved method is a class method that is marked `miForwardRef` but which is not implemented in unmanaged code (reached via PInvoke) nor implemented internally by the runtime itself</span></span>  
  
 <span data-ttu-id="2fb5c-121">The enumeration excludes all methods that are defined either at module scope (globals) or in interfaces or abstract classes.</span><span class="sxs-lookup"><span data-stu-id="2fb5c-121">The enumeration excludes all methods that are defined either at module scope (globals) or in interfaces or abstract classes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2fb5c-122">［要件］</span><span class="sxs-lookup"><span data-stu-id="2fb5c-122">Requirements</span></span>  
 <span data-ttu-id="2fb5c-123">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2fb5c-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2fb5c-124">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="2fb5c-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2fb5c-125">**Library:** Included as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2fb5c-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2fb5c-126">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2fb5c-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fb5c-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="2fb5c-127">See also</span></span>

- [<span data-ttu-id="2fb5c-128">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2fb5c-128">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="2fb5c-129">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2fb5c-129">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
