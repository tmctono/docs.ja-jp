---
title: EMemoryAvailable 列挙型
ms.date: 03/30/2017
api_name:
- EMemoryAvailable
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EMemoryAvailable
helpviewer_keywords:
- EMemoryAvailable enumeration [.NET Framework hosting]
ms.assetid: 38e72a06-dbed-473b-a59b-7e0b3ea4f2af
topic_type:
- apiref
ms.openlocfilehash: 822396e28d000a5309738680fec502e1aeacd67c
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616217"
---
# <a name="ememoryavailable-enumeration"></a><span data-ttu-id="8ce89-102">EMemoryAvailable 列挙型</span><span class="sxs-lookup"><span data-stu-id="8ce89-102">EMemoryAvailable Enumeration</span></span>
<span data-ttu-id="8ce89-103">コンピューターの空き物理メモリの量を示す値を格納します。</span><span class="sxs-lookup"><span data-stu-id="8ce89-103">Contains values that indicate the amount of free physical memory on the computer.</span></span> <span data-ttu-id="8ce89-104">これらの値は、Windows API の関数から返されるメモリの量が多い場合のイベントに論理的にマップされ `CreateMemoryResourceNotification` ます。</span><span class="sxs-lookup"><span data-stu-id="8ce89-104">These values logically map to the events for high and low memory returned from the `CreateMemoryResourceNotification` function in the Windows API.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ce89-105">構文</span><span class="sxs-lookup"><span data-stu-id="8ce89-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eMemoryAvailableLow     = 1,  
    eMemoryAvailableNeutral = 2,  
    eMemoryAvailableHigh    = 3
} EMemoryAvailable;  
```  
  
## <a name="members"></a><span data-ttu-id="8ce89-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="8ce89-106">Members</span></span>  
  
|<span data-ttu-id="8ce89-107">メンバー</span><span class="sxs-lookup"><span data-stu-id="8ce89-107">Member</span></span>|<span data-ttu-id="8ce89-108">説明</span><span class="sxs-lookup"><span data-stu-id="8ce89-108">Description</span></span>|  
|------------|-----------------|  
|`eMemoryAvailableHigh`|<span data-ttu-id="8ce89-109">十分な物理メモリを使用できます。</span><span class="sxs-lookup"><span data-stu-id="8ce89-109">Plenty of physical memory is available.</span></span>|  
|`eMemoryAvailableLow`|<span data-ttu-id="8ce89-110">使用できる物理メモリが非常に少なくなっています。</span><span class="sxs-lookup"><span data-stu-id="8ce89-110">Very little physical memory is available.</span></span>|  
|`eMemoryAvailableNeutral`|<span data-ttu-id="8ce89-111">使用可能な物理メモリはニュートラルです。</span><span class="sxs-lookup"><span data-stu-id="8ce89-111">The available physical memory is neutral.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8ce89-112">解説</span><span class="sxs-lookup"><span data-stu-id="8ce89-112">Remarks</span></span>  
 <span data-ttu-id="8ce89-113">この値は、 [ICLRMemoryNotificationCallback:: OnMemoryNotification](iclrmemorynotificationcallback-onmemorynotification-method.md)メソッドの呼び出しを使用して、ホストによって共通言語ランタイム (CLR) に渡されます。</span><span class="sxs-lookup"><span data-stu-id="8ce89-113">This value is passed by the host to the common language runtime (CLR) by using a call to the [ICLRMemoryNotificationCallback::OnMemoryNotification](iclrmemorynotificationcallback-onmemorynotification-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8ce89-114">要件</span><span class="sxs-lookup"><span data-stu-id="8ce89-114">Requirements</span></span>  
 <span data-ttu-id="8ce89-115">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ce89-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ce89-116">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="8ce89-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8ce89-117">**ライブラリ:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="8ce89-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8ce89-118">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8ce89-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ce89-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="8ce89-119">See also</span></span>

- [<span data-ttu-id="8ce89-120">ホスティングの列挙体</span><span class="sxs-lookup"><span data-stu-id="8ce89-120">Hosting Enumerations</span></span>](hosting-enumerations.md)
