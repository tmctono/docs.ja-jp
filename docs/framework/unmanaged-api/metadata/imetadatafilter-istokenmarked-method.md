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
ms.openlocfilehash: 47377e892aaf2bdd96a297630c47fe52215b0564
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177381"
---
# <a name="imetadatafilteristokenmarked-method"></a><span data-ttu-id="19c2b-102">IMetaDataFilter::IsTokenMarked メソッド</span><span class="sxs-lookup"><span data-stu-id="19c2b-102">IMetaDataFilter::IsTokenMarked Method</span></span>
<span data-ttu-id="19c2b-103">指定したメタデータ トークンが処理済みとしてマークされているかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="19c2b-103">Gets a value indicating whether the specified metadata token has been marked as processed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19c2b-104">構文</span><span class="sxs-lookup"><span data-stu-id="19c2b-104">Syntax</span></span>  
  
```cpp  
HRESULT IsTokenMarked (  
    [in]  mdToken  tk,
    [out] BOOL     *pIsMarked  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="19c2b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="19c2b-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="19c2b-106">[in]処理マークを調べるトークン。</span><span class="sxs-lookup"><span data-stu-id="19c2b-106">[in] The token to examine for a processing mark.</span></span>  
  
 `pIsMarked`  
 <span data-ttu-id="19c2b-107">[アウト]処理済みの`true`場合`tk`の値。それ`false`以外の場合は、</span><span class="sxs-lookup"><span data-stu-id="19c2b-107">[out] A value that is `true` if `tk` has been processed; otherwise `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19c2b-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="19c2b-108">Requirements</span></span>  
 <span data-ttu-id="19c2b-109">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="19c2b-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19c2b-110">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="19c2b-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="19c2b-111">**ライブラリ:** MsCorEE.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="19c2b-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="19c2b-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19c2b-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19c2b-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="19c2b-113">See also</span></span>

- [<span data-ttu-id="19c2b-114">IMetaDataFilter インターフェイス</span><span class="sxs-lookup"><span data-stu-id="19c2b-114">IMetaDataFilter Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-interface.md)
