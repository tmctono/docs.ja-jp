---
title: ICorDebug インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebug
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug
helpviewer_keywords:
- ICorDebug interface [.NET Framework debugging]
ms.assetid: 33f431d7-ab1a-494d-8af2-20ab15aba194
topic_type:
- apiref
ms.openlocfilehash: 0ca66f001d04bc86b64e0fe2d1cd37559e4fc633
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76785117"
---
# <a name="icordebug-interface"></a><span data-ttu-id="48fcd-102">ICorDebug インターフェイス</span><span class="sxs-lookup"><span data-stu-id="48fcd-102">ICorDebug Interface</span></span>
<span data-ttu-id="48fcd-103">開発者が共通言語ランタイム (CLR) 環境でアプリケーションをデバッグできるようにするメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="48fcd-103">Provides methods that allow developers to debug applications in the common language runtime (CLR) environment.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="48fcd-104">混合モード (マネージコードとネイティブコード) のデバッグは、Windows 95、Windows 98、または Windows ME ではサポートされておらず、x86 以外のプラットフォーム (IA64 や AMD64 など) ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="48fcd-104">Mixed-mode (managed and native code) debugging is not supported on Windows 95, Windows 98, or Windows ME, or on non-x86 platforms (such as IA64 and AMD64).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="48fcd-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="48fcd-105">Methods</span></span>  
  
