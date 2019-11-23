---
title: IMetaDataEmit::SetRVA メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetRVA
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetRVA
helpviewer_keywords:
- IMetaDataEmit::SetRVA method [.NET Framework metadata]
- SetRVA method [.NET Framework metadata]
ms.assetid: 4d69fb6d-ee35-4318-8224-5eea2bd16818
topic_type:
- apiref
ms.openlocfilehash: 0a1d244a4bf077970d2031c3c3b2bc56a0dd3d79
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74426815"
---
# <a name="imetadataemitsetrva-method"></a><span data-ttu-id="844b1-102">IMetaDataEmit::SetRVA メソッド</span><span class="sxs-lookup"><span data-stu-id="844b1-102">IMetaDataEmit::SetRVA Method</span></span>
<span data-ttu-id="844b1-103">Sets the relative virtual address of the specified method.</span><span class="sxs-lookup"><span data-stu-id="844b1-103">Sets the relative virtual address of the specified method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="844b1-104">構文</span><span class="sxs-lookup"><span data-stu-id="844b1-104">Syntax</span></span>  
  
```cpp  
HRESULT SetRVA (  
    [in]  mdMethodDef  md,   
    [in]  ULONG        ulRVA   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="844b1-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="844b1-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="844b1-106">[in] The token for the target method or method implementation.</span><span class="sxs-lookup"><span data-stu-id="844b1-106">[in] The token for the target method or method implementation.</span></span>  
  
 `ulRVA`  
 <span data-ttu-id="844b1-107">[in] The address of the code or data area.</span><span class="sxs-lookup"><span data-stu-id="844b1-107">[in] The address of the code or data area.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="844b1-108">［要件］</span><span class="sxs-lookup"><span data-stu-id="844b1-108">Requirements</span></span>  
 <span data-ttu-id="844b1-109">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="844b1-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="844b1-110">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="844b1-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="844b1-111">**Library:** Used as a resource in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="844b1-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="844b1-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="844b1-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="844b1-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="844b1-113">See also</span></span>

- [<span data-ttu-id="844b1-114">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="844b1-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="844b1-115">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="844b1-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
