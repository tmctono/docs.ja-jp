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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f1e003ba23f680c4a5525a956d758aac6b823eb9
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67769709"
---
# <a name="eclrevent-enumeration"></a><span data-ttu-id="19f67-102">EClrEvent 列挙型</span><span class="sxs-lookup"><span data-stu-id="19f67-102">EClrEvent Enumeration</span></span>
<span data-ttu-id="19f67-103">ホストがコールバックを登録できる共通言語ランタイム (CLR) のイベントについて説明します。</span><span class="sxs-lookup"><span data-stu-id="19f67-103">Describes the common language runtime (CLR) events for which the host can register callbacks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19f67-104">構文</span><span class="sxs-lookup"><span data-stu-id="19f67-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    Event_ClrDisabled,  
    Event_DomainUnload,  
    Event_MDAFired,  
    Event_StackOverflow  
} EClrEvent;  
```  
  
## <a name="members"></a><span data-ttu-id="19f67-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="19f67-105">Members</span></span>  
  
|<span data-ttu-id="19f67-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="19f67-106">Member</span></span>|<span data-ttu-id="19f67-107">説明</span><span class="sxs-lookup"><span data-stu-id="19f67-107">Description</span></span>|  
|------------|-----------------|  
|`Event_ClrDisabled`|<span data-ttu-id="19f67-108">CLR の致命的なエラーを指定します。</span><span class="sxs-lookup"><span data-stu-id="19f67-108">Specifies a fatal CLR error.</span></span>|  
|`Event_DomainUnload`|<span data-ttu-id="19f67-109">特定のアンロードを指定します。<xref:System.AppDomain>します。</span><span class="sxs-lookup"><span data-stu-id="19f67-109">Specifies the unloading of a particular <xref:System.AppDomain>.</span></span>|  
|`Event_MDAFired`|<span data-ttu-id="19f67-110">マネージ デバッグ アシスタント (MDA) メッセージが生成されたことを指定します。</span><span class="sxs-lookup"><span data-stu-id="19f67-110">Specifies that a Managed Debugging Assistant (MDA) message has been generated.</span></span>|  
|`Event_StackOverflow`|<span data-ttu-id="19f67-111">スタックのオーバーフロー エラーが発生したことを指定します。</span><span class="sxs-lookup"><span data-stu-id="19f67-111">Specifies that a stack overflow error has occurred.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="19f67-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="19f67-112">Remarks</span></span>  
 <span data-ttu-id="19f67-113">ホストで説明されているイベントの種類のいずれかのコールバックを登録できる`EClrEvent`のメソッドを呼び出すことによって、 [ICLROnEventManager](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="19f67-113">The host can register callbacks for any of the event types described by `EClrEvent` by calling methods of the [ICLROnEventManager](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md) interface.</span></span> <span data-ttu-id="19f67-114">ホストは、呼び出すことによってこのインターフェイスにポインターを取得、 [iclrcontrol::getclrmanager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="19f67-114">The host gets a pointer to this interface by calling the [ICLRControl::GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) method.</span></span>  
  
 <span data-ttu-id="19f67-115">`Event_CLRDisabled`と`Event_DomainUnload`2 回以上、アンロード、または CLR の無効化を通知する別のスレッドからイベントを発生させることができます。</span><span class="sxs-lookup"><span data-stu-id="19f67-115">The `Event_CLRDisabled` and `Event_DomainUnload` events can be raised more than once and from different threads to signal an unload or the disabling of the CLR.</span></span>  
  
 <span data-ttu-id="19f67-116">`Event_MDAFired`イベント発生の作成、 [MDAInfo](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md) MDA メッセージの詳細を格納しているインスタンス。</span><span class="sxs-lookup"><span data-stu-id="19f67-116">The `Event_MDAFired` event raises the creation of an [MDAInfo](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md) instance that contains the details of the MDA message.</span></span> <span data-ttu-id="19f67-117">Mda の詳細については、次を参照してください。[マネージ デバッグ アシスタントによるエラーの診断](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)します。</span><span class="sxs-lookup"><span data-stu-id="19f67-117">For more information about MDAs, see [Diagnosing Errors with Managed Debugging Assistants](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19f67-118">必要条件</span><span class="sxs-lookup"><span data-stu-id="19f67-118">Requirements</span></span>  
 <span data-ttu-id="19f67-119">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="19f67-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19f67-120">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="19f67-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="19f67-121">**ライブラリ:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="19f67-121">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="19f67-122">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19f67-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19f67-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="19f67-123">See also</span></span>

- [<span data-ttu-id="19f67-124">IActionOnCLREvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="19f67-124">IActionOnCLREvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)
- [<span data-ttu-id="19f67-125">ICLRControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="19f67-125">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="19f67-126">ホスティングの列挙型</span><span class="sxs-lookup"><span data-stu-id="19f67-126">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
