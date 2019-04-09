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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 766b17bae0c58d9872ff9c118f330ebc3220257e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59123488"
---
# <a name="ienumreferenceidentity-interface"></a><span data-ttu-id="e2840-102">IEnumReferenceIdentity インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e2840-102">IEnumReferenceIdentity Interface</span></span>
<span data-ttu-id="e2840-103">コレクションの列挙子として機能`IReferenceIdentity`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="e2840-103">Serves as an enumerator for a collection of `IReferenceIdentity` objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e2840-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="e2840-104">Methods</span></span>  
  
|<span data-ttu-id="e2840-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="e2840-105">Method</span></span>|<span data-ttu-id="e2840-106">説明</span><span class="sxs-lookup"><span data-stu-id="e2840-106">Description</span></span>|  
|------------|-----------------|  
|`IEnumReferenceIdentity::Clone`|<span data-ttu-id="e2840-107">新しいインターフェイス ポインターを取得`IEnumReferenceIdentity`これと同じメンバーを格納している`IEnumReferenceIdentity`します。</span><span class="sxs-lookup"><span data-stu-id="e2840-107">Gets an interface pointer to a new `IEnumReferenceIdentity` that contains the same members as this `IEnumReferenceIdentity`.</span></span>|  
|`IEnumReferenceIdentity::Next`|<span data-ttu-id="e2840-108">指定した数を取得`IReferenceIdentity`オブジェクト、現在の位置で開始します。</span><span class="sxs-lookup"><span data-stu-id="e2840-108">Gets the specified number of `IReferenceIdentity` objects, starting at the current position.</span></span>|  
|`IEnumReferenceIdentity::Reset`|<span data-ttu-id="e2840-109">これの先頭に、命令ポインターを移動`IEnumReferenceIdentity`します。</span><span class="sxs-lookup"><span data-stu-id="e2840-109">Moves the instruction pointer to the beginning of this `IEnumReferenceIdentity`.</span></span>|  
|`IEnumReferenceIdentity::Skip`|<span data-ttu-id="e2840-110">指定数の要素を現在の位置からでは、転送、命令ポインターを移動します。</span><span class="sxs-lookup"><span data-stu-id="e2840-110">Moves the instruction pointer forward by the specified number of elements, starting at the current position.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e2840-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="e2840-111">Requirements</span></span>  
 <span data-ttu-id="e2840-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2840-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2840-113">**ヘッダー:** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="e2840-113">**Header:** Isolation.h</span></span>  
  
 **<span data-ttu-id="e2840-114">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="e2840-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e2840-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="e2840-115">See also</span></span>

- [<span data-ttu-id="e2840-116">Fusion インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e2840-116">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
- [<span data-ttu-id="e2840-117">IReferenceIdentity インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e2840-117">IReferenceIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md)
