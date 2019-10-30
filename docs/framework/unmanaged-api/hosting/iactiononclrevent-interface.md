---
title: IActionOnCLREvent インターフェイス
ms.date: 03/30/2017
api_name:
- IActionOnCLREvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IActionOnCLREvent
helpviewer_keywords:
- IActionOnCLREvent interface [.NET Framework hosting]
ms.assetid: b5f9b41e-7301-429c-911f-21d5422292b3
topic_type:
- apiref
ms.openlocfilehash: 9277fe2c241ce4f502339de826dccd08a2ce8055
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126956"
---
# <a name="iactiononclrevent-interface"></a><span data-ttu-id="1e4a9-102">IActionOnCLREvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1e4a9-102">IActionOnCLREvent Interface</span></span>
<span data-ttu-id="1e4a9-103">[Iactiononclrevent:: OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md)メソッドを提供します。このメソッドは、 [ICLROnEventManager:: registeractiononevent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md)メソッドの呼び出しを使用して登録されたイベントに対してコールバックを実行します。</span><span class="sxs-lookup"><span data-stu-id="1e4a9-103">Provides the [IActionOnCLREvent::OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) method, which performs callbacks on events that have been registered by using a call to the [ICLROnEventManager::RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1e4a9-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="1e4a9-104">Methods</span></span>  
  
|<span data-ttu-id="1e4a9-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="1e4a9-105">Method</span></span>|<span data-ttu-id="1e4a9-106">説明</span><span class="sxs-lookup"><span data-stu-id="1e4a9-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1e4a9-107">OnEvent メソッド</span><span class="sxs-lookup"><span data-stu-id="1e4a9-107">OnEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md)|<span data-ttu-id="1e4a9-108">登録されているイベントに対してコールバックを実行します。</span><span class="sxs-lookup"><span data-stu-id="1e4a9-108">Performs a callback for a registered event.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1e4a9-109">［要件］</span><span class="sxs-lookup"><span data-stu-id="1e4a9-109">Requirements</span></span>  
 <span data-ttu-id="1e4a9-110">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1e4a9-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1e4a9-111">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="1e4a9-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1e4a9-112">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="1e4a9-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1e4a9-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1e4a9-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e4a9-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="1e4a9-114">See also</span></span>

- [<span data-ttu-id="1e4a9-115">EClrEvent 列挙型</span><span class="sxs-lookup"><span data-stu-id="1e4a9-115">EClrEvent Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)
- [<span data-ttu-id="1e4a9-116">ICLRControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1e4a9-116">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="1e4a9-117">ICLROnEventManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1e4a9-117">ICLROnEventManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)
- [<span data-ttu-id="1e4a9-118">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1e4a9-118">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
