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
ms.openlocfilehash: d98a0c1c3187b81c44fae6eee91d975169a40045
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59072807"
---
# <a name="ememoryavailable-enumeration"></a><span data-ttu-id="cf695-102">EMemoryAvailable 列挙型</span><span class="sxs-lookup"><span data-stu-id="cf695-102">EMemoryAvailable Enumeration</span></span>
<span data-ttu-id="cf695-103">コンピューター上の空き物理メモリの量を示す値を含みます。</span><span class="sxs-lookup"><span data-stu-id="cf695-103">Contains values that indicate the amount of free physical memory on the computer.</span></span> <span data-ttu-id="cf695-104">返されるメモリの高値と安値のこの値は、論理的にイベントに対応付ける、 `CreateMemoryResourceNotification` Windows api 関数。</span><span class="sxs-lookup"><span data-stu-id="cf695-104">These values logically map to the events for high and low memory returned from the `CreateMemoryResourceNotification` function in the Windows API.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf695-105">構文</span><span class="sxs-lookup"><span data-stu-id="cf695-105">Syntax</span></span>  
  
```  
typedef enum {  
    eMemoryAvailableLow     = 1,  
    eMemoryAvailableNeutral = 2,  
    eMemoryAvailableHigh    = 3   
} EMemoryAvailable;  
```  
  
## <a name="members"></a><span data-ttu-id="cf695-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="cf695-106">Members</span></span>  
  
|<span data-ttu-id="cf695-107">メンバー</span><span class="sxs-lookup"><span data-stu-id="cf695-107">Member</span></span>|<span data-ttu-id="cf695-108">説明</span><span class="sxs-lookup"><span data-stu-id="cf695-108">Description</span></span>|  
|------------|-----------------|  
|`eMemoryAvailableHigh`|<span data-ttu-id="cf695-109">大量の物理メモリは使用できます。</span><span class="sxs-lookup"><span data-stu-id="cf695-109">Plenty of physical memory is available.</span></span>|  
|`eMemoryAvailableLow`|<span data-ttu-id="cf695-110">ほとんどの物理メモリは使用できます。</span><span class="sxs-lookup"><span data-stu-id="cf695-110">Very little physical memory is available.</span></span>|  
|`eMemoryAvailableNeutral`|<span data-ttu-id="cf695-111">使用可能な物理メモリは、ニュートラルです。</span><span class="sxs-lookup"><span data-stu-id="cf695-111">The available physical memory is neutral.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cf695-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="cf695-112">Remarks</span></span>  
 <span data-ttu-id="cf695-113">呼び出しを使用して、共通言語ランタイム (CLR) にホストによってこの値が渡される、 [iclrmemorynotificationcallback::onmemorynotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="cf695-113">This value is passed by the host to the common language runtime (CLR) by using a call to the [ICLRMemoryNotificationCallback::OnMemoryNotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf695-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="cf695-114">Requirements</span></span>  
 <span data-ttu-id="cf695-115">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cf695-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf695-116">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="cf695-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cf695-117">**ライブラリ:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cf695-117">**Library:** MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="cf695-118">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="cf695-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="cf695-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="cf695-119">See also</span></span>

- [<span data-ttu-id="cf695-120">ホスティングの列挙体</span><span class="sxs-lookup"><span data-stu-id="cf695-120">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
