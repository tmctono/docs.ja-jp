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
ms.openlocfilehash: 6f8df824ed36b7793d5f07e5b5cf51f65f9c8e24
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74432239"
---
# <a name="ihostfiltermarktoken-method"></a><span data-ttu-id="f5673-102">IHostFilter::MarkToken メソッド</span><span class="sxs-lookup"><span data-stu-id="f5673-102">IHostFilter::MarkToken Method</span></span>
<span data-ttu-id="f5673-103">指定されたメタデータトークンが処理されることを示します。</span><span class="sxs-lookup"><span data-stu-id="f5673-103">Indicates that the specified metadata token will be processed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5673-104">構文</span><span class="sxs-lookup"><span data-stu-id="f5673-104">Syntax</span></span>  
  
```cpp  
HRESULT MarkToken (  
    [in]  mdToken         tk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f5673-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f5673-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="f5673-106">から処理するメタデータトークン。</span><span class="sxs-lookup"><span data-stu-id="f5673-106">[in] The metadata token to be processed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f5673-107">コメント</span><span class="sxs-lookup"><span data-stu-id="f5673-107">Remarks</span></span>  
 <span data-ttu-id="f5673-108">通常、トークンがメタデータスコープ内にある場合は、トークンを処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5673-108">Typically, you want a token to be processed if it is in the metadata scope.</span></span> <span data-ttu-id="f5673-109">`MarkToken` メソッドは、 [IMetaDataEmit:: SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md)メソッドを使用してメタデータエンジンに渡されます。</span><span class="sxs-lookup"><span data-stu-id="f5673-109">The `MarkToken` method is passed to the metadata engine via the [IMetaDataEmit::SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5673-110">要件</span><span class="sxs-lookup"><span data-stu-id="f5673-110">Requirements</span></span>  
 <span data-ttu-id="f5673-111">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f5673-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5673-112">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="f5673-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f5673-113">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="f5673-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f5673-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5673-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5673-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="f5673-115">See also</span></span>

- [<span data-ttu-id="f5673-116">メタデータ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f5673-116">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [<span data-ttu-id="f5673-117">IHostFilter インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f5673-117">IHostFilter Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/ihostfilter-interface.md)
