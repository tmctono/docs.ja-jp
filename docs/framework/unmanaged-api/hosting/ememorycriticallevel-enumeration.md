---
title: EMemoryCriticalLevel 列挙型
ms.date: 03/30/2017
api_name:
- EMemoryCriticalLevel
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EMemoryCriticalLevel
helpviewer_keywords:
- EMemoryCriticalLevel enumeration [.NET Framework hosting]
ms.assetid: 2ca8a7a2-7b54-4ba3-8e73-277c7df485f3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 26b3761ab49f36c5f687ff2c62882667e044d299
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67774221"
---
# <a name="ememorycriticallevel-enumeration"></a><span data-ttu-id="4a128-102">EMemoryCriticalLevel 列挙型</span><span class="sxs-lookup"><span data-stu-id="4a128-102">EMemoryCriticalLevel Enumeration</span></span>
<span data-ttu-id="4a128-103">特定のメモリ割り当てが要求されましたが満足することはできません、障害の影響を示す値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4a128-103">Contains values that indicate the impact of a failure when a specific memory allocation has been requested but cannot be satisfied.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a128-104">構文</span><span class="sxs-lookup"><span data-stu-id="4a128-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eTaskCritical      = 0,  
    eAppDomainCritical = 1,  
    eProcessCritical   = 2  
} EMemoryCriticalLevel;  
```  
  
## <a name="members"></a><span data-ttu-id="4a128-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="4a128-105">Members</span></span>  
  
|<span data-ttu-id="4a128-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="4a128-106">Member</span></span>|<span data-ttu-id="4a128-107">説明</span><span class="sxs-lookup"><span data-stu-id="4a128-107">Description</span></span>|  
|------------|-----------------|  
|`eAppDomainCritical`|<span data-ttu-id="4a128-108">割り当てが、割り当てが要求したドメイン内のマネージ コードを実行するための重要なことを示します。</span><span class="sxs-lookup"><span data-stu-id="4a128-108">Indicates that the allocation is critical for executing managed code in the domain that has requested the allocation.</span></span> <span data-ttu-id="4a128-109">メモリの割り当てができない場合、CLR がドメインに引き続き使用できることを保証することはできません。</span><span class="sxs-lookup"><span data-stu-id="4a128-109">If memory cannot be allocated, the CLR cannot guarantee that the domain is still usable.</span></span> <span data-ttu-id="4a128-110">ホストは、割り当てを満たすことができない場合に実行するアクションを決定します。</span><span class="sxs-lookup"><span data-stu-id="4a128-110">The host decides what action to take when the allocation cannot be satisfied.</span></span> <span data-ttu-id="4a128-111">中止する CLR に指示することができますが、`AppDomain`自動的にメソッドを呼び出すことによって実行を継続することを許可または[ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)。</span><span class="sxs-lookup"><span data-stu-id="4a128-111">It can instruct the CLR to abort the `AppDomain` automatically, or allow it to keep running by calling methods on [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md).</span></span>|  
|`eProcessCritical`|<span data-ttu-id="4a128-112">割り当てが、プロセス内のマネージ コードの実行に不可欠であることを示します。</span><span class="sxs-lookup"><span data-stu-id="4a128-112">Indicates that the allocation is critical to the execution of managed code in the process.</span></span> <span data-ttu-id="4a128-113">この値は、ファイナライザーを実行するときに起動中に、を使用されます。</span><span class="sxs-lookup"><span data-stu-id="4a128-113">This value is used during startup and when running finalizers.</span></span> <span data-ttu-id="4a128-114">メモリの割り当てができない場合、プロセスで、CLR は動作できません。</span><span class="sxs-lookup"><span data-stu-id="4a128-114">If memory cannot be allocated, the CLR cannot operate in the process.</span></span> <span data-ttu-id="4a128-115">割り当てに失敗した場合、CLR は無効になります。</span><span class="sxs-lookup"><span data-stu-id="4a128-115">If the allocation fails, the CLR is effectively disabled.</span></span> <span data-ttu-id="4a128-116">CLR にすべての後続の呼び出しは、HOST_E_CLRNOTAVAILABLE で失敗します。</span><span class="sxs-lookup"><span data-stu-id="4a128-116">All subsequent calls into the CLR fail with HOST_E_CLRNOTAVAILABLE.</span></span>|  
|`eTaskCritical`|<span data-ttu-id="4a128-117">割り当てが、割り当てが要求したタスクを実行する重要なことを示します。</span><span class="sxs-lookup"><span data-stu-id="4a128-117">Indicates that the allocation is critical to running the task that has requested the allocation.</span></span> <span data-ttu-id="4a128-118">メモリの割り当てができない場合、CLR は、タスクを実行できることを保証できません。</span><span class="sxs-lookup"><span data-stu-id="4a128-118">If memory cannot be allocated, the CLR cannot guarantee that the task can be executed.</span></span> <span data-ttu-id="4a128-119">CLR を発生させる障害が発生した場合、<xref:System.Threading.ThreadAbortException>物理操作システムのスレッドで。</span><span class="sxs-lookup"><span data-stu-id="4a128-119">In the event of failure, the CLR raises a <xref:System.Threading.ThreadAbortException> on the physical operation system thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4a128-120">Remarks</span><span class="sxs-lookup"><span data-stu-id="4a128-120">Remarks</span></span>  
 <span data-ttu-id="4a128-121">定義されているメモリの割り当て方法、 [IHostMemoryManager](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)と[IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)インターフェイスは、この型のパラメーターを受け取る。</span><span class="sxs-lookup"><span data-stu-id="4a128-121">The memory allocation methods defined in the [IHostMemoryManager](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md) and [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) interfaces take a parameter of this type.</span></span> <span data-ttu-id="4a128-122">エラーの重大度に応じて、ホストを決定できます、割り当て要求をすぐに失敗するか、満たすことができるまで待機するかどうか。</span><span class="sxs-lookup"><span data-stu-id="4a128-122">Depending upon the severity of a failure, a host can decide whether to fail the allocation request immediately or to wait until it can be satisfied.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a128-123">必要条件</span><span class="sxs-lookup"><span data-stu-id="4a128-123">Requirements</span></span>  
 <span data-ttu-id="4a128-124">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a128-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a128-125">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4a128-125">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4a128-126">**ライブラリ:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4a128-126">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4a128-127">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a128-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a128-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="4a128-128">See also</span></span>

- [<span data-ttu-id="4a128-129">ICLRMemoryNotificationCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4a128-129">ICLRMemoryNotificationCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)
- [<span data-ttu-id="4a128-130">ホスティングの列挙型</span><span class="sxs-lookup"><span data-stu-id="4a128-130">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
