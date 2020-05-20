---
title: IApartmentCallback インターフェイス
ms.date: 03/30/2017
api_name:
- IApartmentCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IApartmentCallback
helpviewer_keywords:
- IApartmentCallback interface [.NET Framework hosting]
ms.assetid: 57c33c58-bf0b-4533-b569-e6a682d02cba
topic_type:
- apiref
ms.openlocfilehash: fbf501d906ecc0bf55719fa33d1af2d4db1cc2ef
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83617096"
---
# <a name="iapartmentcallback-interface"></a><span data-ttu-id="956e0-102">IApartmentCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="956e0-102">IApartmentCallback Interface</span></span>
<span data-ttu-id="956e0-103">アパートメント内でコールバックを作成するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="956e0-103">Provides methods for making callbacks within an apartment.</span></span> <span data-ttu-id="956e0-104">*アパートメント*は、同じスレッドアクセス要件を共有するオブジェクトのプロセス内の論理コンテナーです。</span><span class="sxs-lookup"><span data-stu-id="956e0-104">An *apartment* is a logical container within a process for objects that share the same thread access requirements.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="956e0-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="956e0-105">Methods</span></span>  
  
|<span data-ttu-id="956e0-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="956e0-106">Method</span></span>|<span data-ttu-id="956e0-107">説明</span><span class="sxs-lookup"><span data-stu-id="956e0-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="956e0-108">DoCallback メソッド</span><span class="sxs-lookup"><span data-stu-id="956e0-108">DoCallback Method</span></span>](iapartmentcallback-docallback-method.md)|<span data-ttu-id="956e0-109">アパートメント内で指定された関数を実行します。</span><span class="sxs-lookup"><span data-stu-id="956e0-109">Executes the specified function within an apartment.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="956e0-110">要件</span><span class="sxs-lookup"><span data-stu-id="956e0-110">Requirements</span></span>  
 <span data-ttu-id="956e0-111">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="956e0-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="956e0-112">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="956e0-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="956e0-113">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="956e0-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="956e0-114">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="956e0-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="956e0-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="956e0-115">See also</span></span>

- [<span data-ttu-id="956e0-116">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="956e0-116">Hosting Interfaces</span></span>](hosting-interfaces.md)
