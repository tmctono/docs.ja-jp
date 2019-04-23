---
title: ICLROnEventManager インターフェイス
ms.date: 03/30/2017
api_name:
- ICLROnEventManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLROnEventManager
helpviewer_keywords:
- ICLROnEventManager interface [.NET Framework hosting]
ms.assetid: 9e15a0c1-8ab6-43d0-ae28-6ec7a4edd913
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7486a094deab16ebbc05f19f1b652126479ce11c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59183002"
---
# <a name="iclroneventmanager-interface"></a><span data-ttu-id="cd4c3-102">ICLROnEventManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cd4c3-102">ICLROnEventManager Interface</span></span>
<span data-ttu-id="cd4c3-103">ホストが登録および共通言語ランタイム (CLR) のイベントのコールバックを登録解除できるようにするメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="cd4c3-103">Provides methods that allow the host to register and unregister callbacks for common language runtime (CLR) events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cd4c3-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="cd4c3-104">Methods</span></span>  
  
|<span data-ttu-id="cd4c3-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="cd4c3-105">Method</span></span>|<span data-ttu-id="cd4c3-106">説明</span><span class="sxs-lookup"><span data-stu-id="cd4c3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cd4c3-107">RegisterActionOnEvent メソッド</span><span class="sxs-lookup"><span data-stu-id="cd4c3-107">RegisterActionOnEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md)|<span data-ttu-id="cd4c3-108">指定したイベントのコールバック ポインターを登録します。</span><span class="sxs-lookup"><span data-stu-id="cd4c3-108">Registers a callback pointer for the specified event.</span></span>|  
|[<span data-ttu-id="cd4c3-109">UnregisterActionOnEvent メソッド</span><span class="sxs-lookup"><span data-stu-id="cd4c3-109">UnregisterActionOnEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-unregisteractiononevent-method.md)|<span data-ttu-id="cd4c3-110">指定されたイベントに対して以前に登録されたコールバック ポインターを登録解除します。</span><span class="sxs-lookup"><span data-stu-id="cd4c3-110">Unregisters a previously registered callback pointer for the specified event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cd4c3-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="cd4c3-111">Remarks</span></span>  
 <span data-ttu-id="cd4c3-112">参照を取得するホストを登録し、イベントのコールバックを登録解除、`ICLROnEventManager`呼び出すことによって、 [iclrcontrol::getclrmanager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="cd4c3-112">To register and unregister event callbacks, the host gets a reference to `ICLROnEventManager` by calling the [ICLRControl::GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cd4c3-113">説明されているイベント[EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) 2 回以上、アンロード、または CLR の無効化を通知する別のスレッドから発生させることができます。</span><span class="sxs-lookup"><span data-stu-id="cd4c3-113">The events described by [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) can be fired more than once and from different threads to signal an unload or the disabling of the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd4c3-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="cd4c3-114">Requirements</span></span>  
 <span data-ttu-id="cd4c3-115">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cd4c3-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd4c3-116">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="cd4c3-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cd4c3-117">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="cd4c3-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cd4c3-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd4c3-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd4c3-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="cd4c3-119">See also</span></span>

- [<span data-ttu-id="cd4c3-120">EClrEvent 列挙型</span><span class="sxs-lookup"><span data-stu-id="cd4c3-120">EClrEvent Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)
- [<span data-ttu-id="cd4c3-121">IActionOnCLREvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cd4c3-121">IActionOnCLREvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)
- [<span data-ttu-id="cd4c3-122">ICLRControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cd4c3-122">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="cd4c3-123">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cd4c3-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
