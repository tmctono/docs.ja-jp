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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 76fc5f578e6da731ffd6406344d00cda8b57f493
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67772398"
---
# <a name="ememoryavailable-enumeration"></a><span data-ttu-id="5709b-102">EMemoryAvailable 列挙型</span><span class="sxs-lookup"><span data-stu-id="5709b-102">EMemoryAvailable Enumeration</span></span>
<span data-ttu-id="5709b-103">コンピューター上の空き物理メモリの量を示す値を含みます。</span><span class="sxs-lookup"><span data-stu-id="5709b-103">Contains values that indicate the amount of free physical memory on the computer.</span></span> <span data-ttu-id="5709b-104">返されるメモリの高値と安値のこの値は、論理的にイベントに対応付ける、 `CreateMemoryResourceNotification` Windows api 関数。</span><span class="sxs-lookup"><span data-stu-id="5709b-104">These values logically map to the events for high and low memory returned from the `CreateMemoryResourceNotification` function in the Windows API.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5709b-105">構文</span><span class="sxs-lookup"><span data-stu-id="5709b-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eMemoryAvailableLow     = 1,  
    eMemoryAvailableNeutral = 2,  
    eMemoryAvailableHigh    = 3   
} EMemoryAvailable;  
```  
  
## <a name="members"></a><span data-ttu-id="5709b-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="5709b-106">Members</span></span>  
  
|<span data-ttu-id="5709b-107">メンバー</span><span class="sxs-lookup"><span data-stu-id="5709b-107">Member</span></span>|<span data-ttu-id="5709b-108">説明</span><span class="sxs-lookup"><span data-stu-id="5709b-108">Description</span></span>|  
|------------|-----------------|  
|`eMemoryAvailableHigh`|<span data-ttu-id="5709b-109">大量の物理メモリは使用できます。</span><span class="sxs-lookup"><span data-stu-id="5709b-109">Plenty of physical memory is available.</span></span>|  
|`eMemoryAvailableLow`|<span data-ttu-id="5709b-110">ほとんどの物理メモリは使用できます。</span><span class="sxs-lookup"><span data-stu-id="5709b-110">Very little physical memory is available.</span></span>|  
|`eMemoryAvailableNeutral`|<span data-ttu-id="5709b-111">使用可能な物理メモリは、ニュートラルです。</span><span class="sxs-lookup"><span data-stu-id="5709b-111">The available physical memory is neutral.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5709b-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="5709b-112">Remarks</span></span>  
 <span data-ttu-id="5709b-113">呼び出しを使用して、共通言語ランタイム (CLR) にホストによってこの値が渡される、 [iclrmemorynotificationcallback::onmemorynotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="5709b-113">This value is passed by the host to the common language runtime (CLR) by using a call to the [ICLRMemoryNotificationCallback::OnMemoryNotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5709b-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="5709b-114">Requirements</span></span>  
 <span data-ttu-id="5709b-115">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5709b-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5709b-116">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5709b-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5709b-117">**ライブラリ:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5709b-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5709b-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5709b-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5709b-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="5709b-119">See also</span></span>

- [<span data-ttu-id="5709b-120">ホスティングの列挙型</span><span class="sxs-lookup"><span data-stu-id="5709b-120">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
