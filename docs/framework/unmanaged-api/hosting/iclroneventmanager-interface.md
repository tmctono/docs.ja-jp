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
ms.openlocfilehash: a1b22e77fe20d5e2d755efcd7a63c8f2bdc781e9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140844"
---
# <a name="iclroneventmanager-interface"></a><span data-ttu-id="e5ed8-102">ICLROnEventManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e5ed8-102">ICLROnEventManager Interface</span></span>
<span data-ttu-id="e5ed8-103">ホストが共通言語ランタイム (CLR) イベントのコールバックを登録および登録解除できるようにするメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="e5ed8-103">Provides methods that allow the host to register and unregister callbacks for common language runtime (CLR) events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e5ed8-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="e5ed8-104">Methods</span></span>  
  
|<span data-ttu-id="e5ed8-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="e5ed8-105">Method</span></span>|<span data-ttu-id="e5ed8-106">説明</span><span class="sxs-lookup"><span data-stu-id="e5ed8-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e5ed8-107">RegisterActionOnEvent メソッド</span><span class="sxs-lookup"><span data-stu-id="e5ed8-107">RegisterActionOnEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md)|<span data-ttu-id="e5ed8-108">指定されたイベントのコールバックポインターを登録します。</span><span class="sxs-lookup"><span data-stu-id="e5ed8-108">Registers a callback pointer for the specified event.</span></span>|  
|[<span data-ttu-id="e5ed8-109">UnregisterActionOnEvent メソッド</span><span class="sxs-lookup"><span data-stu-id="e5ed8-109">UnregisterActionOnEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-unregisteractiononevent-method.md)|<span data-ttu-id="e5ed8-110">指定されたイベントに対して、以前に登録されたコールバックポインターの登録を解除します。</span><span class="sxs-lookup"><span data-stu-id="e5ed8-110">Unregisters a previously registered callback pointer for the specified event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e5ed8-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="e5ed8-111">Remarks</span></span>  
 <span data-ttu-id="e5ed8-112">イベントコールバックの登録と登録解除を行うために、ホストは[ICLRControl:: GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md)メソッドを呼び出すことによって `ICLROnEventManager` への参照を取得します。</span><span class="sxs-lookup"><span data-stu-id="e5ed8-112">To register and unregister event callbacks, the host gets a reference to `ICLROnEventManager` by calling the [ICLRControl::GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e5ed8-113">[Eclrevent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)によって説明されているイベントは、異なるスレッドから、または CLR のアンロードまたは無効化を通知するために、複数回発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e5ed8-113">The events described by [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) can be fired more than once and from different threads to signal an unload or the disabling of the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5ed8-114">［要件］</span><span class="sxs-lookup"><span data-stu-id="e5ed8-114">Requirements</span></span>  
 <span data-ttu-id="e5ed8-115">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5ed8-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5ed8-116">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="e5ed8-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e5ed8-117">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="e5ed8-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e5ed8-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5ed8-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5ed8-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="e5ed8-119">See also</span></span>

- [<span data-ttu-id="e5ed8-120">EClrEvent 列挙型</span><span class="sxs-lookup"><span data-stu-id="e5ed8-120">EClrEvent Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)
- [<span data-ttu-id="e5ed8-121">IActionOnCLREvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e5ed8-121">IActionOnCLREvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)
- [<span data-ttu-id="e5ed8-122">ICLRControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e5ed8-122">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="e5ed8-123">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e5ed8-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
