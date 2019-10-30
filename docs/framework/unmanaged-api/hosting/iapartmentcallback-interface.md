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
ms.openlocfilehash: 4424509c16dd1d9f83db117ae7343fa03995297e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126905"
---
# <a name="iapartmentcallback-interface"></a><span data-ttu-id="dd077-102">IApartmentCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="dd077-102">IApartmentCallback Interface</span></span>
<span data-ttu-id="dd077-103">アパートメント内でコールバックを作成するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="dd077-103">Provides methods for making callbacks within an apartment.</span></span> <span data-ttu-id="dd077-104">*アパートメント*は、同じスレッドアクセス要件を共有するオブジェクトのプロセス内の論理コンテナーです。</span><span class="sxs-lookup"><span data-stu-id="dd077-104">An *apartment* is a logical container within a process for objects that share the same thread access requirements.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="dd077-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="dd077-105">Methods</span></span>  
  
|<span data-ttu-id="dd077-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="dd077-106">Method</span></span>|<span data-ttu-id="dd077-107">説明</span><span class="sxs-lookup"><span data-stu-id="dd077-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="dd077-108">DoCallback メソッド</span><span class="sxs-lookup"><span data-stu-id="dd077-108">DoCallback Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iapartmentcallback-docallback-method.md)|<span data-ttu-id="dd077-109">アパートメント内で指定された関数を実行します。</span><span class="sxs-lookup"><span data-stu-id="dd077-109">Executes the specified function within an apartment.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="dd077-110">［要件］</span><span class="sxs-lookup"><span data-stu-id="dd077-110">Requirements</span></span>  
 <span data-ttu-id="dd077-111">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd077-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd077-112">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="dd077-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="dd077-113">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="dd077-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dd077-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd077-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd077-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="dd077-115">See also</span></span>

- [<span data-ttu-id="dd077-116">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="dd077-116">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
