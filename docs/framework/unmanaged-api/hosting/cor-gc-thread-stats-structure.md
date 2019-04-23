---
title: COR_GC_THREAD_STATS 構造体
ms.date: 03/30/2017
api_name:
- COR_GC_THREAD_STATS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COR_GC_THREAD_STATS
helpviewer_keywords:
- COR_GC_THREAD_STATS structure [.NET Framework hosting]
ms.assetid: 01f9a59b-7679-4d42-9ced-4a8981625c3d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f60a4b56270318a05d0e5a480fdb56eb45593d5e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59177737"
---
# <a name="corgcthreadstats-structure"></a><span data-ttu-id="a1888-102">COR_GC_THREAD_STATS 構造体</span><span class="sxs-lookup"><span data-stu-id="a1888-102">COR_GC_THREAD_STATS Structure</span></span>
<span data-ttu-id="a1888-103">ガベージ コレクションに関連するスレッドごとの統計情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a1888-103">Contains per-thread statistics pertaining to garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1888-104">構文</span><span class="sxs-lookup"><span data-stu-id="a1888-104">Syntax</span></span>  
  
```  
typedef struct _COR_GC_THREAD_STATS {  
    ULONGLONG  PerThreadAllocation;   
    ULONG      Flags;   
} COR_GC_THREAD_STATS;  
```  
  
## <a name="members"></a><span data-ttu-id="a1888-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="a1888-105">Members</span></span>  
  
|<span data-ttu-id="a1888-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="a1888-106">Member</span></span>|<span data-ttu-id="a1888-107">説明</span><span class="sxs-lookup"><span data-stu-id="a1888-107">Description</span></span>|  
|------------|-----------------|  
|`PerThreadAllocation`|<span data-ttu-id="a1888-108">現在関連付けられているスレッドに割り当てられたメモリのバイト数`COR_GC_THREAD_STATS`インスタンス。</span><span class="sxs-lookup"><span data-stu-id="a1888-108">The number of bytes of memory allocated on the thread that is associated with the current `COR_GC_THREAD_STATS` instance.</span></span> <span data-ttu-id="a1888-109">この数は、ジェネレーション 0 ガベージ コレクションが発生するたびに 0 にクリアされます。</span><span class="sxs-lookup"><span data-stu-id="a1888-109">This number is cleared to zero each time a generation-zero garbage collection occurs.</span></span>|  
|`Flags`|<span data-ttu-id="a1888-110">バイト数では、最新のガベージ コレクションを上位のジェネレーションに昇格します。</span><span class="sxs-lookup"><span data-stu-id="a1888-110">The number of bytes promoted to a higher generation at the most recent garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a1888-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="a1888-111">Remarks</span></span>  
 <span data-ttu-id="a1888-112">[Iclrtask::getmemstats](../../../../docs/framework/unmanaged-api/hosting/iclrtask-getmemstats-method.md)型の出力パラメーターを受け取る`COR_GC_THREAD_STATS`します。</span><span class="sxs-lookup"><span data-stu-id="a1888-112">[ICLRTask::GetMemStats](../../../../docs/framework/unmanaged-api/hosting/iclrtask-getmemstats-method.md) takes an output parameter of type `COR_GC_THREAD_STATS`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1888-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="a1888-113">Requirements</span></span>  
 <span data-ttu-id="a1888-114">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a1888-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1888-115">**ヘッダー:** GCHost.idl</span><span class="sxs-lookup"><span data-stu-id="a1888-115">**Header:** GCHost.idl</span></span>  
  
 <span data-ttu-id="a1888-116">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="a1888-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a1888-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1888-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1888-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="a1888-118">See also</span></span>

- [<span data-ttu-id="a1888-119">ホスト構造体</span><span class="sxs-lookup"><span data-stu-id="a1888-119">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [<span data-ttu-id="a1888-120">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a1888-120">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
