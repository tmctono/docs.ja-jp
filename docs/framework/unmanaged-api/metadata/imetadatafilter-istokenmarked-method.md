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
ms.openlocfilehash: eb0ebab0f4e05d81730d5beb2b5345e319e8e274
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84492539"
---
# <a name="imetadatafilteristokenmarked-method"></a><span data-ttu-id="30b5c-102">IMetaDataFilter::IsTokenMarked メソッド</span><span class="sxs-lookup"><span data-stu-id="30b5c-102">IMetaDataFilter::IsTokenMarked Method</span></span>
<span data-ttu-id="30b5c-103">指定したメタデータトークンが処理済みとしてマークされているかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="30b5c-103">Gets a value indicating whether the specified metadata token has been marked as processed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30b5c-104">構文</span><span class="sxs-lookup"><span data-stu-id="30b5c-104">Syntax</span></span>  
  
```cpp  
HRESULT IsTokenMarked (  
    [in]  mdToken  tk,
    [out] BOOL     *pIsMarked  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="30b5c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="30b5c-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="30b5c-106">から処理マークを調べるトークン。</span><span class="sxs-lookup"><span data-stu-id="30b5c-106">[in] The token to examine for a processing mark.</span></span>  
  
 `pIsMarked`  
 <span data-ttu-id="30b5c-107">入出力が `true` 処理された場合は値。それ以外の場合は `tk` `false` 。</span><span class="sxs-lookup"><span data-stu-id="30b5c-107">[out] A value that is `true` if `tk` has been processed; otherwise `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30b5c-108">要件</span><span class="sxs-lookup"><span data-stu-id="30b5c-108">Requirements</span></span>  
 <span data-ttu-id="30b5c-109">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="30b5c-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30b5c-110">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="30b5c-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="30b5c-111">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="30b5c-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="30b5c-112">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30b5c-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30b5c-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="30b5c-113">See also</span></span>

- [<span data-ttu-id="30b5c-114">IMetaDataFilter インターフェイス</span><span class="sxs-lookup"><span data-stu-id="30b5c-114">IMetaDataFilter Interface</span></span>](imetadatafilter-interface.md)
