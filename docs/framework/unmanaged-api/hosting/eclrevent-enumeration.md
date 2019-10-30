---
title: EClrEvent 列挙型
ms.date: 03/30/2017
api_name:
- EClrEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EClrEvent
helpviewer_keywords:
- EClrEvent enumeration [.NET Framework hosting]
ms.assetid: 7c36a7c2-75a2-4971-bc23-abf54c812154
topic_type:
- apiref
ms.openlocfilehash: ee749fd40f440e92f1d1b09c2ea5e7bdd51f1cbe
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131131"
---
# <a name="eclrevent-enumeration"></a><span data-ttu-id="231a2-102">EClrEvent 列挙型</span><span class="sxs-lookup"><span data-stu-id="231a2-102">EClrEvent Enumeration</span></span>
<span data-ttu-id="231a2-103">ホストがコールバックを登録できる共通言語ランタイム (CLR) イベントについて説明します。</span><span class="sxs-lookup"><span data-stu-id="231a2-103">Describes the common language runtime (CLR) events for which the host can register callbacks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="231a2-104">構文</span><span class="sxs-lookup"><span data-stu-id="231a2-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    Event_ClrDisabled,  
    Event_DomainUnload,  
    Event_MDAFired,  
    Event_StackOverflow  
} EClrEvent;  
```  
  
## <a name="members"></a><span data-ttu-id="231a2-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="231a2-105">Members</span></span>  
  
|<span data-ttu-id="231a2-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="231a2-106">Member</span></span>|<span data-ttu-id="231a2-107">説明</span><span class="sxs-lookup"><span data-stu-id="231a2-107">Description</span></span>|  
|------------|-----------------|  
|`Event_ClrDisabled`|<span data-ttu-id="231a2-108">致命的な CLR エラーを指定します。</span><span class="sxs-lookup"><span data-stu-id="231a2-108">Specifies a fatal CLR error.</span></span>|  
|`Event_DomainUnload`|<span data-ttu-id="231a2-109">特定の <xref:System.AppDomain>のアンロードを指定します。</span><span class="sxs-lookup"><span data-stu-id="231a2-109">Specifies the unloading of a particular <xref:System.AppDomain>.</span></span>|  
|`Event_MDAFired`|<span data-ttu-id="231a2-110">マネージデバッグアシスタント (MDA) メッセージが生成されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="231a2-110">Specifies that a Managed Debugging Assistant (MDA) message has been generated.</span></span>|  
|`Event_StackOverflow`|<span data-ttu-id="231a2-111">スタックオーバーフローエラーが発生したことを示します。</span><span class="sxs-lookup"><span data-stu-id="231a2-111">Specifies that a stack overflow error has occurred.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="231a2-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="231a2-112">Remarks</span></span>  
 <span data-ttu-id="231a2-113">ホストは、 [ICLROnEventManager](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)インターフェイスのメソッドを呼び出すことによって、`EClrEvent` によって記述されたイベントの種類のコールバックを登録できます。</span><span class="sxs-lookup"><span data-stu-id="231a2-113">The host can register callbacks for any of the event types described by `EClrEvent` by calling methods of the [ICLROnEventManager](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md) interface.</span></span> <span data-ttu-id="231a2-114">ホストは、 [ICLRControl:: GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md)メソッドを呼び出すことによって、このインターフェイスへのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="231a2-114">The host gets a pointer to this interface by calling the [ICLRControl::GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) method.</span></span>  
  
 <span data-ttu-id="231a2-115">`Event_CLRDisabled` イベントと `Event_DomainUnload` イベントを複数回発生させることができ、さまざまなスレッドから、アンロードまたは CLR の無効化を通知することができます。</span><span class="sxs-lookup"><span data-stu-id="231a2-115">The `Event_CLRDisabled` and `Event_DomainUnload` events can be raised more than once and from different threads to signal an unload or the disabling of the CLR.</span></span>  
  
 <span data-ttu-id="231a2-116">`Event_MDAFired` イベントは、MDA メッセージの詳細を含む[MDAInfo](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md)インスタンスの作成を発生させます。</span><span class="sxs-lookup"><span data-stu-id="231a2-116">The `Event_MDAFired` event raises the creation of an [MDAInfo](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md) instance that contains the details of the MDA message.</span></span> <span data-ttu-id="231a2-117">Mda の詳細については、「[マネージデバッグアシスタントによるエラーの診断](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="231a2-117">For more information about MDAs, see [Diagnosing Errors with Managed Debugging Assistants](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="231a2-118">［要件］</span><span class="sxs-lookup"><span data-stu-id="231a2-118">Requirements</span></span>  
 <span data-ttu-id="231a2-119">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="231a2-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="231a2-120">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="231a2-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="231a2-121">**ライブラリ:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="231a2-121">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="231a2-122">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="231a2-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="231a2-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="231a2-123">See also</span></span>

- [<span data-ttu-id="231a2-124">IActionOnCLREvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="231a2-124">IActionOnCLREvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)
- [<span data-ttu-id="231a2-125">ICLRControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="231a2-125">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="231a2-126">ホスティングの列挙型</span><span class="sxs-lookup"><span data-stu-id="231a2-126">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
