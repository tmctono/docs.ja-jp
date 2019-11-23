---
title: IMetaDataImport::FindTypeRef メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindTypeRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindTypeRef
helpviewer_keywords:
- IMetaDataImport::FindTypeRef method [.NET Framework metadata]
- FindTypeRef method [.NET Framework metadata]
ms.assetid: 1b2bbf3f-943e-412e-b66c-e802431b055c
topic_type:
- apiref
ms.openlocfilehash: 21a69d120cc732ca6659f77abc9f8ea0c993271e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437787"
---
# <a name="imetadataimportfindtyperef-method"></a><span data-ttu-id="7a2d3-102">IMetaDataImport::FindTypeRef メソッド</span><span class="sxs-lookup"><span data-stu-id="7a2d3-102">IMetaDataImport::FindTypeRef Method</span></span>
<span data-ttu-id="7a2d3-103">Gets a pointer to the TypeRef token for the <xref:System.Type> reference that is in the specified scope and that has the specified name.</span><span class="sxs-lookup"><span data-stu-id="7a2d3-103">Gets a pointer to the TypeRef token for the <xref:System.Type> reference that is in the specified scope and that has the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a2d3-104">構文</span><span class="sxs-lookup"><span data-stu-id="7a2d3-104">Syntax</span></span>  
  
```cpp  
HRESULT FindTypeRef (  
   [in] mdToken        tkResolutionScope,  
   [in]  LPCWSTR       szName,  
   [out] mdTypeRef     *ptr  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7a2d3-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7a2d3-105">Parameters</span></span>  
 `tkResolutionScope`  
 <span data-ttu-id="7a2d3-106">[in] A ModuleRef, AssemblyRef, or TypeRef token that specifies the module, assembly, or type, respectively, in which the type reference is defined.</span><span class="sxs-lookup"><span data-stu-id="7a2d3-106">[in] A ModuleRef, AssemblyRef, or TypeRef token that specifies the module, assembly, or type, respectively, in which the type reference is defined.</span></span>  
  
 `szName`  
 <span data-ttu-id="7a2d3-107">[in] The name of the type reference to search for.</span><span class="sxs-lookup"><span data-stu-id="7a2d3-107">[in] The name of the type reference to search for.</span></span>  
  
 `ptr`  
 <span data-ttu-id="7a2d3-108">[out] A pointer to the matching TypeRef token.</span><span class="sxs-lookup"><span data-stu-id="7a2d3-108">[out] A pointer to the matching TypeRef token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7a2d3-109">［要件］</span><span class="sxs-lookup"><span data-stu-id="7a2d3-109">Requirements</span></span>  
 <span data-ttu-id="7a2d3-110">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a2d3-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7a2d3-111">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7a2d3-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7a2d3-112">**Library:** Included as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7a2d3-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7a2d3-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7a2d3-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a2d3-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="7a2d3-114">See also</span></span>

- [<span data-ttu-id="7a2d3-115">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7a2d3-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="7a2d3-116">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7a2d3-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
