---
title: ICorDebugController インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugController
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController
helpviewer_keywords:
- ICorDebugController interface [.NET Framework debugging]
ms.assetid: dbb1c4dc-269a-459b-ab1d-6c70788782ce
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7628aa0ad10398f92d475c4c776810e13fac22b7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59107550"
---
# <a name="icordebugcontroller-interface"></a><span data-ttu-id="4836b-102">ICorDebugController インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4836b-102">ICorDebugController Interface</span></span>

<span data-ttu-id="4836b-103">コードの実行コンテキストを制御できる <xref:System.Diagnostics.Process> または <xref:System.AppDomain> のスコープを表します。</span><span class="sxs-lookup"><span data-stu-id="4836b-103">Represents a scope, either a <xref:System.Diagnostics.Process> or an <xref:System.AppDomain>, in which code execution context can be controlled.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4836b-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="4836b-104">Methods</span></span>  
  
|<span data-ttu-id="4836b-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="4836b-105">Method</span></span>|<span data-ttu-id="4836b-106">説明</span><span class="sxs-lookup"><span data-stu-id="4836b-106">Description</span></span>|  
|------------|-----------------|  
|`ICorDebugController::CanCommitChanges`|<span data-ttu-id="4836b-107">このメソッドは、互換性のために残されています。</span><span class="sxs-lookup"><span data-stu-id="4836b-107">This method is obsolete.</span></span>|  
|`ICorDebugController::CommitChanges`|<span data-ttu-id="4836b-108">このメソッドは、互換性のために残されています。</span><span class="sxs-lookup"><span data-stu-id="4836b-108">This method is obsolete.</span></span>|  
|[<span data-ttu-id="4836b-109">Continue メソッド</span><span class="sxs-lookup"><span data-stu-id="4836b-109">Continue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md)|<span data-ttu-id="4836b-110">呼び出しの後にマネージ スレッドの実行を再開[icordebugcontroller::stop](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="4836b-110">Resumes execution of managed threads after a call to [ICorDebugController::Stop](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md).</span></span>|  
|[<span data-ttu-id="4836b-111">Detach メソッド</span><span class="sxs-lookup"><span data-stu-id="4836b-111">Detach Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-detach-method.md)|<span data-ttu-id="4836b-112">プロセスまたはアプリケーション ドメインからデバッガーをデタッチします。</span><span class="sxs-lookup"><span data-stu-id="4836b-112">Detaches the debugger from the process or application domain.</span></span>|  
|[<span data-ttu-id="4836b-113">EnumerateThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="4836b-113">EnumerateThreads Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-enumeratethreads-method.md)|<span data-ttu-id="4836b-114">プロセスのアクティブなマネージ スレッドの列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="4836b-114">Gets an enumerator for the active managed threads in the process.</span></span>|  
|[<span data-ttu-id="4836b-115">HasQueuedCallbacks メソッド</span><span class="sxs-lookup"><span data-stu-id="4836b-115">HasQueuedCallbacks Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-hasqueuedcallbacks-method.md)|<span data-ttu-id="4836b-116">任意のマネージ コールバックが、指定されたスレッドの現在キューに登録するかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="4836b-116">Gets a value that indicates whether any managed callbacks are currently queued for the specified thread.</span></span>|  
|[<span data-ttu-id="4836b-117">IsRunning メソッド</span><span class="sxs-lookup"><span data-stu-id="4836b-117">IsRunning Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-isrunning-method.md)|<span data-ttu-id="4836b-118">プロセスのスレッドが自由に実行して現在かどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="4836b-118">Gets a value that indicates whether the threads in the process are currently running freely.</span></span>|  
|[<span data-ttu-id="4836b-119">SetAllThreadsDebugState メソッド</span><span class="sxs-lookup"><span data-stu-id="4836b-119">SetAllThreadsDebugState Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-setallthreadsdebugstate-method.md)|<span data-ttu-id="4836b-120">プロセス内のすべてのマネージ スレッドのデバッグ状態を設定します。</span><span class="sxs-lookup"><span data-stu-id="4836b-120">Sets the debug state of all managed threads in the process.</span></span>|  
|[<span data-ttu-id="4836b-121">Stop メソッド</span><span class="sxs-lookup"><span data-stu-id="4836b-121">Stop Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md)|<span data-ttu-id="4836b-122">プロセスでマネージ コードを実行しているすべてのスレッドを協調停止を実行します。</span><span class="sxs-lookup"><span data-stu-id="4836b-122">Performs a cooperative stop on all threads that are running managed code in the process.</span></span>|  
|[<span data-ttu-id="4836b-123">Terminate メソッド</span><span class="sxs-lookup"><span data-stu-id="4836b-123">Terminate Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-terminate-method.md)|<span data-ttu-id="4836b-124">指定した終了コードを使用して、プロセスを終了します。</span><span class="sxs-lookup"><span data-stu-id="4836b-124">Terminates the process with the specified exit code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4836b-125">Remarks</span><span class="sxs-lookup"><span data-stu-id="4836b-125">Remarks</span></span>  
 <span data-ttu-id="4836b-126">場合`ICorDebugController`はプロセスを制御するには、スコープには、プロセスのすべてのスレッドが含まれます。</span><span class="sxs-lookup"><span data-stu-id="4836b-126">If `ICorDebugController` is controlling a process, the scope includes all threads of the process.</span></span> <span data-ttu-id="4836b-127">場合`ICorDebugController`がアプリケーション ドメインを制御するには、スコープにはその特定のアプリケーション ドメインのスレッドのみが含まれます。</span><span class="sxs-lookup"><span data-stu-id="4836b-127">If `ICorDebugController` is controlling an application domain, the scope includes only the threads of that particular application domain.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4836b-128">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="4836b-128">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4836b-129">必要条件</span><span class="sxs-lookup"><span data-stu-id="4836b-129">Requirements</span></span>  
 <span data-ttu-id="4836b-130">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4836b-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4836b-131">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4836b-131">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4836b-132">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4836b-132">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="4836b-133">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="4836b-133">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4836b-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="4836b-134">See also</span></span>

- [<span data-ttu-id="4836b-135">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="4836b-135">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
