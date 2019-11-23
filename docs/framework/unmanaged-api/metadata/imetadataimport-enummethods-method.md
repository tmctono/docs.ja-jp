---
title: IMetaDataImport::EnumMethods メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMethods
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMethods
helpviewer_keywords:
- IMetaDataImport::EnumMethods method [.NET Framework metadata]
- EnumMethods method [.NET Framework metadata]
ms.assetid: 8cc3b0c3-d97d-4f71-9e7d-ef2a92b4959a
topic_type:
- apiref
ms.openlocfilehash: 8e9e08ac903423b2e121f22cc9e43a660ccfac7b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450088"
---
# <a name="imetadataimportenummethods-method"></a><span data-ttu-id="74135-102">IMetaDataImport::EnumMethods メソッド</span><span class="sxs-lookup"><span data-stu-id="74135-102">IMetaDataImport::EnumMethods Method</span></span>
<span data-ttu-id="74135-103">指定した型のメソッドを表す MethodDef トークンを列挙します。</span><span class="sxs-lookup"><span data-stu-id="74135-103">Enumerates MethodDef tokens representing methods of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74135-104">構文</span><span class="sxs-lookup"><span data-stu-id="74135-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMethods (  
   [in, out] HCORENUM   *phEnum,   
   [in]  mdTypeDef      cl,   
   [out] mdMethodDef    rMethods[],   
   [in]  ULONG          cMax,   
   [out] ULONG          *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="74135-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="74135-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="74135-106">[in, out] A pointer to the enumerator.</span><span class="sxs-lookup"><span data-stu-id="74135-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="74135-107">This must be NULL for the first call of this method.</span><span class="sxs-lookup"><span data-stu-id="74135-107">This must be NULL for the first call of this method.</span></span>  
  
 `cl`  
 <span data-ttu-id="74135-108">[in] A TypeDef token representing the type with the methods to enumerate.</span><span class="sxs-lookup"><span data-stu-id="74135-108">[in] A TypeDef token representing the type with the methods to enumerate.</span></span>  
  
 `rMethods`  
 <span data-ttu-id="74135-109">[out] The array to store the MethodDef tokens.</span><span class="sxs-lookup"><span data-stu-id="74135-109">[out] The array to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="74135-110">[in] The maximum size of the MethodDef `rMethods` array.</span><span class="sxs-lookup"><span data-stu-id="74135-110">[in] The maximum size of the MethodDef `rMethods` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="74135-111">[out] The number of MethodDef tokens returned in `rMethods`.</span><span class="sxs-lookup"><span data-stu-id="74135-111">[out] The number of MethodDef tokens returned in `rMethods`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="74135-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="74135-112">Return Value</span></span>  
  
|<span data-ttu-id="74135-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="74135-113">HRESULT</span></span>|<span data-ttu-id="74135-114">説明</span><span class="sxs-lookup"><span data-stu-id="74135-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="74135-115">`EnumMethods` returned successfully.</span><span class="sxs-lookup"><span data-stu-id="74135-115">`EnumMethods` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="74135-116">There are no MethodDef tokens to enumerate.</span><span class="sxs-lookup"><span data-stu-id="74135-116">There are no MethodDef tokens to enumerate.</span></span> <span data-ttu-id="74135-117">In that case, `pcTokens` is zero.</span><span class="sxs-lookup"><span data-stu-id="74135-117">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="74135-118">［要件］</span><span class="sxs-lookup"><span data-stu-id="74135-118">Requirements</span></span>  
 <span data-ttu-id="74135-119">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="74135-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74135-120">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="74135-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="74135-121">**Library:** Included as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="74135-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="74135-122">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74135-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74135-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="74135-123">See also</span></span>

- [<span data-ttu-id="74135-124">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="74135-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="74135-125">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="74135-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
