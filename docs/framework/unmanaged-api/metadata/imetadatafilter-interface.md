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
ms.openlocfilehash: 821936d20a421739e8eb3d5df228888df7f022e3
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503787"
---
# <a name="imetadatafilter-interface"></a><span data-ttu-id="28c6a-102">IMetaDataFilter インターフェイス</span><span class="sxs-lookup"><span data-stu-id="28c6a-102">IMetaDataFilter Interface</span></span>
<span data-ttu-id="28c6a-103">メタデータ トークンにマークを付け、フィルター処理をして、既に実行されたアクションが繰り返し行われないようにするメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="28c6a-103">Provides methods for marking and filtering metadata tokens to avoid repeating actions that have already been taken.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="28c6a-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="28c6a-104">Methods</span></span>  
  
|<span data-ttu-id="28c6a-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="28c6a-105">Method</span></span>|<span data-ttu-id="28c6a-106">説明</span><span class="sxs-lookup"><span data-stu-id="28c6a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="28c6a-107">IsTokenMarked メソッド</span><span class="sxs-lookup"><span data-stu-id="28c6a-107">IsTokenMarked Method</span></span>](imetadatafilter-istokenmarked-method.md)|<span data-ttu-id="28c6a-108">指定したメタデータトークンが処理されたかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="28c6a-108">Gets a value indicating whether the specified metadata token has been processed.</span></span>|  
|[<span data-ttu-id="28c6a-109">MarkToken メソッド</span><span class="sxs-lookup"><span data-stu-id="28c6a-109">MarkToken Method</span></span>](imetadatafilter-marktoken-method.md)|<span data-ttu-id="28c6a-110">指定したメタデータトークンが処理されたことを示す値を設定します。</span><span class="sxs-lookup"><span data-stu-id="28c6a-110">Sets a value indicating that the specified metadata token has been processed.</span></span>|  
|[<span data-ttu-id="28c6a-111">UnmarkAll メソッド</span><span class="sxs-lookup"><span data-stu-id="28c6a-111">UnmarkAll Method</span></span>](imetadatafilter-unmarkall-method.md)|<span data-ttu-id="28c6a-112">現在のメタデータスコープ内のすべてのトークンから処理マークを削除します。</span><span class="sxs-lookup"><span data-stu-id="28c6a-112">Removes the processing marks from all the tokens in the current metadata scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="28c6a-113">要件</span><span class="sxs-lookup"><span data-stu-id="28c6a-113">Requirements</span></span>  
 <span data-ttu-id="28c6a-114">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="28c6a-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28c6a-115">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="28c6a-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="28c6a-116">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="28c6a-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="28c6a-117">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="28c6a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28c6a-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="28c6a-118">See also</span></span>

- [<span data-ttu-id="28c6a-119">メタデータ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="28c6a-119">Metadata Interfaces</span></span>](metadata-interfaces.md)
