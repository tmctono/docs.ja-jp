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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eda866c1a1f1f69f0d042ccfde3dfad293df9b37
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776510"
---
# <a name="waitoption-enumeration"></a><span data-ttu-id="673bb-102">WAIT_OPTION 列挙型</span><span class="sxs-lookup"><span data-stu-id="673bb-102">WAIT_OPTION Enumeration</span></span>
<span data-ttu-id="673bb-103">ホストのアクションは、共通言語ランタイム (CLR) ブロックによって要求された操作を実行する必要がありますかを示す値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="673bb-103">Contains values that indicate the action a host should take if an operation requested by the common language runtime (CLR) blocks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="673bb-104">構文</span><span class="sxs-lookup"><span data-stu-id="673bb-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    WAIT_MSGPUMP       = 0x1,  
    WAIT_ALERTABLE     = 0x2,  
    WAIT_NOTINDEADLOCK = 0x4,  
} WAIT_OPTION;  
```  
  
## <a name="members"></a><span data-ttu-id="673bb-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="673bb-105">Members</span></span>  
  
|<span data-ttu-id="673bb-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="673bb-106">Member</span></span>|<span data-ttu-id="673bb-107">説明</span><span class="sxs-lookup"><span data-stu-id="673bb-107">Description</span></span>|  
|------------|-----------------|  
|`WAIT_ALERTABLE`|<span data-ttu-id="673bb-108">CLR を呼び出す場合に、タスクが起動されることをホストに通知、 [ihosttask::alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="673bb-108">Notifies the host that the task should be awakened if the CLR calls the [IHostTask::Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) method.</span></span>|  
|`WAIT_MSGPUMP`|<span data-ttu-id="673bb-109">スレッドがブロックされた場合に、現在の OS スレッドでメッセージをポンプする必要があります、ホストに通知します。</span><span class="sxs-lookup"><span data-stu-id="673bb-109">Notifies the host that it must pump messages on the current OS thread if the thread becomes blocked.</span></span> <span data-ttu-id="673bb-110">ランタイムでのみこの値を指定します、<xref:System.Threading.ApartmentState.STA>スレッド。</span><span class="sxs-lookup"><span data-stu-id="673bb-110">The runtime specifies this value only on an <xref:System.Threading.ApartmentState.STA> thread.</span></span>|  
|`WAIT_NOTINDEADLOCK`|<span data-ttu-id="673bb-111">ホストによって指定された同期要求を分けることのできないことをホストに通知します。</span><span class="sxs-lookup"><span data-stu-id="673bb-111">Notifies the host that the specified synchronization request cannot be broken by a host.</span></span> <span data-ttu-id="673bb-112">つまり、ホストを返すことができない`HOST_E_DEADLOCK`します。</span><span class="sxs-lookup"><span data-stu-id="673bb-112">That is, the host cannot return `HOST_E_DEADLOCK`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="673bb-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="673bb-113">Remarks</span></span>  
 <span data-ttu-id="673bb-114">[Ihosttaskmanager::sleep](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-sleep-method.md)と[ihosttaskmanager::switchtotask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-switchtotask-method.md)両方のメソッドは、この型のパラメーターを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="673bb-114">The [IHostTaskManager::Sleep](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-sleep-method.md) and [IHostTaskManager::SwitchToTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-switchtotask-method.md) methods both take a parameter of this type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="673bb-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="673bb-115">Requirements</span></span>  
 <span data-ttu-id="673bb-116">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="673bb-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="673bb-117">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="673bb-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="673bb-118">**ライブラリ:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="673bb-118">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="673bb-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="673bb-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="673bb-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="673bb-120">See also</span></span>

- [<span data-ttu-id="673bb-121">ホスティングの列挙型</span><span class="sxs-lookup"><span data-stu-id="673bb-121">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
