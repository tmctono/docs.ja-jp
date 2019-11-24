---
title: IMetaDataImport::EnumModuleRefs メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumModuleRefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumModuleRefs
helpviewer_keywords:
- EnumModuleRefs method [.NET Framework metadata]
- IMetaDataImport::EnumModuleRefs method [.NET Framework metadata]
ms.assetid: 53441f3a-68d2-477c-906e-37c55dfcfb4d
topic_type:
- apiref
ms.openlocfilehash: 66186d25e8fee0d6b25c0a2069d46ff9a104c625
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450039"
---
# <a name="imetadataimportenummodulerefs-method"></a><span data-ttu-id="b442e-102">IMetaDataImport::EnumModuleRefs メソッド</span><span class="sxs-lookup"><span data-stu-id="b442e-102">IMetaDataImport::EnumModuleRefs Method</span></span>
<span data-ttu-id="b442e-103">インポートされたモジュールを表す ModuleRef トークンを列挙します。</span><span class="sxs-lookup"><span data-stu-id="b442e-103">Enumerates ModuleRef tokens that represent imported modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b442e-104">構文</span><span class="sxs-lookup"><span data-stu-id="b442e-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumModuleRefs (  
   [in, out] HCORENUM     *phEnum,  
   [out]     mdModuleRef  rModuleRefs[],  
   [in]      ULONG        cMax,  
   [out]     ULONG        *pcModuleRefs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b442e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b442e-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="b442e-106">[in, out] A pointer to the enumerator.</span><span class="sxs-lookup"><span data-stu-id="b442e-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="b442e-107">This must be NULL for the first call of this method.</span><span class="sxs-lookup"><span data-stu-id="b442e-107">This must be NULL for the first call of this method.</span></span>  
  
 `rModuleRefs`  
 <span data-ttu-id="b442e-108">[out] The array used to store the ModuleRef tokens.</span><span class="sxs-lookup"><span data-stu-id="b442e-108">[out] The array used to store the ModuleRef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="b442e-109">[in] `rModuleRefs` 配列の最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="b442e-109">[in] The maximum size of the `rModuleRefs` array.</span></span>  
  
 `pcModuleRefs`  
 <span data-ttu-id="b442e-110">[out] The number of ModuleRef tokens returned in `rModuleRefs`.</span><span class="sxs-lookup"><span data-stu-id="b442e-110">[out] The number of ModuleRef tokens returned in `rModuleRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b442e-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="b442e-111">Return Value</span></span>  
  
|<span data-ttu-id="b442e-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b442e-112">HRESULT</span></span>|<span data-ttu-id="b442e-113">説明</span><span class="sxs-lookup"><span data-stu-id="b442e-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="b442e-114">`EnumModuleRefs` returned successfully.</span><span class="sxs-lookup"><span data-stu-id="b442e-114">`EnumModuleRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="b442e-115">There are no tokens to enumerate.</span><span class="sxs-lookup"><span data-stu-id="b442e-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="b442e-116">In that case, `pcModuleRefs` is zero.</span><span class="sxs-lookup"><span data-stu-id="b442e-116">In that case, `pcModuleRefs` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b442e-117">［要件］</span><span class="sxs-lookup"><span data-stu-id="b442e-117">Requirements</span></span>  
 <span data-ttu-id="b442e-118">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b442e-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b442e-119">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b442e-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b442e-120">**Library:** Included as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b442e-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b442e-121">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b442e-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b442e-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="b442e-122">See also</span></span>

- [<span data-ttu-id="b442e-123">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b442e-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="b442e-124">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b442e-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
