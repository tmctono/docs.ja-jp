---
title: NOTIFY_FILTER 列挙体
ms.date: 03/30/2017
api_name:
- NOTIFY_FILTER
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- NOTIFY_FILTER
helpviewer_keywords:
- NOTIFY_FILTER enumeration [.NET Framework debugging]
ms.assetid: 4789d08f-8683-45d3-ac30-73d48c61e470
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 09c36dd65c8a4202f13d362668f74cd9a362e35a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67744355"
---
# <a name="notifyfilter-enumeration"></a><span data-ttu-id="01718-102">NOTIFY_FILTER 列挙体</span><span class="sxs-lookup"><span data-stu-id="01718-102">NOTIFY_FILTER Enumeration</span></span>
<span data-ttu-id="01718-103">デバッガーの関数のコールバックを識別します。</span><span class="sxs-lookup"><span data-stu-id="01718-103">Identifies callbacks for debugger functions.</span></span> <span data-ttu-id="01718-104">詳細については、次を参照してください。、 [inotifysource 2::setnotifyfilter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="01718-104">For more information, see the [INotifySource2::SetNotifyFilter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01718-105">構文</span><span class="sxs-lookup"><span data-stu-id="01718-105">Syntax</span></span>  
  
```cpp  
enum tagNOTIFY_FILTER  
{  
    NOTIFY_FILTER_ONSYNCCALLOUT    = 0x1,  
    NOTIFY_FILTER_ONSYNCCALLENTER  = 0x2,  
    NOTIFY_FILTER_ONSYNCCALLEXIT   = 0x4,  
    NOTIFY_FILTER_ONSYNCCALLRETURN = 0x8,  
    NOTIFY_FILTER_ALLSYNC = NOTIFY_FILTER_ONSYNCCALLOUT | NOTIFY_FILTER_ONSYNCCALLENTER | NOTIFY_FILTER_ONSYNCCALLEXIT | NOTIFY_FILTER_ONSYNCCALLRETURN,  
    NOTIFY_FILTER_ALL              = 0xffffffff,  
    NOTIFY_FILTER_NONE             = 0  
};  
```  
  
## <a name="members"></a><span data-ttu-id="01718-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="01718-106">Members</span></span>  
  
|<span data-ttu-id="01718-107">メンバー</span><span class="sxs-lookup"><span data-stu-id="01718-107">Member</span></span>|<span data-ttu-id="01718-108">説明</span><span class="sxs-lookup"><span data-stu-id="01718-108">Description</span></span>|  
|------------|-----------------|  
|`NOTIFY_FILTER_ONSYNCCALLOUT`|<span data-ttu-id="01718-109">示します、 [inotifysink 2::onsynccallout](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallout-method.md)メソッドを呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="01718-109">Indicates that the [INotifySink2::OnSyncCallOut](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallout-method.md) method should be invoked.</span></span>|  
|`NOTIFY_FILTER_ONSYNCCALLENTER`|<span data-ttu-id="01718-110">示します、 [inotifysink 2::onsynccallenter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallenter-method.md)メソッドを呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="01718-110">Indicates that the [INotifySink2::OnSyncCallEnter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallenter-method.md) method should be invoked.</span></span>|  
|`NOTIFY_FILTER_ONSYNCCALLEXIT`|<span data-ttu-id="01718-111">示します、 [inotifysink 2::onsynccallexit](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallexit-method.md)メソッドを呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="01718-111">Indicates that the [INotifySink2::OnSyncCallExit](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallexit-method.md) method should be invoked.</span></span>|  
|`NOTIFY_FILTER_ONSYNCCALLRETURN`|<span data-ttu-id="01718-112">示します、 [inotifysink 2::onsynccallreturn](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallreturn-method.md)メソッドを呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="01718-112">Indicates that the [INotifySink2::OnSyncCallReturn](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallreturn-method.md) method should be invoked.</span></span>|  
|`NOTIFY_FILTER_ALLSYNC`|<span data-ttu-id="01718-113">示すすべての[INotifySink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)メソッドを呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="01718-113">Indicates that all of the [INotifySink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md) methods should be invoked.</span></span>|  
|`NOTIFY_FILTER_ALL`|<span data-ttu-id="01718-114">既存および将来のすべての通知をアクティブにします。</span><span class="sxs-lookup"><span data-stu-id="01718-114">Activates all existing and future notifications.</span></span>|  
|`NOTIFY_FILTER_NONE`|<span data-ttu-id="01718-115">通知メソッドを呼び出す必要がないことを示します。</span><span class="sxs-lookup"><span data-stu-id="01718-115">Indicates that no notification methods should be invoked.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="01718-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="01718-116">Requirements</span></span>  
 <span data-ttu-id="01718-117">**ヘッダー:** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="01718-117">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01718-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="01718-118">See also</span></span>

- [<span data-ttu-id="01718-119">シンボル ストア診断列挙型</span><span class="sxs-lookup"><span data-stu-id="01718-119">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
