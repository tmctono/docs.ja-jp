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
ms.openlocfilehash: 0073a532f680d8764ec9e76ea22326a630457043
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176436"
---
# <a name="ememoryavailable-enumeration"></a><span data-ttu-id="7effa-102">EMemoryAvailable 列挙型</span><span class="sxs-lookup"><span data-stu-id="7effa-102">EMemoryAvailable Enumeration</span></span>
<span data-ttu-id="7effa-103">コンピュータの空き物理メモリの量を示す値を含みます。</span><span class="sxs-lookup"><span data-stu-id="7effa-103">Contains values that indicate the amount of free physical memory on the computer.</span></span> <span data-ttu-id="7effa-104">これらの値は、Windows API の関数から返される高メモリと`CreateMemoryResourceNotification`低メモリのイベントに論理的にマップされます。</span><span class="sxs-lookup"><span data-stu-id="7effa-104">These values logically map to the events for high and low memory returned from the `CreateMemoryResourceNotification` function in the Windows API.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7effa-105">構文</span><span class="sxs-lookup"><span data-stu-id="7effa-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eMemoryAvailableLow     = 1,  
    eMemoryAvailableNeutral = 2,  
    eMemoryAvailableHigh    = 3
} EMemoryAvailable;  
```  
  
## <a name="members"></a><span data-ttu-id="7effa-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="7effa-106">Members</span></span>  
  
|<span data-ttu-id="7effa-107">メンバー</span><span class="sxs-lookup"><span data-stu-id="7effa-107">Member</span></span>|<span data-ttu-id="7effa-108">説明</span><span class="sxs-lookup"><span data-stu-id="7effa-108">Description</span></span>|  
|------------|-----------------|  
|`eMemoryAvailableHigh`|<span data-ttu-id="7effa-109">多くの物理メモリが利用可能です。</span><span class="sxs-lookup"><span data-stu-id="7effa-109">Plenty of physical memory is available.</span></span>|  
|`eMemoryAvailableLow`|<span data-ttu-id="7effa-110">ごくわずかの物理メモリが使用できます。</span><span class="sxs-lookup"><span data-stu-id="7effa-110">Very little physical memory is available.</span></span>|  
|`eMemoryAvailableNeutral`|<span data-ttu-id="7effa-111">使用可能な物理メモリは中立です。</span><span class="sxs-lookup"><span data-stu-id="7effa-111">The available physical memory is neutral.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7effa-112">解説</span><span class="sxs-lookup"><span data-stu-id="7effa-112">Remarks</span></span>  
 <span data-ttu-id="7effa-113">この値は、呼び出しを使用して、ホストによって共通言語ランタイム (CLR)[ICLRMemoryNotificationCallback::OnMemoryNotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md)に渡されます。</span><span class="sxs-lookup"><span data-stu-id="7effa-113">This value is passed by the host to the common language runtime (CLR) by using a call to the [ICLRMemoryNotificationCallback::OnMemoryNotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7effa-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="7effa-114">Requirements</span></span>  
 <span data-ttu-id="7effa-115">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7effa-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7effa-116">**ヘッダー:** msCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7effa-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7effa-117">**ライブラリ:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7effa-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7effa-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7effa-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7effa-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="7effa-119">See also</span></span>

- [<span data-ttu-id="7effa-120">ホスティングの列挙体</span><span class="sxs-lookup"><span data-stu-id="7effa-120">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
