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
# <a name="imetadataemitsave-method"></a><span data-ttu-id="ea536-102">IMetaDataEmit::Save メソッド</span><span class="sxs-lookup"><span data-stu-id="ea536-102">IMetaDataEmit::Save Method</span></span>
<span data-ttu-id="ea536-103">現在のスコープ内のすべてのメタデータを、指定したアドレスにあるファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="ea536-103">Saves all metadata in the current scope to the file at the specified address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea536-104">構文</span><span class="sxs-lookup"><span data-stu-id="ea536-104">Syntax</span></span>  
  
```cpp  
HRESULT Save (   
    [in]  LPCWSTR     szFile,   
    [in]  DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ea536-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ea536-105">Parameters</span></span>  
 `wzFile`  
 <span data-ttu-id="ea536-106">から保存先のファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="ea536-106">[in] The name of the file to save to.</span></span> <span data-ttu-id="ea536-107">この値が null の場合、メモリ内のコピーは、使用された最後の場所に保存されます。</span><span class="sxs-lookup"><span data-stu-id="ea536-107">If this value is null, the in-memory copy will be saved to the last location that was used.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="ea536-108">[in] 予約されています。</span><span class="sxs-lookup"><span data-stu-id="ea536-108">[in] Reserved.</span></span> <span data-ttu-id="ea536-109">ゼロを指定してください。</span><span class="sxs-lookup"><span data-stu-id="ea536-109">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea536-110">要件</span><span class="sxs-lookup"><span data-stu-id="ea536-110">Requirements</span></span>  
 <span data-ttu-id="ea536-111">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ea536-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea536-112">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="ea536-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ea536-113">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="ea536-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ea536-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea536-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea536-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="ea536-115">See also</span></span>

- [<span data-ttu-id="ea536-116">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ea536-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="ea536-117">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ea536-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
