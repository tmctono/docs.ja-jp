---
title: ICorDebugProcess インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess
helpviewer_keywords:
- ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: be86f4b5-418a-4c5c-a67c-97148c65ed8c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 46d96d66f16cd956d8fab1afe00486d564e37953
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775565"
---
# <a name="icordebugprocess-interface"></a><span data-ttu-id="60c38-102">ICorDebugProcess インターフェイス</span><span class="sxs-lookup"><span data-stu-id="60c38-102">ICorDebugProcess Interface</span></span>
<span data-ttu-id="60c38-103">マネージド コードを実行しているプロセスを表します。</span><span class="sxs-lookup"><span data-stu-id="60c38-103">Represents a process that is executing managed code.</span></span> <span data-ttu-id="60c38-104">このインターフェイスは、ICorDebugController のサブクラスです。</span><span class="sxs-lookup"><span data-stu-id="60c38-104">This interface is a subclass of ICorDebugController.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="60c38-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="60c38-105">Methods</span></span>  
  
|<span data-ttu-id="60c38-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="60c38-106">Method</span></span>|<span data-ttu-id="60c38-107">説明</span><span class="sxs-lookup"><span data-stu-id="60c38-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="60c38-108">ClearCurrentException メソッド</span><span class="sxs-lookup"><span data-stu-id="60c38-108">ClearCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-clearcurrentexception-method.md)|<span data-ttu-id="60c38-109">特定のスレッドで現在管理されていない例外をクリアします。</span><span class="sxs-lookup"><span data-stu-id="60c38-109">Clears the current unmanaged exception on the given thread.</span></span>|  
|[<span data-ttu-id="60c38-110">EnableLogMessages メソッド</span><span class="sxs-lookup"><span data-stu-id="60c38-110">EnableLogMessages Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-enablelogmessages-method.md)|<span data-ttu-id="60c38-111">有効にし、デバッガーへのログ メッセージの送信を無効にします。</span><span class="sxs-lookup"><span data-stu-id="60c38-111">Enables and disables the sending of log messages to the debugger.</span></span>|  
|[<span data-ttu-id="60c38-112">EnumerateAppDomains メソッド</span><span class="sxs-lookup"><span data-stu-id="60c38-112">EnumerateAppDomains Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-enumerateappdomains-method.md)|<span data-ttu-id="60c38-113">すべてのプロセスのアプリケーション ドメインを列挙します。</span><span class="sxs-lookup"><span data-stu-id="60c38-113">Enumerates all of the application domains in the process.</span></span>|  
|[<span data-ttu-id="60c38-114">EnumerateObjects メソッド</span><span class="sxs-lookup"><span data-stu-id="60c38-114">EnumerateObjects Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-enumerateobjects-method.md)|<span data-ttu-id="60c38-115">実装されていません。</span><span class="sxs-lookup"><span data-stu-id="60c38-115">Not implemented.</span></span>|  
|[<span data-ttu-id="60c38-116">GetHandle メソッド</span><span class="sxs-lookup"><span data-stu-id="60c38-116">GetHandle Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-gethandle-method.md)|<span data-ttu-id="60c38-117">プロセスを識別するハンドルを取得します。</span><span class="sxs-lookup"><span data-stu-id="60c38-117">Gets a handle to the process.</span></span>|  
|[<span data-ttu-id="60c38-118">GetHelperThreadID メソッド</span><span class="sxs-lookup"><span data-stu-id="60c38-118">GetHelperThreadID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-gethelperthreadid-method.md)|<span data-ttu-id="60c38-119">デバッガーの内部ヘルパーのスレッドのオペレーティング システム (OS) のスレッド ID を取得します。</span><span class="sxs-lookup"><span data-stu-id="60c38-119">Gets the operating system (OS) thread ID for the debugger's internal helper thread.</span></span>|  
|[<span data-ttu-id="60c38-120">GetID メソッド</span><span class="sxs-lookup"><span data-stu-id="60c38-120">GetID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getid-method.md)|<span data-ttu-id="60c38-121">プロセスのオペレーティング システム (OS) の ID を取得します。</span><span class="sxs-lookup"><span data-stu-id="60c38-121">Gets the operating system (OS) ID of the process.</span></span>|  
|[<span data-ttu-id="60c38-122">GetObject メソッド</span><span class="sxs-lookup"><span data-stu-id="60c38-122">GetObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getobject-method.md)|<span data-ttu-id="60c38-123">実装されていません。</span><span class="sxs-lookup"><span data-stu-id="60c38-123">Not implemented.</span></span>|  
|[<span data-ttu-id="60c38-124">GetThread メソッド</span><span class="sxs-lookup"><span data-stu-id="60c38-124">GetThread Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getthread-method.md)|<span data-ttu-id="60c38-125">取得しますが、指定された OS スレッドをある ICorDebugThread インスタンスの id。</span><span class="sxs-lookup"><span data-stu-id="60c38-125">Gets the ICorDebugThread instance that has the specified OS thread ID.</span></span>|  
|[<span data-ttu-id="60c38-126">GetThreadContext メソッド</span><span class="sxs-lookup"><span data-stu-id="60c38-126">GetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getthreadcontext-method.md)|<span data-ttu-id="60c38-127">特定のスレッドのコンテキストを取得します。</span><span class="sxs-lookup"><span data-stu-id="60c38-127">Gets the context for the given thread.</span></span>|  
|[<span data-ttu-id="60c38-128">IsOSSuspended メソッド</span><span class="sxs-lookup"><span data-stu-id="60c38-128">IsOSSuspended Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-isossuspended-method.md)|<span data-ttu-id="60c38-129">デバッガーがプロセスを停止したため、スレッドが中断されたかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="60c38-129">Determines whether the thread has been suspended as a result of the debugger stopping the process.</span></span>|  
|[<span data-ttu-id="60c38-130">IsTransitionStub メソッド</span><span class="sxs-lookup"><span data-stu-id="60c38-130">IsTransitionStub Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-istransitionstub-method.md)|<span data-ttu-id="60c38-131">マネージ コードへの遷移を発生させるスタブ内にアドレスがあるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="60c38-131">Determines whether an address is inside a stub that will cause a transition to managed code.</span></span>|  
|[<span data-ttu-id="60c38-132">ModifyLogSwitch メソッド</span><span class="sxs-lookup"><span data-stu-id="60c38-132">ModifyLogSwitch Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-modifylogswitch-method.md)|<span data-ttu-id="60c38-133">指定したログ スイッチの重大度レベルを設定します。</span><span class="sxs-lookup"><span data-stu-id="60c38-133">Sets the severity level of the specified log switch.</span></span>|  
|[<span data-ttu-id="60c38-134">ReadMemory メソッド</span><span class="sxs-lookup"><span data-stu-id="60c38-134">ReadMemory Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-readmemory-method.md)|<span data-ttu-id="60c38-135">プロセスからメモリを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="60c38-135">Reads memory from the process.</span></span>|  
|[<span data-ttu-id="60c38-136">SetThreadContext メソッド</span><span class="sxs-lookup"><span data-stu-id="60c38-136">SetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-setthreadcontext-method.md)|<span data-ttu-id="60c38-137">特定のスレッドのコンテキストを設定します。</span><span class="sxs-lookup"><span data-stu-id="60c38-137">Sets the context for the given thread.</span></span>|  
|[<span data-ttu-id="60c38-138">ThreadForFiberCookie メソッド</span><span class="sxs-lookup"><span data-stu-id="60c38-138">ThreadForFiberCookie Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-threadforfibercookie-method.md)|<span data-ttu-id="60c38-139">非推奨。</span><span class="sxs-lookup"><span data-stu-id="60c38-139">Deprecated.</span></span>|  
|[<span data-ttu-id="60c38-140">WriteMemory メソッド</span><span class="sxs-lookup"><span data-stu-id="60c38-140">WriteMemory Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-writememory-method.md)|<span data-ttu-id="60c38-141">プロセスのメモリの領域にデータを書き込みます。</span><span class="sxs-lookup"><span data-stu-id="60c38-141">Writes data to an area of memory in the process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="60c38-142">Remarks</span><span class="sxs-lookup"><span data-stu-id="60c38-142">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="60c38-143">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="60c38-143">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="60c38-144">必要条件</span><span class="sxs-lookup"><span data-stu-id="60c38-144">Requirements</span></span>  
 <span data-ttu-id="60c38-145">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="60c38-145">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="60c38-146">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="60c38-146">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="60c38-147">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="60c38-147">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="60c38-148">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="60c38-148">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60c38-149">関連項目</span><span class="sxs-lookup"><span data-stu-id="60c38-149">See also</span></span>

- [<span data-ttu-id="60c38-150">ICorDebug インターフェイス</span><span class="sxs-lookup"><span data-stu-id="60c38-150">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
- [<span data-ttu-id="60c38-151">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="60c38-151">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
