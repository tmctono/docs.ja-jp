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
ms.openlocfilehash: b99630ba60cd84254024b91dba9ef9922fd7e041
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69943310"
---
# <a name="icordebugprocess-interface"></a><span data-ttu-id="76ce1-102">ICorDebugProcess インターフェイス</span><span class="sxs-lookup"><span data-stu-id="76ce1-102">ICorDebugProcess Interface</span></span>
<span data-ttu-id="76ce1-103">マネージド コードを実行しているプロセスを表します。</span><span class="sxs-lookup"><span data-stu-id="76ce1-103">Represents a process that is executing managed code.</span></span> <span data-ttu-id="76ce1-104">このインターフェイスは、というコントロールのサブクラスです。</span><span class="sxs-lookup"><span data-stu-id="76ce1-104">This interface is a subclass of ICorDebugController.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="76ce1-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="76ce1-105">Methods</span></span>  
  
|<span data-ttu-id="76ce1-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="76ce1-106">Method</span></span>|<span data-ttu-id="76ce1-107">説明</span><span class="sxs-lookup"><span data-stu-id="76ce1-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="76ce1-108">ClearCurrentException メソッド</span><span class="sxs-lookup"><span data-stu-id="76ce1-108">ClearCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-clearcurrentexception-method.md)|<span data-ttu-id="76ce1-109">指定されたスレッドで現在のアンマネージ例外をクリアします。</span><span class="sxs-lookup"><span data-stu-id="76ce1-109">Clears the current unmanaged exception on the given thread.</span></span>|  
|[<span data-ttu-id="76ce1-110">EnableLogMessages メソッド</span><span class="sxs-lookup"><span data-stu-id="76ce1-110">EnableLogMessages Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-enablelogmessages-method.md)|<span data-ttu-id="76ce1-111">デバッガーへのログメッセージの送信を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="76ce1-111">Enables and disables the sending of log messages to the debugger.</span></span>|  
|[<span data-ttu-id="76ce1-112">EnumerateAppDomains メソッド</span><span class="sxs-lookup"><span data-stu-id="76ce1-112">EnumerateAppDomains Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-enumerateappdomains-method.md)|<span data-ttu-id="76ce1-113">プロセス内のすべてのアプリケーションドメインを列挙します。</span><span class="sxs-lookup"><span data-stu-id="76ce1-113">Enumerates all of the application domains in the process.</span></span>|  
|[<span data-ttu-id="76ce1-114">EnumerateObjects メソッド</span><span class="sxs-lookup"><span data-stu-id="76ce1-114">EnumerateObjects Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-enumerateobjects-method.md)|<span data-ttu-id="76ce1-115">実装されていません。</span><span class="sxs-lookup"><span data-stu-id="76ce1-115">Not implemented.</span></span>|  
|[<span data-ttu-id="76ce1-116">GetHandle メソッド</span><span class="sxs-lookup"><span data-stu-id="76ce1-116">GetHandle Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-gethandle-method.md)|<span data-ttu-id="76ce1-117">プロセスを処理するハンドルを取得します。</span><span class="sxs-lookup"><span data-stu-id="76ce1-117">Gets a handle to the process.</span></span>|  
|[<span data-ttu-id="76ce1-118">GetHelperThreadID メソッド</span><span class="sxs-lookup"><span data-stu-id="76ce1-118">GetHelperThreadID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-gethelperthreadid-method.md)|<span data-ttu-id="76ce1-119">デバッガーの内部ヘルパースレッドのオペレーティングシステム (OS) スレッド ID を取得します。</span><span class="sxs-lookup"><span data-stu-id="76ce1-119">Gets the operating system (OS) thread ID for the debugger's internal helper thread.</span></span>|  
|[<span data-ttu-id="76ce1-120">GetID メソッド</span><span class="sxs-lookup"><span data-stu-id="76ce1-120">GetID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getid-method.md)|<span data-ttu-id="76ce1-121">プロセスのオペレーティングシステム (OS) ID を取得します。</span><span class="sxs-lookup"><span data-stu-id="76ce1-121">Gets the operating system (OS) ID of the process.</span></span>|  
|[<span data-ttu-id="76ce1-122">GetObject メソッド</span><span class="sxs-lookup"><span data-stu-id="76ce1-122">GetObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getobject-method.md)|<span data-ttu-id="76ce1-123">実装されていません。</span><span class="sxs-lookup"><span data-stu-id="76ce1-123">Not implemented.</span></span>|  
|[<span data-ttu-id="76ce1-124">GetThread メソッド</span><span class="sxs-lookup"><span data-stu-id="76ce1-124">GetThread Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getthread-method.md)|<span data-ttu-id="76ce1-125">指定された OS スレッド ID を持つコードスレッドインスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="76ce1-125">Gets the ICorDebugThread instance that has the specified OS thread ID.</span></span>|  
|[<span data-ttu-id="76ce1-126">GetThreadContext メソッド</span><span class="sxs-lookup"><span data-stu-id="76ce1-126">GetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getthreadcontext-method.md)|<span data-ttu-id="76ce1-127">指定されたスレッドのコンテキストを取得します。</span><span class="sxs-lookup"><span data-stu-id="76ce1-127">Gets the context for the given thread.</span></span>|  
|[<span data-ttu-id="76ce1-128">IsOSSuspended メソッド</span><span class="sxs-lookup"><span data-stu-id="76ce1-128">IsOSSuspended Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-isossuspended-method.md)|<span data-ttu-id="76ce1-129">デバッガーがプロセスを停止した結果としてスレッドが中断されたかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="76ce1-129">Determines whether the thread has been suspended as a result of the debugger stopping the process.</span></span>|  
|[<span data-ttu-id="76ce1-130">IsTransitionStub メソッド</span><span class="sxs-lookup"><span data-stu-id="76ce1-130">IsTransitionStub Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-istransitionstub-method.md)|<span data-ttu-id="76ce1-131">マネージコードへの遷移を発生させるスタブ内にアドレスがあるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="76ce1-131">Determines whether an address is inside a stub that will cause a transition to managed code.</span></span>|  
|[<span data-ttu-id="76ce1-132">ModifyLogSwitch メソッド</span><span class="sxs-lookup"><span data-stu-id="76ce1-132">ModifyLogSwitch Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-modifylogswitch-method.md)|<span data-ttu-id="76ce1-133">指定されたログスイッチの重大度レベルを設定します。</span><span class="sxs-lookup"><span data-stu-id="76ce1-133">Sets the severity level of the specified log switch.</span></span>|  
|[<span data-ttu-id="76ce1-134">ReadMemory メソッド</span><span class="sxs-lookup"><span data-stu-id="76ce1-134">ReadMemory Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-readmemory-method.md)|<span data-ttu-id="76ce1-135">プロセスからメモリを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="76ce1-135">Reads memory from the process.</span></span>|  
|[<span data-ttu-id="76ce1-136">SetThreadContext メソッド</span><span class="sxs-lookup"><span data-stu-id="76ce1-136">SetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-setthreadcontext-method.md)|<span data-ttu-id="76ce1-137">指定されたスレッドのコンテキストを設定します。</span><span class="sxs-lookup"><span data-stu-id="76ce1-137">Sets the context for the given thread.</span></span>|  
|[<span data-ttu-id="76ce1-138">ThreadForFiberCookie メソッド</span><span class="sxs-lookup"><span data-stu-id="76ce1-138">ThreadForFiberCookie Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-threadforfibercookie-method.md)|<span data-ttu-id="76ce1-139">使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="76ce1-139">Deprecated.</span></span>|  
|[<span data-ttu-id="76ce1-140">WriteMemory メソッド</span><span class="sxs-lookup"><span data-stu-id="76ce1-140">WriteMemory Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-writememory-method.md)|<span data-ttu-id="76ce1-141">プロセスのメモリ領域にデータを書き込みます。</span><span class="sxs-lookup"><span data-stu-id="76ce1-141">Writes data to an area of memory in the process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="76ce1-142">Remarks</span><span class="sxs-lookup"><span data-stu-id="76ce1-142">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="76ce1-143">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="76ce1-143">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="76ce1-144">必要条件</span><span class="sxs-lookup"><span data-stu-id="76ce1-144">Requirements</span></span>  
 <span data-ttu-id="76ce1-145">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="76ce1-145">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="76ce1-146">**ヘッダー:** CorDebug .idl、CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="76ce1-146">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="76ce1-147">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="76ce1-147">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="76ce1-148">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="76ce1-148">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76ce1-149">関連項目</span><span class="sxs-lookup"><span data-stu-id="76ce1-149">See also</span></span>

- [<span data-ttu-id="76ce1-150">ICorDebug インターフェイス</span><span class="sxs-lookup"><span data-stu-id="76ce1-150">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
- [<span data-ttu-id="76ce1-151">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="76ce1-151">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
