---
title: IHostFilter::MarkToken メソッド
ms.date: 03/30/2017
api_name:
- IHostFilter.MarkToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostFilter::MarkToken
helpviewer_keywords:
- MarkToken method, IHostFilter interface [.NET Framework metadata]
- IHostFilter::MarkToken method [.NET Framework metadata]
ms.assetid: d7061343-d0a3-4fd5-b312-61974f98bd62
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f3214a21dda27fda01054e96400997b15d11f71b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59194438"
---
# <a name="ihostfiltermarktoken-method"></a><span data-ttu-id="debb6-102">IHostFilter::MarkToken メソッド</span><span class="sxs-lookup"><span data-stu-id="debb6-102">IHostFilter::MarkToken Method</span></span>
<span data-ttu-id="debb6-103">指定したメタデータ トークンを処理することを示します。</span><span class="sxs-lookup"><span data-stu-id="debb6-103">Indicates that the specified metadata token will be processed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="debb6-104">構文</span><span class="sxs-lookup"><span data-stu-id="debb6-104">Syntax</span></span>  
  
```  
HRESULT MarkToken (  
    [in]  mdToken         tk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="debb6-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="debb6-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="debb6-106">[in]処理するメタデータ トークンです。</span><span class="sxs-lookup"><span data-stu-id="debb6-106">[in] The metadata token to be processed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="debb6-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="debb6-107">Remarks</span></span>  
 <span data-ttu-id="debb6-108">通常、メタデータ スコープ内にある場合、処理するためのトークンが必要です。</span><span class="sxs-lookup"><span data-stu-id="debb6-108">Typically, you want a token to be processed if it is in the metadata scope.</span></span> <span data-ttu-id="debb6-109">`MarkToken`メソッドが使用してメタデータ エンジンに渡される、 [imetadataemit::sethandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="debb6-109">The `MarkToken` method is passed to the metadata engine via the [IMetaDataEmit::SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="debb6-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="debb6-110">Requirements</span></span>  
 <span data-ttu-id="debb6-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="debb6-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="debb6-112">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="debb6-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="debb6-113">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="debb6-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="debb6-114">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="debb6-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="debb6-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="debb6-115">See also</span></span>

- [<span data-ttu-id="debb6-116">メタデータ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="debb6-116">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [<span data-ttu-id="debb6-117">IHostFilter インターフェイス</span><span class="sxs-lookup"><span data-stu-id="debb6-117">IHostFilter Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/ihostfilter-interface.md)
