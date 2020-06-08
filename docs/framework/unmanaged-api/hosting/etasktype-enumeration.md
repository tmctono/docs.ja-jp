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
ms.openlocfilehash: 0fa72568df77c4916a3c6676e1dcca7c0c616c4a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84493319"
---
# <a name="etasktype-enumeration"></a><span data-ttu-id="ac700-102">ETaskType 列挙型</span><span class="sxs-lookup"><span data-stu-id="ac700-102">ETaskType Enumeration</span></span>
<span data-ttu-id="ac700-103">[ICLRTask](iclrtask-interface.md)または[IHostTask](ihosttask-interface.md)インターフェイスによって表されるタスクの種類を示す値を格納します。</span><span class="sxs-lookup"><span data-stu-id="ac700-103">Contains values that indicate the type of task that is represented by either an [ICLRTask](iclrtask-interface.md) or an [IHostTask](ihosttask-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac700-104">構文</span><span class="sxs-lookup"><span data-stu-id="ac700-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="ac700-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="ac700-105">Members</span></span>  
  
|<span data-ttu-id="ac700-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="ac700-106">Member</span></span>|<span data-ttu-id="ac700-107">説明</span><span class="sxs-lookup"><span data-stu-id="ac700-107">Description</span></span>|  
|------------|-----------------|  
|`TT_ADUNLOAD`|<span data-ttu-id="ac700-108">インターフェイスは、アプリケーションドメインのアンロードタスクを表します。</span><span class="sxs-lookup"><span data-stu-id="ac700-108">The interface represents an application domain unloading task.</span></span>|  
|`TT_DEBUGGERHELPER`|<span data-ttu-id="ac700-109">インターフェイスは、デバッガーヘルパータスクを表します。</span><span class="sxs-lookup"><span data-stu-id="ac700-109">The interface represents a debugger helper task.</span></span>|  
|`TT_FINALIZER`|<span data-ttu-id="ac700-110">インターフェイスは、ファイナライザータスクを表します。</span><span class="sxs-lookup"><span data-stu-id="ac700-110">The interface represents a finalizer task.</span></span>|  
|`TT_GC`|<span data-ttu-id="ac700-111">インターフェイスは、ガベージコレクションタスクを表します。</span><span class="sxs-lookup"><span data-stu-id="ac700-111">The interface represents a garbage collection task.</span></span>|  
|`TT_THREADPOOL_GATE`|<span data-ttu-id="ac700-112">インターフェイスは、ゲートスレッドタスクを表します。</span><span class="sxs-lookup"><span data-stu-id="ac700-112">The interface represents a gate thread task.</span></span>|  
|`TT_THREADPOOL_IOCOMPLETION`|<span data-ttu-id="ac700-113">インターフェイスは、i/o スレッドタスクまたは完了ポートスレッドタスクを表します。</span><span class="sxs-lookup"><span data-stu-id="ac700-113">The interface represents an I/O thread task or a completion port thread task.</span></span>|  
|`TT_THREADPOOL_TIMER`|<span data-ttu-id="ac700-114">インターフェイスは、タイマースレッドタスクを表します。</span><span class="sxs-lookup"><span data-stu-id="ac700-114">The interface represents a timer thread task.</span></span>|  
|`TT_THREADPOOL_WAIT`|<span data-ttu-id="ac700-115">インターフェイスは、待機スレッドタスクを表します。</span><span class="sxs-lookup"><span data-stu-id="ac700-115">The interface represents a wait thread task.</span></span>|  
|`TT_THREADPOOL_WORKER`|<span data-ttu-id="ac700-116">インターフェイスは、ワーカースレッドタスクを表します。</span><span class="sxs-lookup"><span data-stu-id="ac700-116">The interface represents a worker thread task.</span></span>|  
|`TT_UNKNOWN`|<span data-ttu-id="ac700-117">タスクは不明です。</span><span class="sxs-lookup"><span data-stu-id="ac700-117">The task is unknown.</span></span>|  
|`TT_USER`|<span data-ttu-id="ac700-118">インターフェイスは、ユーザータスクを表します。</span><span class="sxs-lookup"><span data-stu-id="ac700-118">The interface represents a user task.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ac700-119">要件</span><span class="sxs-lookup"><span data-stu-id="ac700-119">Requirements</span></span>  
 <span data-ttu-id="ac700-120">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac700-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac700-121">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="ac700-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ac700-122">**ライブラリ:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="ac700-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ac700-123">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac700-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac700-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="ac700-124">See also</span></span>

- [<span data-ttu-id="ac700-125">ホスティングの列挙型</span><span class="sxs-lookup"><span data-stu-id="ac700-125">Hosting Enumerations</span></span>](hosting-enumerations.md)
