---
title: ETaskType 列挙型
ms.date: 03/30/2017
api_name:
- ETaskType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ETaskType
helpviewer_keywords:
- ETaskType enumeration [.NET Framework hosting]
ms.assetid: aa527b31-89d4-41f2-ad6f-63b76950b7df
topic_type:
- apiref
ms.openlocfilehash: bc956827ad59fc655137e4147e6d98b6d097d470
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138189"
---
# <a name="etasktype-enumeration"></a><span data-ttu-id="6a607-102">ETaskType 列挙型</span><span class="sxs-lookup"><span data-stu-id="6a607-102">ETaskType Enumeration</span></span>
<span data-ttu-id="6a607-103">[ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)または[IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)インターフェイスによって表されるタスクの種類を示す値を格納します。</span><span class="sxs-lookup"><span data-stu-id="6a607-103">Contains values that indicate the type of task that is represented by either an [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) or an [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a607-104">構文</span><span class="sxs-lookup"><span data-stu-id="6a607-104">Syntax</span></span>  
  
```cpp  
typedef enum ETaskType {  
    TT_DEBUGGERHELPER           = 0x1,  
    TT_GC                       = 0x2,  
    TT_FINALIZER                = 0x4,  
    TT_THREADPOOL_TIMER         = 0x8,  
    TT_THREADPOOL_GATE          = 0x10,  
    TT_THREADPOOL_WORKER        = 0x20,  
    TT_THREADPOOL_IOCOMPLETION  = 0x40,  
    TT_ADUNLOAD                 = 0x80,  
    TT_USER                     = 0x100,  
    TT_THREADPOOL_WAIT          = 0x200,  
    TT_UNKNOWN                  = 0x80000000  
} ETaskType;  
```  
  
## <a name="members"></a><span data-ttu-id="6a607-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="6a607-105">Members</span></span>  
  
|<span data-ttu-id="6a607-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="6a607-106">Member</span></span>|<span data-ttu-id="6a607-107">説明</span><span class="sxs-lookup"><span data-stu-id="6a607-107">Description</span></span>|  
|------------|-----------------|  
|`TT_ADUNLOAD`|<span data-ttu-id="6a607-108">インターフェイスは、アプリケーションドメインのアンロードタスクを表します。</span><span class="sxs-lookup"><span data-stu-id="6a607-108">The interface represents an application domain unloading task.</span></span>|  
|`TT_DEBUGGERHELPER`|<span data-ttu-id="6a607-109">インターフェイスは、デバッガーヘルパータスクを表します。</span><span class="sxs-lookup"><span data-stu-id="6a607-109">The interface represents a debugger helper task.</span></span>|  
|`TT_FINALIZER`|<span data-ttu-id="6a607-110">インターフェイスは、ファイナライザータスクを表します。</span><span class="sxs-lookup"><span data-stu-id="6a607-110">The interface represents a finalizer task.</span></span>|  
|`TT_GC`|<span data-ttu-id="6a607-111">インターフェイスは、ガベージコレクションタスクを表します。</span><span class="sxs-lookup"><span data-stu-id="6a607-111">The interface represents a garbage collection task.</span></span>|  
|`TT_THREADPOOL_GATE`|<span data-ttu-id="6a607-112">インターフェイスは、ゲートスレッドタスクを表します。</span><span class="sxs-lookup"><span data-stu-id="6a607-112">The interface represents a gate thread task.</span></span>|  
|`TT_THREADPOOL_IOCOMPLETION`|<span data-ttu-id="6a607-113">インターフェイスは、i/o スレッドタスクまたは完了ポートスレッドタスクを表します。</span><span class="sxs-lookup"><span data-stu-id="6a607-113">The interface represents an I/O thread task or a completion port thread task.</span></span>|  
|`TT_THREADPOOL_TIMER`|<span data-ttu-id="6a607-114">インターフェイスは、タイマースレッドタスクを表します。</span><span class="sxs-lookup"><span data-stu-id="6a607-114">The interface represents a timer thread task.</span></span>|  
|`TT_THREADPOOL_WAIT`|<span data-ttu-id="6a607-115">インターフェイスは、待機スレッドタスクを表します。</span><span class="sxs-lookup"><span data-stu-id="6a607-115">The interface represents a wait thread task.</span></span>|  
|`TT_THREADPOOL_WORKER`|<span data-ttu-id="6a607-116">インターフェイスは、ワーカースレッドタスクを表します。</span><span class="sxs-lookup"><span data-stu-id="6a607-116">The interface represents a worker thread task.</span></span>|  
|`TT_UNKNOWN`|<span data-ttu-id="6a607-117">タスクは不明です。</span><span class="sxs-lookup"><span data-stu-id="6a607-117">The task is unknown.</span></span>|  
|`TT_USER`|<span data-ttu-id="6a607-118">インターフェイスは、ユーザータスクを表します。</span><span class="sxs-lookup"><span data-stu-id="6a607-118">The interface represents a user task.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6a607-119">［要件］</span><span class="sxs-lookup"><span data-stu-id="6a607-119">Requirements</span></span>  
 <span data-ttu-id="6a607-120">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a607-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6a607-121">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="6a607-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6a607-122">**ライブラリ:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="6a607-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6a607-123">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6a607-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a607-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="6a607-124">See also</span></span>

- [<span data-ttu-id="6a607-125">ホスティングの列挙型</span><span class="sxs-lookup"><span data-stu-id="6a607-125">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
