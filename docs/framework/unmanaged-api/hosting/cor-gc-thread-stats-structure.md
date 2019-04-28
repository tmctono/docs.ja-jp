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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61696714"
---
# <a name="corgcthreadstats-structure"></a><span data-ttu-id="abddd-102">COR_GC_THREAD_STATS 構造体</span><span class="sxs-lookup"><span data-stu-id="abddd-102">COR_GC_THREAD_STATS Structure</span></span>
<span data-ttu-id="abddd-103">ガベージ コレクションに関連するスレッドごとの統計情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="abddd-103">Contains per-thread statistics pertaining to garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="abddd-104">構文</span><span class="sxs-lookup"><span data-stu-id="abddd-104">Syntax</span></span>  
  
```  
typedef struct _COR_GC_THREAD_STATS {  
    ULONGLONG  PerThreadAllocation;   
    ULONG      Flags;   
} COR_GC_THREAD_STATS;  
```  
  
## <a name="members"></a><span data-ttu-id="abddd-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="abddd-105">Members</span></span>  
  
|<span data-ttu-id="abddd-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="abddd-106">Member</span></span>|<span data-ttu-id="abddd-107">説明</span><span class="sxs-lookup"><span data-stu-id="abddd-107">Description</span></span>|  
|------------|-----------------|  
|`PerThreadAllocation`|<span data-ttu-id="abddd-108">現在関連付けられているスレッドに割り当てられたメモリのバイト数`COR_GC_THREAD_STATS`インスタンス。</span><span class="sxs-lookup"><span data-stu-id="abddd-108">The number of bytes of memory allocated on the thread that is associated with the current `COR_GC_THREAD_STATS` instance.</span></span> <span data-ttu-id="abddd-109">この数は、ジェネレーション 0 ガベージ コレクションが発生するたびに 0 にクリアされます。</span><span class="sxs-lookup"><span data-stu-id="abddd-109">This number is cleared to zero each time a generation-zero garbage collection occurs.</span></span>|  
|`Flags`|<span data-ttu-id="abddd-110">バイト数では、最新のガベージ コレクションを上位のジェネレーションに昇格します。</span><span class="sxs-lookup"><span data-stu-id="abddd-110">The number of bytes promoted to a higher generation at the most recent garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="abddd-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="abddd-111">Remarks</span></span>  
 <span data-ttu-id="abddd-112">[Iclrtask::getmemstats](../../../../docs/framework/unmanaged-api/hosting/iclrtask-getmemstats-method.md)型の出力パラメーターを受け取る`COR_GC_THREAD_STATS`します。</span><span class="sxs-lookup"><span data-stu-id="abddd-112">[ICLRTask::GetMemStats](../../../../docs/framework/unmanaged-api/hosting/iclrtask-getmemstats-method.md) takes an output parameter of type `COR_GC_THREAD_STATS`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="abddd-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="abddd-113">Requirements</span></span>  
 <span data-ttu-id="abddd-114">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="abddd-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="abddd-115">**ヘッダー:** GCHost.idl</span><span class="sxs-lookup"><span data-stu-id="abddd-115">**Header:** GCHost.idl</span></span>  
  
 <span data-ttu-id="abddd-116">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="abddd-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="abddd-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="abddd-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abddd-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="abddd-118">See also</span></span>

- [<span data-ttu-id="abddd-119">ホスト構造体</span><span class="sxs-lookup"><span data-stu-id="abddd-119">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [<span data-ttu-id="abddd-120">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="abddd-120">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
