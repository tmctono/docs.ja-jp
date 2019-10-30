---
title: WAIT_OPTION 列挙型
ms.date: 03/30/2017
api_name:
- WAIT_OPTION
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- WAIT_OPTION
helpviewer_keywords:
- WAIT_OPTION enumeration [.NET Framework hosting]
ms.assetid: 962fc293-8ded-4b3b-90ce-2c21a4f1b244
topic_type:
- apiref
ms.openlocfilehash: 9ecfb551b55551e5f6cc7e7e9ffb55e5a96259ee
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141518"
---
# <a name="wait_option-enumeration"></a><span data-ttu-id="8b417-102">WAIT_OPTION 列挙型</span><span class="sxs-lookup"><span data-stu-id="8b417-102">WAIT_OPTION Enumeration</span></span>
<span data-ttu-id="8b417-103">共通言語ランタイム (CLR) ブロックによって操作が要求された場合にホストが実行するアクションを示す値を格納します。</span><span class="sxs-lookup"><span data-stu-id="8b417-103">Contains values that indicate the action a host should take if an operation requested by the common language runtime (CLR) blocks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b417-104">構文</span><span class="sxs-lookup"><span data-stu-id="8b417-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    WAIT_MSGPUMP       = 0x1,  
    WAIT_ALERTABLE     = 0x2,  
    WAIT_NOTINDEADLOCK = 0x4,  
} WAIT_OPTION;  
```  
  
## <a name="members"></a><span data-ttu-id="8b417-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="8b417-105">Members</span></span>  
  
|<span data-ttu-id="8b417-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="8b417-106">Member</span></span>|<span data-ttu-id="8b417-107">説明</span><span class="sxs-lookup"><span data-stu-id="8b417-107">Description</span></span>|  
|------------|-----------------|  
|`WAIT_ALERTABLE`|<span data-ttu-id="8b417-108">CLR が[IHostTask:: Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md)メソッドを呼び出した場合に、タスクが起こされる必要があることをホストに通知します。</span><span class="sxs-lookup"><span data-stu-id="8b417-108">Notifies the host that the task should be awakened if the CLR calls the [IHostTask::Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) method.</span></span>|  
|`WAIT_MSGPUMP`|<span data-ttu-id="8b417-109">スレッドがブロックされた場合に、現在の OS スレッドでメッセージをポンプする必要があることをホストに通知します。</span><span class="sxs-lookup"><span data-stu-id="8b417-109">Notifies the host that it must pump messages on the current OS thread if the thread becomes blocked.</span></span> <span data-ttu-id="8b417-110">ランタイムは、この値を <xref:System.Threading.ApartmentState.STA> のスレッドに対してのみ指定します。</span><span class="sxs-lookup"><span data-stu-id="8b417-110">The runtime specifies this value only on an <xref:System.Threading.ApartmentState.STA> thread.</span></span>|  
|`WAIT_NOTINDEADLOCK`|<span data-ttu-id="8b417-111">指定された同期要求がホストによって壊れていないことをホストに通知します。</span><span class="sxs-lookup"><span data-stu-id="8b417-111">Notifies the host that the specified synchronization request cannot be broken by a host.</span></span> <span data-ttu-id="8b417-112">つまり、ホストは `HOST_E_DEADLOCK`を返すことができません。</span><span class="sxs-lookup"><span data-stu-id="8b417-112">That is, the host cannot return `HOST_E_DEADLOCK`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8b417-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="8b417-113">Remarks</span></span>  
 <span data-ttu-id="8b417-114">[IHostTaskManager:: Sleep](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-sleep-method.md)メソッドと[IHostTaskManager:: switchtotask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-switchtotask-method.md)メソッドは、どちらもこの型のパラメーターを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="8b417-114">The [IHostTaskManager::Sleep](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-sleep-method.md) and [IHostTaskManager::SwitchToTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-switchtotask-method.md) methods both take a parameter of this type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b417-115">［要件］</span><span class="sxs-lookup"><span data-stu-id="8b417-115">Requirements</span></span>  
 <span data-ttu-id="8b417-116">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b417-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b417-117">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="8b417-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8b417-118">**ライブラリ:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="8b417-118">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8b417-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b417-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b417-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="8b417-120">See also</span></span>

- [<span data-ttu-id="8b417-121">ホスティングの列挙型</span><span class="sxs-lookup"><span data-stu-id="8b417-121">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
