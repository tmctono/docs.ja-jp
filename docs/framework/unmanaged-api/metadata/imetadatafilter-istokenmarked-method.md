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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6969f2c1df9b5b04122ed6aef550697171123cf5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59229018"
---
# <a name="imetadatafilteristokenmarked-method"></a><span data-ttu-id="5d2d7-102">IMetaDataFilter::IsTokenMarked メソッド</span><span class="sxs-lookup"><span data-stu-id="5d2d7-102">IMetaDataFilter::IsTokenMarked Method</span></span>
<span data-ttu-id="5d2d7-103">処理されるときに、指定したメタデータ トークンがマークされているかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="5d2d7-103">Gets a value indicating whether the specified metadata token has been marked as processed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d2d7-104">構文</span><span class="sxs-lookup"><span data-stu-id="5d2d7-104">Syntax</span></span>  
  
```  
HRESULT IsTokenMarked (  
    [in]  mdToken  tk,   
    [out] BOOL     *pIsMarked  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5d2d7-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5d2d7-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="5d2d7-106">[in]処理のマークをチェックするトークンです。</span><span class="sxs-lookup"><span data-stu-id="5d2d7-106">[in] The token to examine for a processing mark.</span></span>  
  
 `pIsMarked`  
 <span data-ttu-id="5d2d7-107">[out]値が`true`場合`tk`それ以外の処理された`false`します。</span><span class="sxs-lookup"><span data-stu-id="5d2d7-107">[out] A value that is `true` if `tk` has been processed; otherwise `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d2d7-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="5d2d7-108">Requirements</span></span>  
 <span data-ttu-id="5d2d7-109">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d2d7-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d2d7-110">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5d2d7-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5d2d7-111">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="5d2d7-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="5d2d7-112">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="5d2d7-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5d2d7-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="5d2d7-113">See also</span></span>

- [<span data-ttu-id="5d2d7-114">IMetaDataFilter インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5d2d7-114">IMetaDataFilter Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-interface.md)
