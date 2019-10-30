---
title: IEnumReferenceIdentity インターフェイス
ms.date: 03/30/2017
api_name:
- IEnumReferenceIdentity
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IEnumReferenceIdentity
helpviewer_keywords:
- IEnumReferenceIdentity interface [.NET Framework fusion]
ms.assetid: a17b3155-7216-4e16-8c9f-abce21f549e7
topic_type:
- apiref
ms.openlocfilehash: 1305b9ebe3cd87ba002ee87610ff309d015a44e6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131748"
---
# <a name="ienumreferenceidentity-interface"></a><span data-ttu-id="26cff-102">IEnumReferenceIdentity インターフェイス</span><span class="sxs-lookup"><span data-stu-id="26cff-102">IEnumReferenceIdentity Interface</span></span>
<span data-ttu-id="26cff-103">`IReferenceIdentity` オブジェクトのコレクションの列挙子として機能します。</span><span class="sxs-lookup"><span data-stu-id="26cff-103">Serves as an enumerator for a collection of `IReferenceIdentity` objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="26cff-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="26cff-104">Methods</span></span>  
  
|<span data-ttu-id="26cff-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="26cff-105">Method</span></span>|<span data-ttu-id="26cff-106">説明</span><span class="sxs-lookup"><span data-stu-id="26cff-106">Description</span></span>|  
|------------|-----------------|  
|`IEnumReferenceIdentity::Clone`|<span data-ttu-id="26cff-107">この `IEnumReferenceIdentity`と同じメンバーを含む新しい `IEnumReferenceIdentity` へのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="26cff-107">Gets an interface pointer to a new `IEnumReferenceIdentity` that contains the same members as this `IEnumReferenceIdentity`.</span></span>|  
|`IEnumReferenceIdentity::Next`|<span data-ttu-id="26cff-108">現在の位置から開始して、指定した数の `IReferenceIdentity` オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="26cff-108">Gets the specified number of `IReferenceIdentity` objects, starting at the current position.</span></span>|  
|`IEnumReferenceIdentity::Reset`|<span data-ttu-id="26cff-109">命令ポインターをこの `IEnumReferenceIdentity`の先頭に移動します。</span><span class="sxs-lookup"><span data-stu-id="26cff-109">Moves the instruction pointer to the beginning of this `IEnumReferenceIdentity`.</span></span>|  
|`IEnumReferenceIdentity::Skip`|<span data-ttu-id="26cff-110">現在位置を開始位置として、指定した要素数だけ前方に命令ポインターを移動します。</span><span class="sxs-lookup"><span data-stu-id="26cff-110">Moves the instruction pointer forward by the specified number of elements, starting at the current position.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="26cff-111">［要件］</span><span class="sxs-lookup"><span data-stu-id="26cff-111">Requirements</span></span>  
 <span data-ttu-id="26cff-112">**:** 「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="26cff-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="26cff-113">**ヘッダー:** 分離 .h</span><span class="sxs-lookup"><span data-stu-id="26cff-113">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="26cff-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="26cff-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26cff-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="26cff-115">See also</span></span>

- [<span data-ttu-id="26cff-116">Fusion インターフェイス</span><span class="sxs-lookup"><span data-stu-id="26cff-116">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="26cff-117">IReferenceIdentity インターフェイス</span><span class="sxs-lookup"><span data-stu-id="26cff-117">IReferenceIdentity Interface</span></span>](ireferenceidentity-interface.md)
