---
title: IReferenceAppId インターフェイス
ms.date: 03/30/2017
api_name:
- IReferenceAppId
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IReferenceAppId
helpviewer_keywords:
- IReferenceAppId interface [.NET Framework fusion]
ms.assetid: 8eb9e565-f358-43ce-900e-a8f8a5aa6cfb
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 522ed80f161f114af25e1fa7ad041c8238073d6f
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796371"
---
# <a name="ireferenceappid-interface"></a><span data-ttu-id="7c3b5-102">IReferenceAppId インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7c3b5-102">IReferenceAppId Interface</span></span>
<span data-ttu-id="7c3b5-103">現在のスコープ内のアプリケーションの一意の識別子への参照を表します。</span><span class="sxs-lookup"><span data-stu-id="7c3b5-103">Represents a reference to the unique identifier for the application in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7c3b5-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="7c3b5-104">Methods</span></span>  
  
|<span data-ttu-id="7c3b5-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="7c3b5-105">Method</span></span>|<span data-ttu-id="7c3b5-106">説明</span><span class="sxs-lookup"><span data-stu-id="7c3b5-106">Description</span></span>|  
|------------|-----------------|  
|`IReferenceAppId::get_CodeBase`|<span data-ttu-id="7c3b5-107">この`IReferenceAppId`によって参照されるアプリケーションのコード識別子の文字列形式へのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="7c3b5-107">Gets a pointer to a string representation of the code identifier for the application referenced by this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::put_CodeBase`|<span data-ttu-id="7c3b5-108">この`IReferenceAppId`によって参照されるアプリケーションのコード識別子を設定します。</span><span class="sxs-lookup"><span data-stu-id="7c3b5-108">Sets the code identifier for the application referenced by this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::EnumAppPath`|<span data-ttu-id="7c3b5-109">この`IReferenceIdentity` `IEnumReferenceIdentity` のメンバーを表すインスタンスを格納しているインスタンスへのインターフェイスポインターを取得します。`IReferenceAppId`</span><span class="sxs-lookup"><span data-stu-id="7c3b5-109">Gets an interface pointer to an `IEnumReferenceIdentity` instance containing the `IReferenceIdentity` instances that represent members of this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::get_SubscriptionId`|<span data-ttu-id="7c3b5-110">この`IReferenceAppId`に対するサブスクリプションのトークン識別子の文字列形式へのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="7c3b5-110">Gets a pointer to a string representation of the token identifier for a subscription to this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::put_SubscriptionId`|<span data-ttu-id="7c3b5-111">サブスクリプションのトークン識別子を指定された`IReferenceAppId`文字列値に設定します。</span><span class="sxs-lookup"><span data-stu-id="7c3b5-111">Sets the token identifier for a subscription to this `IReferenceAppId` to the specified string value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7c3b5-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="7c3b5-112">Requirements</span></span>  
 <span data-ttu-id="7c3b5-113">**・** [システム要件](../../get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7c3b5-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c3b5-114">**ヘッダー:** 分離 .h</span><span class="sxs-lookup"><span data-stu-id="7c3b5-114">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="7c3b5-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c3b5-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c3b5-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="7c3b5-116">See also</span></span>

- [<span data-ttu-id="7c3b5-117">Fusion インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7c3b5-117">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="7c3b5-118">IEnumReferenceIdentity インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7c3b5-118">IEnumReferenceIdentity Interface</span></span>](ienumreferenceidentity-interface.md)
- [<span data-ttu-id="7c3b5-119">IReferenceIdentity インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7c3b5-119">IReferenceIdentity Interface</span></span>](ireferenceidentity-interface.md)