|<span data-ttu-id="48fcd-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="48fcd-106">Method</span></span>|<span data-ttu-id="48fcd-107">説明</span><span class="sxs-lookup"><span data-stu-id="48fcd-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="48fcd-108">CanLaunchOrAttach メソッド</span><span class="sxs-lookup"><span data-stu-id="48fcd-108">CanLaunchOrAttach Method</span></span>](icordebug-canlaunchorattach-method.md)|<span data-ttu-id="48fcd-109">現在のコンピューターおよびランタイム構成のコンテキスト内で、新しいプロセスを起動するか、指定したプロセスにアタッチするかを決定します。</span><span class="sxs-lookup"><span data-stu-id="48fcd-109">Determines whether launching a new process or attaching to the given process is possible within the context of the current machine and runtime configuration.</span></span>|  
|[<span data-ttu-id="48fcd-110">CreateProcess メソッド</span><span class="sxs-lookup"><span data-stu-id="48fcd-110">CreateProcess Method</span></span>](icordebug-createprocess-method.md)|<span data-ttu-id="48fcd-111">デバッガーの制御下でプロセスとそのプライマリスレッドを起動します。</span><span class="sxs-lookup"><span data-stu-id="48fcd-111">Launches a process and its primary thread under the control of the debugger.</span></span>|  
|[<span data-ttu-id="48fcd-112">DebugActiveProcess メソッド</span><span class="sxs-lookup"><span data-stu-id="48fcd-112">DebugActiveProcess Method</span></span>](icordebug-debugactiveprocess-method.md)|<span data-ttu-id="48fcd-113">デバッガーを既存のプロセスにアタッチします。</span><span class="sxs-lookup"><span data-stu-id="48fcd-113">Attaches the debugger to an existing process.</span></span>|  
|[<span data-ttu-id="48fcd-114">EnumerateProcesses メソッド</span><span class="sxs-lookup"><span data-stu-id="48fcd-114">EnumerateProcesses Method</span></span>](icordebug-enumerateprocesses-method.md)|<span data-ttu-id="48fcd-115">デバッグ中のプロセスの列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="48fcd-115">Gets an enumerator for the processes that are being debugged.</span></span>|  
|[<span data-ttu-id="48fcd-116">GetProcess メソッド</span><span class="sxs-lookup"><span data-stu-id="48fcd-116">GetProcess Method</span></span>](icordebug-getprocess-method.md)|<span data-ttu-id="48fcd-117">指定されたプロセス ID を持つ "いいプロセス" オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="48fcd-117">Returns the "ICorDebugProcess" object with the given process ID.</span></span>|  
|[<span data-ttu-id="48fcd-118">Initialize メソッド</span><span class="sxs-lookup"><span data-stu-id="48fcd-118">Initialize Method</span></span>](icordebug-initialize-method.md)|<span data-ttu-id="48fcd-119">`ICorDebug` オブジェクトを初期化します。</span><span class="sxs-lookup"><span data-stu-id="48fcd-119">Initializes the `ICorDebug` object.</span></span>|  
|[<span data-ttu-id="48fcd-120">SetManagedHandler メソッド</span><span class="sxs-lookup"><span data-stu-id="48fcd-120">SetManagedHandler Method</span></span>](icordebug-setmanagedhandler-method.md)|<span data-ttu-id="48fcd-121">マネージイベントのイベントハンドラーオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="48fcd-121">Specifies the event handler object for managed events.</span></span>|  
|[<span data-ttu-id="48fcd-122">SetUnmanagedHandler メソッド</span><span class="sxs-lookup"><span data-stu-id="48fcd-122">SetUnmanagedHandler Method</span></span>](icordebug-setunmanagedhandler-method.md)|<span data-ttu-id="48fcd-123">アンマネージイベントのイベントハンドラーオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="48fcd-123">Specifies the event handler object for unmanaged events.</span></span>|  
|[<span data-ttu-id="48fcd-124">Terminate メソッド</span><span class="sxs-lookup"><span data-stu-id="48fcd-124">Terminate Method</span></span>](icordebug-terminate-method.md)|<span data-ttu-id="48fcd-125">`ICorDebug` オブジェクトを終了します。</span><span class="sxs-lookup"><span data-stu-id="48fcd-125">Terminates the `ICorDebug` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="48fcd-126">コメント</span><span class="sxs-lookup"><span data-stu-id="48fcd-126">Remarks</span></span>  
 <span data-ttu-id="48fcd-127">`ICorDebug` は、デバッガープロセスのイベント処理ループを表します。</span><span class="sxs-lookup"><span data-stu-id="48fcd-127">`ICorDebug` represents an event processing loop for a debugger process.</span></span> <span data-ttu-id="48fcd-128">デバッガーは、このインターフェイスを解放する前に、デバッグされているすべてのプロセスからの "ExitProcess" コール[バック](icordebugmanagedcallback-exitprocess-method.md)を待機する必要があります。</span><span class="sxs-lookup"><span data-stu-id="48fcd-128">The debugger must wait for the [ICorDebugManagedCallback::ExitProcess](icordebugmanagedcallback-exitprocess-method.md) callback from all processes being debugged before releasing this interface.</span></span>  
  
 <span data-ttu-id="48fcd-129">`ICorDebug` オブジェクトは、さらに管理されているすべてのデバッグを制御するための初期オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="48fcd-129">The `ICorDebug` object is the initial object to control all further managed debugging.</span></span> <span data-ttu-id="48fcd-130">.NET Framework バージョン1.0 および1.1 では、このオブジェクトは COM から作成された `CoClass` オブジェクトでした。</span><span class="sxs-lookup"><span data-stu-id="48fcd-130">In the .NET Framework versions 1.0 and 1.1, this object was a `CoClass` object created from COM.</span></span> <span data-ttu-id="48fcd-131">.NET Framework バージョン2.0 では、このオブジェクトは `CoClass` オブジェクトではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="48fcd-131">In the .NET Framework version 2.0, this object is no longer a `CoClass` object.</span></span> <span data-ttu-id="48fcd-132">これは、バージョンを認識する[CreateDebuggingInterfaceFromVersion](../../../../docs/framework/unmanaged-api/hosting/createdebugginginterfacefromversion-function.md)関数によって作成される必要があります。</span><span class="sxs-lookup"><span data-stu-id="48fcd-132">It must be created by the [CreateDebuggingInterfaceFromVersion](../../../../docs/framework/unmanaged-api/hosting/createdebugginginterfacefromversion-function.md) function, which is more version-aware.</span></span> <span data-ttu-id="48fcd-133">この新しい作成関数を使用すると、クライアントは特定のバージョンのデバッグ API もエミュレートする `ICorDebug`の特定の実装を取得できます。</span><span class="sxs-lookup"><span data-stu-id="48fcd-133">This new creation function enables clients to get a specific implementation of `ICorDebug`, which also emulates a specific version of the debugging API.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="48fcd-134">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="48fcd-134">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48fcd-135">要件</span><span class="sxs-lookup"><span data-stu-id="48fcd-135">Requirements</span></span>  
 <span data-ttu-id="48fcd-136">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="48fcd-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48fcd-137">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="48fcd-137">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="48fcd-138">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="48fcd-138">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="48fcd-139">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48fcd-139">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48fcd-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="48fcd-140">See also</span></span>

- [<span data-ttu-id="48fcd-141">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="48fcd-141">Debugging Interfaces</span></span>](debugging-interfaces.md)
