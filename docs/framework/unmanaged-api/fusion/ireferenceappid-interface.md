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
ms.openlocfilehash: 25733e459423500352595d6be0eee26ef75ca7e2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61789689"
---
# <a name="ireferenceappid-interface"></a><span data-ttu-id="d0f42-102">IReferenceAppId インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d0f42-102">IReferenceAppId Interface</span></span>
<span data-ttu-id="d0f42-103">現在のスコープ内でアプリケーションの一意の識別子への参照を表します。</span><span class="sxs-lookup"><span data-stu-id="d0f42-103">Represents a reference to the unique identifier for the application in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d0f42-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="d0f42-104">Methods</span></span>  
  
|<span data-ttu-id="d0f42-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="d0f42-105">Method</span></span>|<span data-ttu-id="d0f42-106">説明</span><span class="sxs-lookup"><span data-stu-id="d0f42-106">Description</span></span>|  
|------------|-----------------|  
|`IReferenceAppId::get_CodeBase`|<span data-ttu-id="d0f42-107">これによって参照されているアプリケーションのコードの識別子の文字列表現にポインターを取得します。`IReferenceAppId`します。</span><span class="sxs-lookup"><span data-stu-id="d0f42-107">Gets a pointer to a string representation of the code identifier for the application referenced by this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::put_CodeBase`|<span data-ttu-id="d0f42-108">これによって参照されているアプリケーションのコードの識別子を設定`IReferenceAppId`します。</span><span class="sxs-lookup"><span data-stu-id="d0f42-108">Sets the code identifier for the application referenced by this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::EnumAppPath`|<span data-ttu-id="d0f42-109">インターフェイス ポインターを取得、`IEnumReferenceIdentity`インスタンスを含む、 `IReferenceIdentity` this のメンバーを表すインスタンス`IReferenceAppId`します。</span><span class="sxs-lookup"><span data-stu-id="d0f42-109">Gets an interface pointer to an `IEnumReferenceIdentity` instance containing the `IReferenceIdentity` instances that represent members of this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::get_SubscriptionId`|<span data-ttu-id="d0f42-110">このサブスクリプションのトークンの識別子の文字列表現にポインターを取得します。`IReferenceAppId`します。</span><span class="sxs-lookup"><span data-stu-id="d0f42-110">Gets a pointer to a string representation of the token identifier for a subscription to this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::put_SubscriptionId`|<span data-ttu-id="d0f42-111">このサブスクリプションのトークンの識別子を設定`IReferenceAppId`を指定した文字列値。</span><span class="sxs-lookup"><span data-stu-id="d0f42-111">Sets the token identifier for a subscription to this `IReferenceAppId` to the specified string value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d0f42-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="d0f42-112">Requirements</span></span>  
 <span data-ttu-id="d0f42-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0f42-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d0f42-114">**ヘッダー:** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="d0f42-114">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="d0f42-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d0f42-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0f42-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="d0f42-116">See also</span></span>

- [<span data-ttu-id="d0f42-117">Fusion インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d0f42-117">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
- [<span data-ttu-id="d0f42-118">IEnumReferenceIdentity インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d0f42-118">IEnumReferenceIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ienumreferenceidentity-interface.md)
- [<span data-ttu-id="d0f42-119">IReferenceIdentity インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d0f42-119">IReferenceIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md)
