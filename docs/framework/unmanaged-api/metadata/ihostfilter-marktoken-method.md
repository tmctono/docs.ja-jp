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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59194438"
---
# <a name="ihostfiltermarktoken-method"></a><span data-ttu-id="6dfdc-102">IHostFilter::MarkToken メソッド</span><span class="sxs-lookup"><span data-stu-id="6dfdc-102">IHostFilter::MarkToken Method</span></span>
<span data-ttu-id="6dfdc-103">指定したメタデータ トークンを処理することを示します。</span><span class="sxs-lookup"><span data-stu-id="6dfdc-103">Indicates that the specified metadata token will be processed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6dfdc-104">構文</span><span class="sxs-lookup"><span data-stu-id="6dfdc-104">Syntax</span></span>  
  
```  
HRESULT MarkToken (  
    [in]  mdToken         tk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6dfdc-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6dfdc-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="6dfdc-106">[in]処理するメタデータ トークンです。</span><span class="sxs-lookup"><span data-stu-id="6dfdc-106">[in] The metadata token to be processed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6dfdc-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="6dfdc-107">Remarks</span></span>  
 <span data-ttu-id="6dfdc-108">通常、メタデータ スコープ内にある場合、処理するためのトークンが必要です。</span><span class="sxs-lookup"><span data-stu-id="6dfdc-108">Typically, you want a token to be processed if it is in the metadata scope.</span></span> <span data-ttu-id="6dfdc-109">`MarkToken`メソッドが使用してメタデータ エンジンに渡される、 [imetadataemit::sethandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="6dfdc-109">The `MarkToken` method is passed to the metadata engine via the [IMetaDataEmit::SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6dfdc-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="6dfdc-110">Requirements</span></span>  
 <span data-ttu-id="6dfdc-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6dfdc-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6dfdc-112">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="6dfdc-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6dfdc-113">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="6dfdc-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6dfdc-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6dfdc-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6dfdc-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="6dfdc-115">See also</span></span>

- [<span data-ttu-id="6dfdc-116">メタデータ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6dfdc-116">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [<span data-ttu-id="6dfdc-117">IHostFilter インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6dfdc-117">IHostFilter Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/ihostfilter-interface.md)
