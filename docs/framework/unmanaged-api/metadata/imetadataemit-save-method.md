---
title: IMetaDataEmit::Save メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.Save
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::Save
helpviewer_keywords:
- Save method, IMetaDataEmit interface [.NET Framework metadata]
- IMetaDataEmit::Save method [.NET Framework metadata]
ms.assetid: c1de8400-adfe-4a71-b828-a1d0cc1ea505
topic_type:
- apiref
ms.openlocfilehash: afd60cdf566bea459816ee890d44cc09258de516
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74435940"
---
# <a name="imetadataemitsave-method"></a><span data-ttu-id="3f04f-102">IMetaDataEmit::Save メソッド</span><span class="sxs-lookup"><span data-stu-id="3f04f-102">IMetaDataEmit::Save Method</span></span>
<span data-ttu-id="3f04f-103">Saves all metadata in the current scope to the file at the specified address.</span><span class="sxs-lookup"><span data-stu-id="3f04f-103">Saves all metadata in the current scope to the file at the specified address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f04f-104">構文</span><span class="sxs-lookup"><span data-stu-id="3f04f-104">Syntax</span></span>  
  
```cpp  
HRESULT Save (   
    [in]  LPCWSTR     szFile,   
    [in]  DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3f04f-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3f04f-105">Parameters</span></span>  
 `wzFile`  
 <span data-ttu-id="3f04f-106">[in] The name of the file to save to.</span><span class="sxs-lookup"><span data-stu-id="3f04f-106">[in] The name of the file to save to.</span></span> <span data-ttu-id="3f04f-107">If this value is null, the in-memory copy will be saved to the last location that was used.</span><span class="sxs-lookup"><span data-stu-id="3f04f-107">If this value is null, the in-memory copy will be saved to the last location that was used.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="3f04f-108">[in] 予約されています。</span><span class="sxs-lookup"><span data-stu-id="3f04f-108">[in] Reserved.</span></span> <span data-ttu-id="3f04f-109">ゼロを指定してください。</span><span class="sxs-lookup"><span data-stu-id="3f04f-109">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f04f-110">［要件］</span><span class="sxs-lookup"><span data-stu-id="3f04f-110">Requirements</span></span>  
 <span data-ttu-id="3f04f-111">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3f04f-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f04f-112">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="3f04f-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3f04f-113">**Library:** Used as a resource in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3f04f-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3f04f-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f04f-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f04f-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="3f04f-115">See also</span></span>

- [<span data-ttu-id="3f04f-116">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3f04f-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="3f04f-117">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3f04f-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
