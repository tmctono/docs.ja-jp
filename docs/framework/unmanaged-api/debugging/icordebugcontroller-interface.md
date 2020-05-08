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
ms.openlocfilehash: e494bbb24e8f2245593e7945625e72e70ae1dde5
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82892765"
---
# <a name="icordebugcontroller-interface"></a><span data-ttu-id="04ea9-102">ICorDebugController インターフェイス</span><span class="sxs-lookup"><span data-stu-id="04ea9-102">ICorDebugController Interface</span></span>

<span data-ttu-id="04ea9-103">コードの実行コンテキストを制御できる <xref:System.Diagnostics.Process> または <xref:System.AppDomain> のスコープを表します。</span><span class="sxs-lookup"><span data-stu-id="04ea9-103">Represents a scope, either a <xref:System.Diagnostics.Process> or an <xref:System.AppDomain>, in which code execution context can be controlled.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="04ea9-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="04ea9-104">Methods</span></span>  
  
|<span data-ttu-id="04ea9-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="04ea9-105">Method</span></span>|<span data-ttu-id="04ea9-106">説明</span><span class="sxs-lookup"><span data-stu-id="04ea9-106">Description</span></span>|  
|------------|-----------------|  
|`ICorDebugController::CanCommitChanges`|<span data-ttu-id="04ea9-107">このメソッドは、互換性のために残されています。</span><span class="sxs-lookup"><span data-stu-id="04ea9-107">This method is obsolete.</span></span>|  
|`ICorDebugController::CommitChanges`|<span data-ttu-id="04ea9-108">このメソッドは、互換性のために残されています。</span><span class="sxs-lookup"><span data-stu-id="04ea9-108">This method is obsolete.</span></span>|  
|[<span data-ttu-id="04ea9-109">Continue メソッド</span><span class="sxs-lookup"><span data-stu-id="04ea9-109">Continue Method</span></span>](icordebugcontroller-continue-method.md)|<span data-ttu-id="04ea9-110">次のように、[コントロール](icordebugcontroller-stop-method.md)スレッドの実行を再開します。</span><span class="sxs-lookup"><span data-stu-id="04ea9-110">Resumes execution of managed threads after a call to [ICorDebugController::Stop](icordebugcontroller-stop-method.md).</span></span>|  
|[<span data-ttu-id="04ea9-111">Detach メソッド</span><span class="sxs-lookup"><span data-stu-id="04ea9-111">Detach Method</span></span>](icordebugcontroller-detach-method.md)|<span data-ttu-id="04ea9-112">プロセスまたはアプリケーションドメインからデバッガーをデタッチします。</span><span class="sxs-lookup"><span data-stu-id="04ea9-112">Detaches the debugger from the process or application domain.</span></span>|  
|[<span data-ttu-id="04ea9-113">EnumerateThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="04ea9-113">EnumerateThreads Method</span></span>](icordebugcontroller-enumeratethreads-method.md)|<span data-ttu-id="04ea9-114">プロセス内のアクティブなマネージスレッドの列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="04ea9-114">Gets an enumerator for the active managed threads in the process.</span></span>|  
|[<span data-ttu-id="04ea9-115">HasQueuedCallbacks メソッド</span><span class="sxs-lookup"><span data-stu-id="04ea9-115">HasQueuedCallbacks Method</span></span>](icordebugcontroller-hasqueuedcallbacks-method.md)|<span data-ttu-id="04ea9-116">マネージコールバックが、指定されたスレッドに対して現在キューに登録されているかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="04ea9-116">Gets a value that indicates whether any managed callbacks are currently queued for the specified thread.</span></span>|  
|[<span data-ttu-id="04ea9-117">IsRunning メソッド</span><span class="sxs-lookup"><span data-stu-id="04ea9-117">IsRunning Method</span></span>](icordebugcontroller-isrunning-method.md)|<span data-ttu-id="04ea9-118">プロセス内のスレッドが現在実行中であるかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="04ea9-118">Gets a value that indicates whether the threads in the process are currently running freely.</span></span>|  
|[<span data-ttu-id="04ea9-119">SetAllThreadsDebugState メソッド</span><span class="sxs-lookup"><span data-stu-id="04ea9-119">SetAllThreadsDebugState Method</span></span>](icordebugcontroller-setallthreadsdebugstate-method.md)|<span data-ttu-id="04ea9-120">プロセス内のすべてのマネージスレッドのデバッグ状態を設定します。</span><span class="sxs-lookup"><span data-stu-id="04ea9-120">Sets the debug state of all managed threads in the process.</span></span>|  
|[<span data-ttu-id="04ea9-121">Stop メソッド</span><span class="sxs-lookup"><span data-stu-id="04ea9-121">Stop Method</span></span>](icordebugcontroller-stop-method.md)|<span data-ttu-id="04ea9-122">プロセスでマネージコードを実行しているすべてのスレッドで協調停止を実行します。</span><span class="sxs-lookup"><span data-stu-id="04ea9-122">Performs a cooperative stop on all threads that are running managed code in the process.</span></span>|  
|[<span data-ttu-id="04ea9-123">Terminate メソッド</span><span class="sxs-lookup"><span data-stu-id="04ea9-123">Terminate Method</span></span>](icordebugcontroller-terminate-method.md)|<span data-ttu-id="04ea9-124">指定された終了コードを使用してプロセスを終了します。</span><span class="sxs-lookup"><span data-stu-id="04ea9-124">Terminates the process with the specified exit code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="04ea9-125">解説</span><span class="sxs-lookup"><span data-stu-id="04ea9-125">Remarks</span></span>  
 <span data-ttu-id="04ea9-126">が`ICorDebugController`プロセスを制御している場合、スコープにはプロセスのすべてのスレッドが含まれます。</span><span class="sxs-lookup"><span data-stu-id="04ea9-126">If `ICorDebugController` is controlling a process, the scope includes all threads of the process.</span></span> <span data-ttu-id="04ea9-127">が`ICorDebugController`アプリケーションドメインを制御している場合、スコープにはその特定のアプリケーションドメインのスレッドだけが含まれます。</span><span class="sxs-lookup"><span data-stu-id="04ea9-127">If `ICorDebugController` is controlling an application domain, the scope includes only the threads of that particular application domain.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="04ea9-128">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="04ea9-128">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="04ea9-129">必要条件</span><span class="sxs-lookup"><span data-stu-id="04ea9-129">Requirements</span></span>  
 <span data-ttu-id="04ea9-130">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="04ea9-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04ea9-131">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="04ea9-131">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="04ea9-132">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="04ea9-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="04ea9-133">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="04ea9-133">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04ea9-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="04ea9-134">See also</span></span>

- [<span data-ttu-id="04ea9-135">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="04ea9-135">Debugging Interfaces</span></span>](debugging-interfaces.md)
