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
ms.openlocfilehash: 28a5f79f6fa8d25fd254c4093b0f76e0308edbad
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84492526"
---
# <a name="imetadatafiltermarktoken-method"></a><span data-ttu-id="fe1b8-102">IMetaDataFilter::MarkToken メソッド</span><span class="sxs-lookup"><span data-stu-id="fe1b8-102">IMetaDataFilter::MarkToken Method</span></span>
<span data-ttu-id="fe1b8-103">指定したメタデータトークンが処理されたことを示す値を設定します。</span><span class="sxs-lookup"><span data-stu-id="fe1b8-103">Sets a value indicating that the specified metadata token has been processed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe1b8-104">構文</span><span class="sxs-lookup"><span data-stu-id="fe1b8-104">Syntax</span></span>  
  
```cpp  
HRESULT MarkToken (  
    [in] mdToken   tk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fe1b8-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="fe1b8-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="fe1b8-106">から処理済みとしてマークするトークン。</span><span class="sxs-lookup"><span data-stu-id="fe1b8-106">[in] The token to mark as processed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe1b8-107">要件</span><span class="sxs-lookup"><span data-stu-id="fe1b8-107">Requirements</span></span>  
 <span data-ttu-id="fe1b8-108">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe1b8-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe1b8-109">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="fe1b8-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fe1b8-110">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="fe1b8-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fe1b8-111">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fe1b8-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe1b8-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="fe1b8-112">See also</span></span>

- [<span data-ttu-id="fe1b8-113">IMetaDataFilter インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fe1b8-113">IMetaDataFilter Interface</span></span>](imetadatafilter-interface.md)
