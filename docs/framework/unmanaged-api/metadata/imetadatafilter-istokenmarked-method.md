---
title: IMetaDataFilter::IsTokenMarked メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataFilter.IsTokenMarked
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataFilter::IsTokenMarked
helpviewer_keywords:
- IMetaDataFilter::IsTokenMarked method [.NET Framework metadata]
- IsTokenMarked method [.NET Framework metadata]
ms.assetid: 7d90dcee-0206-4540-807b-06982fe65f1a
topic_type:
- apiref
ms.openlocfilehash: 10f31d56a9727e99157f49038c19781f12cd9958
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440432"
---
# <a name="imetadatafilteristokenmarked-method"></a><span data-ttu-id="3457d-102">IMetaDataFilter::IsTokenMarked メソッド</span><span class="sxs-lookup"><span data-stu-id="3457d-102">IMetaDataFilter::IsTokenMarked Method</span></span>
<span data-ttu-id="3457d-103">指定したメタデータトークンが処理済みとしてマークされているかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="3457d-103">Gets a value indicating whether the specified metadata token has been marked as processed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3457d-104">構文</span><span class="sxs-lookup"><span data-stu-id="3457d-104">Syntax</span></span>  
  
```cpp  
HRESULT IsTokenMarked (  
    [in]  mdToken  tk,   
    [out] BOOL     *pIsMarked  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3457d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3457d-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="3457d-106">から処理マークを調べるトークン。</span><span class="sxs-lookup"><span data-stu-id="3457d-106">[in] The token to examine for a processing mark.</span></span>  
  
 `pIsMarked`  
 <span data-ttu-id="3457d-107">入出力`tk` が処理された場合に `true` される値です。それ以外の場合は `false`。</span><span class="sxs-lookup"><span data-stu-id="3457d-107">[out] A value that is `true` if `tk` has been processed; otherwise `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3457d-108">要件</span><span class="sxs-lookup"><span data-stu-id="3457d-108">Requirements</span></span>  
 <span data-ttu-id="3457d-109">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3457d-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3457d-110">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="3457d-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3457d-111">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="3457d-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3457d-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3457d-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3457d-113">参照</span><span class="sxs-lookup"><span data-stu-id="3457d-113">See also</span></span>

- [<span data-ttu-id="3457d-114">IMetaDataFilter インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3457d-114">IMetaDataFilter Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-interface.md)
