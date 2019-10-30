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
ms.openlocfilehash: 6f20fb2e9e026253fb02b47dfcd63cf655acc4ee
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131657"
---
# <a name="ireferenceappid-interface"></a><span data-ttu-id="e3d53-102">IReferenceAppId インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e3d53-102">IReferenceAppId Interface</span></span>
<span data-ttu-id="e3d53-103">現在のスコープ内のアプリケーションの一意の識別子への参照を表します。</span><span class="sxs-lookup"><span data-stu-id="e3d53-103">Represents a reference to the unique identifier for the application in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e3d53-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="e3d53-104">Methods</span></span>  
  
|<span data-ttu-id="e3d53-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="e3d53-105">Method</span></span>|<span data-ttu-id="e3d53-106">説明</span><span class="sxs-lookup"><span data-stu-id="e3d53-106">Description</span></span>|  
|------------|-----------------|  
|`IReferenceAppId::get_CodeBase`|<span data-ttu-id="e3d53-107">この `IReferenceAppId`によって参照されるアプリケーションのコード識別子の文字列形式へのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="e3d53-107">Gets a pointer to a string representation of the code identifier for the application referenced by this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::put_CodeBase`|<span data-ttu-id="e3d53-108">この `IReferenceAppId`によって参照されるアプリケーションのコード識別子を設定します。</span><span class="sxs-lookup"><span data-stu-id="e3d53-108">Sets the code identifier for the application referenced by this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::EnumAppPath`|<span data-ttu-id="e3d53-109">この `IReferenceAppId`のメンバーを表す `IReferenceIdentity` インスタンスを格納している `IEnumReferenceIdentity` インスタンスへのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="e3d53-109">Gets an interface pointer to an `IEnumReferenceIdentity` instance containing the `IReferenceIdentity` instances that represent members of this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::get_SubscriptionId`|<span data-ttu-id="e3d53-110">この `IReferenceAppId`へのサブスクリプションのトークン識別子の文字列形式へのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="e3d53-110">Gets a pointer to a string representation of the token identifier for a subscription to this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::put_SubscriptionId`|<span data-ttu-id="e3d53-111">この `IReferenceAppId` に対するサブスクリプションのトークン識別子を、指定された文字列値に設定します。</span><span class="sxs-lookup"><span data-stu-id="e3d53-111">Sets the token identifier for a subscription to this `IReferenceAppId` to the specified string value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e3d53-112">［要件］</span><span class="sxs-lookup"><span data-stu-id="e3d53-112">Requirements</span></span>  
 <span data-ttu-id="e3d53-113">**:** 「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e3d53-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e3d53-114">**ヘッダー:** 分離 .h</span><span class="sxs-lookup"><span data-stu-id="e3d53-114">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="e3d53-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e3d53-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3d53-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="e3d53-116">See also</span></span>

- [<span data-ttu-id="e3d53-117">Fusion インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e3d53-117">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="e3d53-118">IEnumReferenceIdentity インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e3d53-118">IEnumReferenceIdentity Interface</span></span>](ienumreferenceidentity-interface.md)
- [<span data-ttu-id="e3d53-119">IReferenceIdentity インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e3d53-119">IReferenceIdentity Interface</span></span>](ireferenceidentity-interface.md)
