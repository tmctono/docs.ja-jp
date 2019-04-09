---
title: IMetaDataFilter::MarkToken メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataFilter.MarkToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataFilter::MarkToken
helpviewer_keywords:
- IMetaDataFilter::MarkToken method [.NET Framework metadata]
- MarkToken method, IMetaDataFilter interface [.NET Framework metadata]
ms.assetid: bd492834-6529-4d39-b93d-f8cdbd3e297f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6fdd50f0de014aa68b14303e9e22924b0790fa55
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59085117"
---
# <a name="imetadatafiltermarktoken-method"></a><span data-ttu-id="dc29d-102">IMetaDataFilter::MarkToken メソッド</span><span class="sxs-lookup"><span data-stu-id="dc29d-102">IMetaDataFilter::MarkToken Method</span></span>
<span data-ttu-id="dc29d-103">指定したメタデータ トークンが処理されたことを示す値を設定します。</span><span class="sxs-lookup"><span data-stu-id="dc29d-103">Sets a value indicating that the specified metadata token has been processed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc29d-104">構文</span><span class="sxs-lookup"><span data-stu-id="dc29d-104">Syntax</span></span>  
  
```  
HRESULT MarkToken (  
    [in] mdToken   tk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dc29d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="dc29d-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="dc29d-106">[in]処理済みとマークするトークンです。</span><span class="sxs-lookup"><span data-stu-id="dc29d-106">[in] The token to mark as processed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc29d-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="dc29d-107">Requirements</span></span>  
 <span data-ttu-id="dc29d-108">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc29d-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc29d-109">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="dc29d-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="dc29d-110">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="dc29d-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="dc29d-111">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="dc29d-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="dc29d-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="dc29d-112">See also</span></span>

- [<span data-ttu-id="dc29d-113">IMetaDataFilter インターフェイス</span><span class="sxs-lookup"><span data-stu-id="dc29d-113">IMetaDataFilter Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-interface.md)
