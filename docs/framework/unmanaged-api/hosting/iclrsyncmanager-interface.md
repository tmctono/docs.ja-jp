---
title: ICLRSyncManager インターフェイス
ms.date: 03/30/2017
api_name:
- ICLRSyncManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRSyncManager
helpviewer_keywords:
- ICLRSyncManager interface [.NET Framework hosting]
ms.assetid: a49f9d80-1c76-4ddd-8c49-34f913a5c596
topic_type:
- apiref
ms.openlocfilehash: b0b9c0b7d178557806a9ab2893bff2d34dc408ff
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557737"
---
# <a name="iclrsyncmanager-interface"></a><span data-ttu-id="5a65f-102">ICLRSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5a65f-102">ICLRSyncManager Interface</span></span>
<span data-ttu-id="5a65f-103">ホストが要求されたタスクに関する情報を取得し、その同期実装でデッドロックを検出できるようにするメソッドを定義します。</span><span class="sxs-lookup"><span data-stu-id="5a65f-103">Defines methods that allow the host to get information about requested tasks and to detect deadlocks in its synchronization implementation.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5a65f-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="5a65f-104">Methods</span></span>  
  
|<span data-ttu-id="5a65f-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="5a65f-105">Method</span></span>|<span data-ttu-id="5a65f-106">説明</span><span class="sxs-lookup"><span data-stu-id="5a65f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5a65f-107">CreateRWLockOwnerIterator メソッド</span><span class="sxs-lookup"><span data-stu-id="5a65f-107">CreateRWLockOwnerIterator Method</span></span>](iclrsyncmanager-createrwlockowneriterator-method.md)|<span data-ttu-id="5a65f-108">リーダーライターロックを待機しているタスクのセットを決定するために使用するホストの反復子を共通言語ランタイム (CLR) が作成することを要求します。</span><span class="sxs-lookup"><span data-stu-id="5a65f-108">Requests that the common language runtime (CLR) create an iterator for the host to use to determine the set of tasks waiting on a reader-writer lock.</span></span>|  
|[<span data-ttu-id="5a65f-109">DeleteRWLockOwnerIterator メソッド</span><span class="sxs-lookup"><span data-stu-id="5a65f-109">DeleteRWLockOwnerIterator Method</span></span>](iclrsyncmanager-deleterwlockowneriterator-method.md)|<span data-ttu-id="5a65f-110">の呼び出しによって作成された反復子が CLR によって破棄されることを要求 `CreateRWLockOwnerIterator` します。</span><span class="sxs-lookup"><span data-stu-id="5a65f-110">Requests that the CLR destroy an iterator that was created by a call to `CreateRWLockOwnerIterator`.</span></span>|  
|[<span data-ttu-id="5a65f-111">GetMonitorOwner メソッド</span><span class="sxs-lookup"><span data-stu-id="5a65f-111">GetMonitorOwner Method</span></span>](iclrsyncmanager-getmonitorowner-method.md)|<span data-ttu-id="5a65f-112">指定したモニターを所有しているタスクを取得します。</span><span class="sxs-lookup"><span data-stu-id="5a65f-112">Gets the task that owns the specified monitor.</span></span>|  
|[<span data-ttu-id="5a65f-113">GetRWLockOwnerNext メソッド</span><span class="sxs-lookup"><span data-stu-id="5a65f-113">GetRWLockOwnerNext Method</span></span>](iclrsyncmanager-getrwlockownernext-method.md)|<span data-ttu-id="5a65f-114">現在のリーダーライターロックを待機している次のタスクを取得します。</span><span class="sxs-lookup"><span data-stu-id="5a65f-114">Gets the next task that is waiting on the current reader-writer lock.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5a65f-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="5a65f-115">Requirements</span></span>  
 <span data-ttu-id="5a65f-116">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a65f-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a65f-117">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="5a65f-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5a65f-118">**ライブラリ:** MSCorEE.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="5a65f-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5a65f-119">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a65f-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a65f-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="5a65f-120">See also</span></span>

- <xref:System.Threading.Thread>
- [<span data-ttu-id="5a65f-121">IHostSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5a65f-121">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
- <span data-ttu-id="5a65f-122">[マネージド スレッドとアンマネージド スレッド](/previous-versions/dotnet/netframework-4.0/5s8ee185(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="5a65f-122">[Managed and Unmanaged Threading](/previous-versions/dotnet/netframework-4.0/5s8ee185(v=vs.100))</span></span>
- [<span data-ttu-id="5a65f-123">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5a65f-123">Hosting Interfaces</span></span>](hosting-interfaces.md)
