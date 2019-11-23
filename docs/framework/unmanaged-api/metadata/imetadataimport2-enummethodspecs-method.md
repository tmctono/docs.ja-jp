---
title: IMetaDataImport2::EnumMethodSpecs メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.EnumMethodSpecs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::EnumMethodSpecs
helpviewer_keywords:
- IMetaDataImport2::EnumMethodSpecs method [.NET Framework metadata]
- EnumMethodSpecs method [.NET Framework metadata]
ms.assetid: b3fc1e6c-bcb6-4915-baf8-7dc0a31b8724
topic_type:
- apiref
ms.openlocfilehash: 4a1de144163ec2b4952bd16b59fb1c92b706631b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74428301"
---
# <a name="imetadataimport2enummethodspecs-method"></a><span data-ttu-id="07a1d-102">IMetaDataImport2::EnumMethodSpecs メソッド</span><span class="sxs-lookup"><span data-stu-id="07a1d-102">IMetaDataImport2::EnumMethodSpecs Method</span></span>
<span data-ttu-id="07a1d-103">Gets an enumerator for an array of MethodSpec tokens associated with the specified MethodDef or MemberRef token.</span><span class="sxs-lookup"><span data-stu-id="07a1d-103">Gets an enumerator for an array of MethodSpec tokens associated with the specified MethodDef or MemberRef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07a1d-104">構文</span><span class="sxs-lookup"><span data-stu-id="07a1d-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMethodSpecs (  
    [in, out] HCORENUM      *phEnum,   
    [in]      mdToken       tk,  
    [out]     mdMethodSpec  rMethodSpecs[],  
    [in]      ULONG         cMax,  
    [out]     ULONG         *pcMethodSpecs  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="07a1d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="07a1d-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="07a1d-106">[in, out] A pointer to the enumerator for `rMethodSpecs`.</span><span class="sxs-lookup"><span data-stu-id="07a1d-106">[in, out] A pointer to the enumerator for `rMethodSpecs`.</span></span>  
  
 `tk`  
 <span data-ttu-id="07a1d-107">[in] The MemberRef or MethodDef token that represents the method whose MethodSpec tokens are to be enumerated.</span><span class="sxs-lookup"><span data-stu-id="07a1d-107">[in] The MemberRef or MethodDef token that represents the method whose MethodSpec tokens are to be enumerated.</span></span> <span data-ttu-id="07a1d-108">If the value of `tk` is 0 (zero), all MethodSpec tokens in the scope will be enumerated.</span><span class="sxs-lookup"><span data-stu-id="07a1d-108">If the value of `tk` is 0 (zero), all MethodSpec tokens in the scope will be enumerated.</span></span>  
  
 `rMethodSpecs`  
 <span data-ttu-id="07a1d-109">[out] The array of MethodSpec tokens to enumerate.</span><span class="sxs-lookup"><span data-stu-id="07a1d-109">[out] The array of MethodSpec tokens to enumerate.</span></span>  
  
 `cMax`  
 <span data-ttu-id="07a1d-110">[in] The requested maximum number of tokens to place in `rMethodSpecs`.</span><span class="sxs-lookup"><span data-stu-id="07a1d-110">[in] The requested maximum number of tokens to place in `rMethodSpecs`.</span></span>  
  
 `pcMethodSpecs`  
 <span data-ttu-id="07a1d-111">[out] The returned number of tokens placed in `rMethodSpecs`.</span><span class="sxs-lookup"><span data-stu-id="07a1d-111">[out] The returned number of tokens placed in `rMethodSpecs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="07a1d-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="07a1d-112">Return Value</span></span>  
  
|<span data-ttu-id="07a1d-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="07a1d-113">HRESULT</span></span>|<span data-ttu-id="07a1d-114">説明</span><span class="sxs-lookup"><span data-stu-id="07a1d-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="07a1d-115">`EnumMethodSpecs` returned successfully.</span><span class="sxs-lookup"><span data-stu-id="07a1d-115">`EnumMethodSpecs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="07a1d-116">`phEnum` has no member elements.</span><span class="sxs-lookup"><span data-stu-id="07a1d-116">`phEnum` has no member elements.</span></span> <span data-ttu-id="07a1d-117">In this case, `pcMethodSpecs` is set to 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="07a1d-117">In this case, `pcMethodSpecs` is set to 0 (zero).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="07a1d-118">［要件］</span><span class="sxs-lookup"><span data-stu-id="07a1d-118">Requirements</span></span>  
 <span data-ttu-id="07a1d-119">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="07a1d-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="07a1d-120">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="07a1d-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="07a1d-121">**Library:** Used as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="07a1d-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="07a1d-122">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="07a1d-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07a1d-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="07a1d-123">See also</span></span>

- [<span data-ttu-id="07a1d-124">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="07a1d-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [<span data-ttu-id="07a1d-125">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="07a1d-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
