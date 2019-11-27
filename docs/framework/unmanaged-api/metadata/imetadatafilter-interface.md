---
title: IMetaDataFilter インターフェイス
ms.date: 03/30/2017
api_name:
- IMetaDataFilter
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataFilter
helpviewer_keywords:
- IMetaDataFilter interface [.NET Framework metadata]
ms.assetid: ec0856ef-8c56-40ba-bf60-86e0ce8b337f
topic_type:
- apiref
ms.openlocfilehash: e8b15f478eb3b94b7cdcab3b69d54e7cc99be13b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440167"
---
# <a name="imetadatafilter-interface"></a><span data-ttu-id="1a8d4-102">IMetaDataFilter インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1a8d4-102">IMetaDataFilter Interface</span></span>
<span data-ttu-id="1a8d4-103">メタデータ トークンにマークを付け、フィルター処理をして、既に実行されたアクションが繰り返し行われないようにするメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="1a8d4-103">Provides methods for marking and filtering metadata tokens to avoid repeating actions that have already been taken.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1a8d4-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="1a8d4-104">Methods</span></span>  
  
|<span data-ttu-id="1a8d4-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="1a8d4-105">Method</span></span>|<span data-ttu-id="1a8d4-106">説明</span><span class="sxs-lookup"><span data-stu-id="1a8d4-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1a8d4-107">IsTokenMarked メソッド</span><span class="sxs-lookup"><span data-stu-id="1a8d4-107">IsTokenMarked Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-istokenmarked-method.md)|<span data-ttu-id="1a8d4-108">指定したメタデータトークンが処理されたかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="1a8d4-108">Gets a value indicating whether the specified metadata token has been processed.</span></span>|  
|[<span data-ttu-id="1a8d4-109">MarkToken メソッド</span><span class="sxs-lookup"><span data-stu-id="1a8d4-109">MarkToken Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-marktoken-method.md)|<span data-ttu-id="1a8d4-110">指定したメタデータトークンが処理されたことを示す値を設定します。</span><span class="sxs-lookup"><span data-stu-id="1a8d4-110">Sets a value indicating that the specified metadata token has been processed.</span></span>|  
|[<span data-ttu-id="1a8d4-111">UnmarkAll メソッド</span><span class="sxs-lookup"><span data-stu-id="1a8d4-111">UnmarkAll Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-unmarkall-method.md)|<span data-ttu-id="1a8d4-112">現在のメタデータスコープ内のすべてのトークンから処理マークを削除します。</span><span class="sxs-lookup"><span data-stu-id="1a8d4-112">Removes the processing marks from all the tokens in the current metadata scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1a8d4-113">要件</span><span class="sxs-lookup"><span data-stu-id="1a8d4-113">Requirements</span></span>  
 <span data-ttu-id="1a8d4-114">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a8d4-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1a8d4-115">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="1a8d4-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1a8d4-116">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="1a8d4-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1a8d4-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1a8d4-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a8d4-118">参照</span><span class="sxs-lookup"><span data-stu-id="1a8d4-118">See also</span></span>

- [<span data-ttu-id="1a8d4-119">メタデータ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1a8d4-119">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
