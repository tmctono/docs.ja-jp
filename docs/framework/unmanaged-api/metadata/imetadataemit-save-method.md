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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 90ddc540115a60154953ac6e8cb931103a650752
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57492414"
---
# <a name="imetadataemitsave-method"></a><span data-ttu-id="fc3fd-102">IMetaDataEmit::Save メソッド</span><span class="sxs-lookup"><span data-stu-id="fc3fd-102">IMetaDataEmit::Save Method</span></span>
<span data-ttu-id="fc3fd-103">指定したアドレスにあるファイルに現在のスコープ内のすべてのメタデータを保存します。</span><span class="sxs-lookup"><span data-stu-id="fc3fd-103">Saves all metadata in the current scope to the file at the specified address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc3fd-104">構文</span><span class="sxs-lookup"><span data-stu-id="fc3fd-104">Syntax</span></span>  
  
```  
HRESULT Save (   
    [in]  LPCWSTR     szFile,   
    [in]  DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fc3fd-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="fc3fd-105">Parameters</span></span>  
 `wzFile`  
 <span data-ttu-id="fc3fd-106">[in]保存するファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="fc3fd-106">[in] The name of the file to save to.</span></span> <span data-ttu-id="fc3fd-107">この値が null の場合は、メモリ内のコピーは、最後に使用された場所に保存されます。</span><span class="sxs-lookup"><span data-stu-id="fc3fd-107">If this value is null, the in-memory copy will be saved to the last location that was used.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="fc3fd-108">[in] 予約されています。</span><span class="sxs-lookup"><span data-stu-id="fc3fd-108">[in] Reserved.</span></span> <span data-ttu-id="fc3fd-109">ゼロを指定してください。</span><span class="sxs-lookup"><span data-stu-id="fc3fd-109">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc3fd-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="fc3fd-110">Requirements</span></span>  
 <span data-ttu-id="fc3fd-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fc3fd-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc3fd-112">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="fc3fd-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fc3fd-113">**ライブラリ:** MSCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="fc3fd-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fc3fd-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc3fd-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc3fd-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="fc3fd-115">See also</span></span>
- [<span data-ttu-id="fc3fd-116">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fc3fd-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="fc3fd-117">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fc3fd-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
