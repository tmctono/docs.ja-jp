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
ms.openlocfilehash: 3633db69877db771d919c9f43da4809f8321f77c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69951196"
---
# <a name="iclroneventmanager-interface"></a><span data-ttu-id="e974f-102">ICLROnEventManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e974f-102">ICLROnEventManager Interface</span></span>
<span data-ttu-id="e974f-103">ホストが共通言語ランタイム (CLR) イベントのコールバックを登録および登録解除できるようにするメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="e974f-103">Provides methods that allow the host to register and unregister callbacks for common language runtime (CLR) events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e974f-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="e974f-104">Methods</span></span>  
  
|<span data-ttu-id="e974f-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="e974f-105">Method</span></span>|<span data-ttu-id="e974f-106">説明</span><span class="sxs-lookup"><span data-stu-id="e974f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e974f-107">RegisterActionOnEvent メソッド</span><span class="sxs-lookup"><span data-stu-id="e974f-107">RegisterActionOnEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md)|<span data-ttu-id="e974f-108">指定されたイベントのコールバックポインターを登録します。</span><span class="sxs-lookup"><span data-stu-id="e974f-108">Registers a callback pointer for the specified event.</span></span>|  
|[<span data-ttu-id="e974f-109">UnregisterActionOnEvent メソッド</span><span class="sxs-lookup"><span data-stu-id="e974f-109">UnregisterActionOnEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-unregisteractiononevent-method.md)|<span data-ttu-id="e974f-110">指定されたイベントに対して、以前に登録されたコールバックポインターの登録を解除します。</span><span class="sxs-lookup"><span data-stu-id="e974f-110">Unregisters a previously registered callback pointer for the specified event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e974f-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="e974f-111">Remarks</span></span>  
 <span data-ttu-id="e974f-112">イベントコールバックの登録と登録解除を行うために、 `ICLROnEventManager`ホストは[ICLRControl:: getclrmanager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md)メソッドを呼び出すことによってへの参照を取得します。</span><span class="sxs-lookup"><span data-stu-id="e974f-112">To register and unregister event callbacks, the host gets a reference to `ICLROnEventManager` by calling the [ICLRControl::GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e974f-113">[Eclrevent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)によって説明されているイベントは、異なるスレッドから、または CLR のアンロードまたは無効化を通知するために、複数回発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e974f-113">The events described by [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) can be fired more than once and from different threads to signal an unload or the disabling of the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e974f-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="e974f-114">Requirements</span></span>  
 <span data-ttu-id="e974f-115">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e974f-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e974f-116">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="e974f-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e974f-117">**ライブラリ**Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="e974f-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e974f-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e974f-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e974f-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="e974f-119">See also</span></span>

- [<span data-ttu-id="e974f-120">EClrEvent 列挙型</span><span class="sxs-lookup"><span data-stu-id="e974f-120">EClrEvent Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)
- [<span data-ttu-id="e974f-121">IActionOnCLREvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e974f-121">IActionOnCLREvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)
- [<span data-ttu-id="e974f-122">ICLRControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e974f-122">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="e974f-123">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e974f-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
